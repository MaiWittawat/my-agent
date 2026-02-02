# -----------------------------------------------------------
# PART 1: GATHER INPUT & CONFIGURATION
# -----------------------------------------------------------
Write-Host "🚀 INITIALIZING FULL PROJECT & AGENT..." -ForegroundColor Cyan
$projectName = Read-Host "Enter Project Name (e.g. my-app)"
$projectType = Read-Host "Enter Project Type (single/fullstack)"

Write-Host "`nSelect Tech Stack:"
Write-Host "1. Node.js + React (Vite)"
Write-Host "2. Python (FastAPI) + React"
Write-Host "3. Go (Golang) + HTML/Templates"
Write-Host "4. Custom"
$stackChoice = Read-Host "Enter Choice (1-4)"

# กำหนดค่าตัวแปรตาม Stack ที่เลือก
$techStack = ""
$aiRole = ""
$codingRules = ""

switch ($stackChoice) {
    "1" { 
        $techStack = "Node.js, Express, React (Vite)" 
        $aiRole = "Senior Fullstack JS Developer"
        $codingRules = "- Use ES6+ syntax.`n- Prefer Functional Components & Hooks."
    }
    "2" { 
        $techStack = "Python, FastAPI, React" 
        $aiRole = "Senior Python Developer"
        $codingRules = "- Follow PEP8.`n- Use Pydantic for models."
    }
    "3" { 
        $techStack = "Go (Golang), HTML, Vanilla JS" 
        $aiRole = "Senior Go Systems Architect"
        $codingRules = "- ALWAYS handle errors (if err != nil).`n- Follow 'Effective Go'.`n- Use Clean Architecture."
    }
    Default { 
        $techStack = Read-Host "Enter Manual Stack" 
        $aiRole = "Senior Software Architect"
        $codingRules = "- Follow industry best practices."
    }
}

# -----------------------------------------------------------
# PART 2: BUILD DYNAMIC STRUCTURE (Logic สร้างโครงสร้าง)
# -----------------------------------------------------------
Write-Host "`n🏗️  Building Directory Structure..." -ForegroundColor Yellow

# 2.1 Folder มาตรฐาน (มีทุกโปรเจกต์)
$baseDirs = @(
    "docs/design",
    "docs/tasks",
    "docs/logs",
    "logs",
    ".agent/rules",
    ".agent/workflows",
    ".agent/skills"
)

# 2.2 กำหนด Source Directories และ Tree Diagram ตามประเภทโปรเจกต์
$srcDirs = @()
$structureDiagram = "" # ตัวแปรเก็บข้อความ Diagram

if ($projectType -eq "fullstack") {
    # กรณี Full Stack
    $srcDirs += "$projectName/frontend/src", "$projectName/backend/src"
    $srcContext = "Frontend in '$projectName/frontend', Backend in '$projectName/backend'"
    
    # สร้าง Diagram สำหรับ Full Stack
    $structureDiagram = @"
 [project_name]/         # <--- SOURCE CODE ROOT ($projectName)
    frontend/           # Client-side ($techStack)
       src/
       tests/
    backend/            # Server-side
        src/
        tests/
"@
} else {
    # กรณี Single App
    $srcDirs += "$projectName/app/src"
    $srcContext = "Source code in '$projectName/app/src'"

    # สร้าง Diagram สำหรับ Single App
    $structureDiagram = @"
 [project_name]/         # <--- SOURCE CODE ROOT ($projectName)
    app/                # Main Application ($techStack)
       src/
       tests/
"@
}

# รวม Folder ทั้งหมดและสร้างจริง
$allDirs = $baseDirs + $srcDirs
foreach ($dir in $allDirs) {
    if (-not (Test-Path $dir)) { New-Item -ItemType Directory -Path $dir -Force | Out-Null }
}

# -----------------------------------------------------------
# PART 3: CREATE AGENT BRAIN (สร้างสมอง + Dynamic Rules)
# -----------------------------------------------------------
Write-Host "🧠 Injecting Agent Intelligence..." -ForegroundColor Yellow

# 3.1 สร้างไฟล์ workspace-setup.md (แบบ Dynamic)
# เราเอา $structureDiagram ที่สร้างไว้ด้านบนมาใส่ตรงนี้
$workspaceSetupContent = @"
# Workspace Setup Guidelines
---
last_updated: $(Get-Date -Format "yyyy-MM-dd")
project_type: $projectType
stack: $techStack
---

## Directory Structure
This project follows a **$projectType** structure using **$techStack**.

```text
/
 .agent/                 # Agent configuration and rules
    rules/              # Active rule definitions
 docs/                   # Documentation & Planning
    design/             # Architecture, Designs
    tasks/              # Task breakdown
    working_logs/       # Archived logs
 logs/                   # System & Activity logs
$structureDiagram
 WORKING_LOG.md          # Active working log
 README.md               # Setup instructions
 .gitignore              # Security exclusions