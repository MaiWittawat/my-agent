# Agent Templates — Central Library

Template agents กลางสำหรับหยิบไปใช้ในทุก project เมื่อ copy ไปแล้ว agent จะถามคำถามเพื่อ customize ตัวเองให้เจาะจงกับธุรกิจนั้นๆ

> **วิธีใช้:** เลือก agent → copy ไฟล์ไปยัง project → เปิดใช้ครั้งแรก agent จะถามคำถาม → ตอบคำถาม → agent พร้อมใช้งาน
>
> ดูรายละเอียดที่ [_onboarding.md](_onboarding.md)

---

## สารบัญ

### 🎯 Marketing (การตลาด)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Campaign Planner | [campaign-planner.md](marketing/campaign-planner.md) | วางแผน promotion, Flash Sale, Bundle Deal | Pricing Strategy, Urgency Marketing, Campaign Calendar, Copywriting |
| Content Creator | [content-creator.md](marketing/content-creator.md) | สร้าง content สำหรับ social media | Hook Writing, Storytelling, Hashtag Strategy, Trend Hijacking |
| Listing Optimizer | [listing-optimizer.md](marketing/listing-optimizer.md) | เขียนและ optimize product listing บน marketplace | Marketplace SEO, Title Optimization, Competitive Analysis |

### 📊 Sales (การขายและวิเคราะห์)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Sales Analyst | [sales-analyst.md](sales/sales-analyst.md) | วิเคราะห์ยอดขาย แปลงเป็น insight | Performance Analysis, Trend Detection, Cohort Analysis |
| CRM Manager | [crm-manager.md](sales/crm-manager.md) | จัดการความสัมพันธ์ลูกค้า เพิ่ม retention | Customer Segmentation, Lifecycle Marketing, CLV Analysis |

### ⚙️ Operations (ปฏิบัติการ)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Inventory Manager | [inventory-manager.md](operations/inventory-manager.md) | ติดตามสต็อก วางแผนสั่งซื้อ | Stock Monitoring, Reorder Calculation, Demand Forecasting |
| Project Coordinator | [project-coordinator.md](operations/project-coordinator.md) | ประสานงาน ติดตาม deadline จัดลำดับงาน | Task Breakdown, Timeline Management, Risk Identification |

### 💬 Customer Experience (ลูกค้าสัมพันธ์)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Customer Support | [customer-support.md](customer-experience/customer-support.md) | ตอบคำถาม แก้ปัญหา จัดการ complaint | FAQ, Complaint Resolution, Escalation Management |
| Community Manager | [community-manager.md](customer-experience/community-manager.md) | ดูแล community กระตุ้น engagement | Engagement Strategy, UGC Curation, Crisis Communication |

### 💰 Finance (การเงิน)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Financial Analyst | [financial-analyst.md](finance/financial-analyst.md) | วิเคราะห์ P&L, forecast, budget planning | P&L Analysis, Revenue Forecasting, Cost Optimization |
| Pricing Strategist | [pricing-strategist.md](finance/pricing-strategist.md) | กำหนดราคาสินค้า/บริการ | Cost-Plus, Value-Based, Competitive Pricing, Scenario Modeling |

### 👥 HR (ทรัพยากรบุคคล)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| HR Advisor | [hr-advisor.md](hr/hr-advisor.md) | ให้คำปรึกษา HR, สรรหา, onboarding | JD Writing, Interview Design, Policy Drafting |
| Training Coordinator | [training-coordinator.md](hr/training-coordinator.md) | ออกแบบ training program | Skill Gap Analysis, Learning Path Design, ROI Measurement |

### 💻 Tech (เทคโนโลยี)
| Agent | ไฟล์ | หน้าที่หลัก | Skills หลัก |
|---|---|---|---|
| Backend Engineer | [backend-engineer.md](tech/backend-engineer.md) | เขียน API, database, server-side logic | API Dev, DB Design, Auth, Integration, Performance |
| Frontend Engineer | [frontend-engineer.md](tech/frontend-engineer.md) | สร้าง UI, components, responsive design | Component Dev, State Management, Forms, A11y |
| Fullstack Engineer | [fullstack-engineer.md](tech/fullstack-engineer.md) | implement feature ครบทั้ง stack (UI → API → DB) | API-First, Full CRUD, End-to-End |
| DevOps Engineer | [devops-engineer.md](tech/devops-engineer.md) | ดูแล infra, CI/CD, deploy, monitoring | CI/CD Pipeline, IaC, Containerization, Incident Response |
| System Architect | [system-architect.md](tech/system-architect.md) | ออกแบบ system architecture | System Design, API Design, Trade-off Analysis, Scalability |
| Data Analyst | [data-analyst.md](tech/data-analyst.md) | วิเคราะห์ data, สร้าง pipeline, dashboard | SQL, Data Pipeline, Statistical Analysis, Dashboard Design |
| QA Engineer | [qa-engineer.md](tech/qa-engineer.md) | ทดสอบ software, เขียน test automation | Test Planning, Automation, Performance Testing, Bug Reporting |
| Mobile Engineer | [mobile-engineer.md](tech/mobile-engineer.md) | สร้าง mobile app (iOS/Android/cross-platform) | Native Features, Navigation, Offline, App Store |
| AI/ML Engineer | [ai-ml-engineer.md](tech/ai-ml-engineer.md) | integrate AI/ML เข้า product, LLM, pipeline | Prompt Engineering, RAG, ML Pipeline, Evaluation |
| Security Engineer | [security-engineer.md](tech/security-engineer.md) | security review, pentest, compliance | Threat Modeling, OWASP, Auth, Encryption, Incident Response |
| Technical Writer | [technical-writer.md](tech/technical-writer.md) | เขียน API docs, guides, runbooks, ADR | API Docs, Getting Started, Runbooks, Diagrams |
| SRE | [sre-engineer.md](tech/sre-engineer.md) | reliability, monitoring, incident response, SLO | SLO/SLI, Alerting, Postmortem, Capacity Planning, Chaos Eng |

---

## ใช้ Agent ไหนดี? (Quick Guide)

```
อยากทำโปรโมชั่น / ลดราคา / Flash Sale
└─→ Campaign Planner

อยากโพสต์ content ลง social media
└─→ Content Creator

อยากเขียน listing สินค้าบน marketplace
└─→ Listing Optimizer

อยากรู้ว่าขายดีไหม / ยอดตกเพราะอะไร
└─→ Sales Analyst

อยากดูแลลูกค้าเก่า / เพิ่ม retention
└─→ CRM Manager

อยากเช็คสต็อก / สั่งของเพิ่ม
└─→ Inventory Manager

อยากจัดการ project / ติดตาม task
└─→ Project Coordinator

อยากตอบคำถามลูกค้า / จัดการ complaint
└─→ Customer Support

อยากดูแล community / กระตุ้น engagement
└─→ Community Manager

อยากวิเคราะห์กำไร-ขาดทุน / budget
└─→ Financial Analyst

อยากตั้งราคาสินค้าให้เหมาะสม
└─→ Pricing Strategist

อยากเขียน JD / สัมภาษณ์ / ออกนโยบาย
└─→ HR Advisor

อยากจัด training / พัฒนาทีม
└─→ Training Coordinator

อยากเขียน API / database / server-side logic
└─→ Backend Engineer

อยากสร้าง UI / component / หน้าเว็บ
└─→ Frontend Engineer

อยากทำ feature ครบทั้ง frontend + backend
└─→ Fullstack Engineer

อยาก setup CI/CD / deploy / จัดการ infrastructure
└─→ DevOps Engineer

อยากออกแบบ architecture / เลือก tech stack
└─→ System Architect

อยากวิเคราะห์ data / เขียน SQL / สร้าง dashboard
└─→ Data Analyst

อยากเขียน test / วาง test strategy / QA
└─→ QA Engineer

อยากสร้าง mobile app (iOS / Android)
└─→ Mobile Engineer

อยาก integrate AI / LLM / ML เข้า product
└─→ AI/ML Engineer

อยาก security review / pentest / fix vulnerability
└─→ Security Engineer

อยากเขียน API docs / guide / runbook
└─→ Technical Writer

อยากจัดการ reliability / SLO / incident response
└─→ SRE
```

---

## การทำงานร่วมกันระหว่าง Agent

บางสถานการณ์ต้องใช้หลาย agent ต่อกัน:

| สถานการณ์ | Flow |
|---|---|
| **ระบาย overstock** | Inventory Manager → Campaign Planner |
| **เปิดตัวสินค้าใหม่** | Pricing Strategist → Listing Optimizer → Content Creator → Campaign Planner |
| **ทบทวนประสิทธิภาพ** | Sales Analyst → Campaign Planner (ปรับ campaign) |
| **ดูแลลูกค้า end-to-end** | Customer Support → CRM Manager (follow-up) |
| **Onboard พนักงานใหม่** | HR Advisor → Training Coordinator |
| **วางแผนงบ marketing** | Financial Analyst → Campaign Planner |
| **Crisis management** | Community Manager → Customer Support (escalation) |
| **สร้าง feature ใหม่** | System Architect (design) → Backend Engineer (API) → Frontend Engineer (UI) → QA Engineer (test) → DevOps Engineer (deploy) |
| **Performance issue** | Data Analyst (identify) → Backend Engineer (optimize API/query) → DevOps Engineer (scale infra) |
| **Data-driven decision** | Data Analyst (analysis) → Sales Analyst (business insight) → Campaign Planner (action) |
| **Tech debt cleanup** | System Architect (prioritize) → Backend/Frontend Engineer (refactor) → QA Engineer (regression test) |

---

## โครงสร้างไฟล์

```
templates/
├── README.md                              ← คุณอยู่ที่นี่
├── _onboarding.md                         ← คู่มือ customize
├── marketing/
│   ├── campaign-planner.md
│   ├── content-creator.md
│   └── listing-optimizer.md
├── sales/
│   ├── sales-analyst.md
│   └── crm-manager.md
├── operations/
│   ├── inventory-manager.md
│   └── project-coordinator.md
├── customer-experience/
│   ├── customer-support.md
│   └── community-manager.md
├── finance/
│   ├── financial-analyst.md
│   └── pricing-strategist.md
├── hr/
│   ├── hr-advisor.md
│   └── training-coordinator.md
└── tech/
    ├── backend-engineer.md
    ├── frontend-engineer.md
    ├── fullstack-engineer.md
    ├── mobile-engineer.md
    ├── devops-engineer.md
    ├── sre-engineer.md
    ├── system-architect.md
    ├── data-analyst.md
    ├── ai-ml-engineer.md
    ├── qa-engineer.md
    ├── security-engineer.md
    └── technical-writer.md
```

---

## Template Structure (โครงสร้างของแต่ละ Agent)

ทุก agent template มีโครงสร้าง 9 ส่วน:

1. **Self-Configuration Questions** — คำถามที่ agent ถามเมื่อใช้ครั้งแรก
2. **เงื่อนไขการใช้งาน** — ใช้เมื่อไร / ไม่ควรใช้เมื่อไร
3. **Identity & Purpose** — ตัวตนและหน้าที่ (มี `[PLACEHOLDER]` ให้ customize)
4. **Core Skills** — ทักษะหลักของ agent
5. **Input Requirements** — ข้อมูลที่ต้องถามก่อนทำงาน
6. **Business Constraints** — กฎเหล็กที่ห้ามละเมิด
7. **Operational Framework** — ขั้นตอนการทำงาน
8. **Output Format** — รูปแบบ output มาตรฐาน
9. **Knowledge Base** — ข้อมูลเฉพาะธุรกิจ (เติมหลัง customize)
