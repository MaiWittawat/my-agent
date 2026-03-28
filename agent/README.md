# AI Agent Library — คู่มือ Agent ทั้งหมด

Agent templates กลางที่ออกแบบมาให้หยิบไปใช้ได้กับทุก project
Copy agent ที่ต้องการ → เปิดใช้ครั้งแรก → agent ถามคำถามเพื่อ customize ตัวเอง → พร้อมทำงาน

> ดูคู่มือ customize ที่ [templates/_onboarding.md](templates/_onboarding.md)

---

## สารบัญทุก Agent (25 ตัว / 7 แผนก)

| # | แผนก | จำนวน |
|---|---|---|
| 1 | [Marketing](#-marketing-การตลาด) | 3 |
| 2 | [Sales](#-sales-การขายและวิเคราะห์) | 2 |
| 3 | [Operations](#️-operations-ปฏิบัติการ) | 2 |
| 4 | [Customer Experience](#-customer-experience-ลูกค้าสัมพันธ์) | 2 |
| 5 | [Finance](#-finance-การเงิน) | 2 |
| 6 | [HR](#-hr-ทรัพยากรบุคคล) | 2 |
| 7 | [Tech](#-tech-เทคโนโลยี) | 12 |

---

## 🎯 Marketing (การตลาด)

### Campaign Planner — นักวางแผนแคมเปญ
📁 [templates/marketing/campaign-planner.md](templates/marketing/campaign-planner.md)

**ทำอะไรได้:**
- วางแผน Flash Sale, Promotion, Bundle Deal, Double Day Campaign
- คำนวณราคา campaign ที่ดึงดูดแต่ยังรักษา margin
- เขียน copywriting โฆษณาแยกตาม channel (Facebook, LINE, TikTok ฯลฯ)
- วาง Campaign Calendar รายเดือน
- ประมาณการ ROI และ KPI เป้าหมาย
- ออกแบบ bundle deal และ cross-sell strategy

**Skills:** Pricing Strategy · Urgency Marketing · Campaign Calendar · Channel-Specific Copywriting · Bundle Design · ROI Forecasting

---

### Content Creator — นักสร้าง Content
📁 [templates/marketing/content-creator.md](templates/marketing/content-creator.md)

**ทำอะไรได้:**
- สร้าง content สำหรับ TikTok, Facebook, IG, LINE OA, X
- เขียน script วิดีโอ พร้อม storyboard แต่ละ scene
- เขียน caption ปรับ tone ตามแต่ละ platform
- วาง hashtag strategy (broad / niche / brand)
- แนะนำ visual direction, มุมกล้อง, color tone
- นำ trend มาปรับใช้กับแบรนด์

**Skills:** Platform-Native Content · Hook Writing · Storytelling · Hashtag Strategy · Trend Hijacking · Visual Direction

---

### Listing Optimizer — นักเขียน Product Listing
📁 [templates/marketing/listing-optimizer.md](templates/marketing/listing-optimizer.md)

**ทำอะไรได้:**
- เขียนชื่อสินค้าที่ติดอันดับค้นหาบน Shopee, Lazada, TikTok Shop, Amazon
- วิจัย keyword (primary, secondary, long-tail) สำหรับแต่ละ platform
- เขียน product description / bullet points ที่ตอบ pain point ลูกค้า
- แนะนำ category และ attribute ที่ถูกต้อง
- วิเคราะห์ listing คู่แข่ง
- เสนอ A/B testing variant

**Skills:** Marketplace SEO · Title Optimization · Description Writing · Category Tagging · Competitive Analysis · A/B Testing

---

## 📊 Sales (การขายและวิเคราะห์)

### Sales Analyst — นักวิเคราะห์ยอดขาย
📁 [templates/sales/sales-analyst.md](templates/sales/sales-analyst.md)

**ทำอะไรได้:**
- วิเคราะห์ยอดขายรายวัน/สัปดาห์/เดือน แยกตามสินค้าและ platform
- จัดอันดับสินค้า top/bottom ตาม revenue, units, growth
- เปรียบเทียบ ROI ของแต่ละ channel
- หา pattern, seasonal trend, anomaly
- วิเคราะห์ cohort ลูกค้า
- หาสาเหตุเมื่อยอดขายตก/พุ่งผิดปกติ
- เสนอ action items เรียงตาม priority

**Skills:** Performance Analysis · Product Ranking · Channel Efficiency · Trend Detection · Cohort Analysis · Actionable Recommendation

---

### CRM Manager — นักจัดการลูกค้าสัมพันธ์
📁 [templates/sales/crm-manager.md](templates/sales/crm-manager.md)

**ทำอะไรได้:**
- แบ่งกลุ่มลูกค้า (VIP / Active / At-risk / Dormant)
- วาง customer lifecycle touchpoints
- ออกแบบ re-engagement campaign ดึงลูกค้าที่หายไปกลับมา
- คำนวณ Customer Lifetime Value (CLV)
- ออกแบบ loyalty / referral program
- เขียนข้อความ personalized สำหรับแต่ละ segment

**Skills:** Customer Segmentation · Lifecycle Marketing · Retention Strategy · Re-engagement · CLV Analysis · Personalized Messaging

---

## ⚙️ Operations (ปฏิบัติการ)

### Inventory Manager — นักจัดการสต็อก
📁 [templates/operations/inventory-manager.md](templates/operations/inventory-manager.md)

**ทำอะไรได้:**
- ติดตามสถานะสต็อกสินค้าทุกรายการ
- คำนวณ Reorder Point และปริมาณที่ควรสั่งซื้อ
- แจ้งเตือนสินค้าใกล้หมดอายุ (FEFO)
- ระบุ overstock พร้อมแนวทางระบาย
- วางแผนสั่งซื้อล่วงหน้าตาม promotion/season
- ประมาณการ demand จากข้อมูลอดีต

**Skills:** Stock Monitoring · Reorder Calculation · Expiry Management · Overstock Detection · Purchase Planning · Demand Forecasting

---

### Project Coordinator — ผู้ประสานงานโปรเจค
📁 [templates/operations/project-coordinator.md](templates/operations/project-coordinator.md)

**ทำอะไรได้:**
- แตก project ใหญ่เป็น task ย่อย (Work Breakdown Structure)
- จัดลำดับความสำคัญด้วย Eisenhower / MoSCoW
- วาง timeline / Gantt chart พร้อม dependencies
- มอบหมายงาน ติดตาม progress
- เตรียม meeting agenda และสรุป action items
- ระบุ risk พร้อมแผนรับมือ
- สร้าง status report สำหรับทีม

**Skills:** Task Breakdown · Priority Matrix · Timeline Management · Status Reporting · Risk Identification · Meeting Facilitation

---

## 💬 Customer Experience (ลูกค้าสัมพันธ์)

### Customer Support — ฝ่ายดูแลลูกค้า
📁 [templates/customer-experience/customer-support.md](templates/customer-experience/customer-support.md)

**ทำอะไรได้:**
- ตอบคำถามลูกค้าเกี่ยวกับสินค้า/บริการ
- จัดการ complaint ด้วย empathy + solution
- Draft ข้อความตอบกลับปรับ tone ตาม channel
- สร้าง FAQ / Knowledge Base สำหรับทีม
- กำหนด escalation guideline (เมื่อไรต้องส่งต่อ)
- วิเคราะห์ปัญหาที่เกิดบ่อยเพื่อป้องกัน

**Skills:** FAQ & Knowledge Base · Complaint Resolution · Response Drafting · Escalation Management · Tone Matching · Policy Application

---

### Community Manager — ผู้ดูแล Community
📁 [templates/customer-experience/community-manager.md](templates/customer-experience/community-manager.md)

**ทำอะไรได้:**
- วางแผน engagement activity รายสัปดาห์
- ตอบ comment / DM ด้วย brand voice สม่ำเสมอ
- กระตุ้นและคัดเลือก user-generated content (UGC)
- จัดการ crisis communication เมื่อเกิด negative viral
- วาง community growth strategy
- อ่าน sentiment ของ community

**Skills:** Engagement Strategy · Comment/DM Management · UGC Curation · Crisis Communication · Community Growth · Sentiment Monitoring

---

## 💰 Finance (การเงิน)

### Financial Analyst — นักวิเคราะห์การเงิน
📁 [templates/finance/financial-analyst.md](templates/finance/financial-analyst.md)

**ทำอะไรได้:**
- วิเคราะห์ กำไร-ขาดทุน (P&L) แยกตาม period
- Forecast revenue และ expenses
- วิเคราะห์ cost structure หาจุด optimize
- คำนวณ break-even สำหรับ product/project ใหม่
- วิเคราะห์ cash flow
- วางแผน budget รายเดือน/ไตรมาส/ปี

**Skills:** P&L Analysis · Revenue Forecasting · Cost Optimization · Break-even Analysis · Cash Flow Management · Budget Planning

---

### Pricing Strategist — นักวางกลยุทธ์ราคา
📁 [templates/finance/pricing-strategist.md](templates/finance/pricing-strategist.md)

**ทำอะไรได้:**
- กำหนดราคาสินค้า/บริการใหม่ (cost-plus, value-based, competitive)
- Review ราคาปัจจุบันว่าเหมาะสมไหม
- วิเคราะห์ price elasticity
- ออกแบบ pricing tier / subscription pricing
- เปรียบเทียบราคากับคู่แข่ง
- จำลองสถานการณ์ what-if (ราคาสูง/ต่ำ → ผลกระทบ)
- คำนวณ platform fee เข้าไปในต้นทุน

**Skills:** Cost-Plus Pricing · Value-Based Pricing · Competitive Pricing · Price Elasticity · Tier/Bundle Design · Margin Optimization

---

## 👥 HR (ทรัพยากรบุคคล)

### HR Advisor — ที่ปรึกษา HR
📁 [templates/hr/hr-advisor.md](templates/hr/hr-advisor.md)

**ทำอะไรได้:**
- เขียน Job Description (JD) ที่ชัดเจนและดึงดูด
- ออกแบบคำถามสัมภาษณ์ตาม competency
- วาง onboarding process สำหรับพนักงานใหม่
- ออกแบบ performance review framework
- ร่างนโยบาย HR (ลา, สวัสดิการ, probation)
- เสนอกลยุทธ์ employee engagement

**Skills:** JD Writing · Interview Design · Onboarding Design · Performance Review · Policy Drafting · Employee Engagement

---

### Training Coordinator — ผู้ประสานงาน Training
📁 [templates/hr/training-coordinator.md](templates/hr/training-coordinator.md)

**ทำอะไรได้:**
- วิเคราะห์ skill gap ของทีม
- วาง learning path สำหรับแต่ละ role/level
- ออกแบบ training program ตั้งแต่ objective ถึง evaluation
- วางแผน workshop: agenda, activities, materials
- ร่างโครงสร้างเนื้อหา training
- วัดผล training ด้วย Kirkpatrick model (Reaction → Learning → Behavior → Results)

**Skills:** Skill Gap Analysis · Learning Path Design · Training Program Design · Workshop Facilitation · Content Outline · ROI Measurement

---

## 💻 Tech (เทคโนโลยี)

### Backend Engineer — วิศวกร Backend
📁 [templates/tech/backend-engineer.md](templates/tech/backend-engineer.md)

**ทำอะไรได้:**
- ออกแบบและ implement API endpoints (REST, GraphQL, gRPC)
- ออกแบบ database schema, เขียน migration, optimize query
- Implement business logic ที่ซับซ้อน
- Implement authentication & authorization (JWT, OAuth2, RBAC)
- เชื่อมต่อ third-party API, payment gateway, external services
- เขียน background job, worker, queue consumer
- จัดการ error อย่างเป็นระบบ (custom errors, logging, retry)
- Optimize query performance, fix N+1 problems, implement caching
- ป้องกัน SQL injection, auth bypass, IDOR, mass assignment
- เขียน unit test, integration test สำหรับ API + service layer

**Skills:** API Development · Database Design · Auth · Business Logic · Integration · Background Jobs · Error Handling · Performance · Security · Testing

---

### Frontend Engineer — วิศวกร Frontend
📁 [templates/tech/frontend-engineer.md](templates/tech/frontend-engineer.md)

**ทำอะไรได้:**
- สร้าง reusable UI components ที่มี typed props API ชัดเจน
- สร้าง layout ที่ responsive ทุก screen size (mobile-first)
- จัดการ state management (local, global, server state)
- Integrate กับ API — handle loading, error, empty, success states
- สร้าง form ที่ซับซ้อน (multi-step, dynamic fields, validation)
- เพิ่ม animation / micro-interactions ที่ช่วย UX
- Optimize rendering, bundle size, lazy loading, code splitting
- สร้าง UI ที่ accessible (keyboard nav, screen reader, ARIA)
- เขียน component test, integration test, e2e test
- ใช้ TypeScript อย่างเต็มที่ — type props, API responses, form data

**Skills:** Component Development · Responsive Layout · State Management · API Integration · Forms · Animation · Performance · Accessibility · Testing · Type Safety

---

### Fullstack Engineer — วิศวกร Fullstack
📁 [templates/tech/fullstack-engineer.md](templates/tech/fullstack-engineer.md)

**ทำอะไรได้:**
- Implement feature ครบทั้ง frontend + backend ใน PR เดียว
- สร้าง full CRUD ตั้งแต่ UI → API → Database
- ออกแบบ API contract ก่อนแล้ว implement ทั้งสองฝั่ง
- Implement auth flow ครบ (login, register, protected routes)
- Form UI + client validation + server validation
- จัดการ error handling ข้าม layer (API errors → user-friendly UI)
- เหมาะสำหรับทีมเล็กที่คนเดียวดูแลทั้ง stack
- สร้าง prototype / MVP ที่ทำงานได้ end-to-end

**Skills:** API-First Development · Full CRUD · Auth · Cross-Layer Error Handling · Shared Types · End-to-End Testing

> **เมื่อไรใช้ Fullstack vs. Backend+Frontend แยก?**
> - ทีมเล็ก / MVP / feature ง่ายๆ → **Fullstack**
> - ทีมใหญ่ / งานเจาะลึก / ต้องการ expertise เฉพาะทาง → **Backend + Frontend แยก**

---

### DevOps Engineer — วิศวกร DevOps
📁 [templates/tech/devops-engineer.md](templates/tech/devops-engineer.md)

**ทำอะไรได้:**
- ออกแบบและ optimize CI/CD pipeline
- เขียน Infrastructure as Code (Terraform, Pulumi, CloudFormation)
- Containerize applications (Docker, Kubernetes)
- Setup monitoring, alerting, logging (Datadog, Grafana, CloudWatch)
- Security hardening (IAM, network, secrets management)
- Auto-scaling, load balancing, disaster recovery
- วิเคราะห์และ optimize cloud costs
- จัดการ production incident อย่างเป็นระบบ

**Skills:** CI/CD Pipeline · IaC · Containerization · Monitoring & Alerting · Security Hardening · Scaling · Cost Optimization · Incident Response

---

### System Architect — สถาปนิกระบบ
📁 [templates/tech/system-architect.md](templates/tech/system-architect.md)

**ทำอะไรได้:**
- ออกแบบ system architecture (monolith, microservices, serverless)
- ออกแบบ API ที่ consistent, versioned, well-documented
- ออกแบบ data model, storage strategy, data flow
- เลือก integration pattern (sync/async, event-driven, CQRS)
- วิเคราะห์ trade-offs ระหว่าง options อย่างเป็นระบบ
- Capacity planning สำหรับ growth
- ประเมินและเลือก technology stack
- วาง migration plan แบบ incremental

**Skills:** System Design · API Design · Data Modeling · Integration Patterns · Trade-off Analysis · Scalability Planning · Tech Evaluation · Migration Planning

---

### Data Analyst — นักวิเคราะห์ข้อมูล
📁 [templates/tech/data-analyst.md](templates/tech/data-analyst.md)

**ทำอะไรได้:**
- เขียน SQL query ที่ performant และ readable
- ออกแบบและสร้าง ETL/ELT data pipeline
- ออกแบบ dimensional model (star/snowflake schema)
- วิเคราะห์ข้อมูลเชิงสถิติ (distributions, correlations, significance)
- ออกแบบ dashboard ที่ตอบ business questions
- ตรวจสอบและรักษา data quality
- วิเคราะห์ผล A/B test อย่างถูกต้องทางสถิติ
- เขียน data dictionary, lineage documentation

**Skills:** SQL & Query Optimization · Data Pipeline · Data Modeling · Statistical Analysis · Dashboard Design · Data Quality · A/B Test Analysis · Data Documentation

---

### QA Engineer — วิศวกรทดสอบ
📁 [templates/tech/qa-engineer.md](templates/tech/qa-engineer.md)

**ทำอะไรได้:**
- ออกแบบ test strategy ที่ครอบคลุม (happy path + edge cases + negative)
- เขียน test cases ด้วย boundary analysis, equivalence partitioning, decision table
- เขียน automated tests (unit, integration, e2e)
- ทดสอบ API (functional, contract, load)
- ออกแบบและรัน performance test / load test
- เขียน bug report ที่ชัดเจน reproduce ได้
- วาง regression suite สำหรับ critical paths
- Basic security testing (injection, auth bypass, XSS)

**Skills:** Test Planning · Test Case Design · Test Automation · API Testing · Performance Testing · Bug Reporting · Regression Testing · Security Testing

---

### Mobile Engineer — วิศวกร Mobile
📁 [templates/tech/mobile-engineer.md](templates/tech/mobile-engineer.md)

**ทำอะไรได้:**
- สร้าง mobile app screen / feature (iOS, Android, cross-platform)
- Implement native functionality (camera, GPS, biometrics, push notifications)
- Implement navigation flow (stack, tab, drawer, deep link)
- Handle offline mode / local caching / sync strategy
- Integrate กับ backend API จาก mobile (connectivity, retry, timeout)
- Optimize app performance (startup time, memory, battery usage)
- ปฏิบัติตาม HIG (iOS) / Material Design (Android) guidelines
- เตรียม app สำหรับ App Store / Play Store submission

**Skills:** Screen Development · Native Features · Navigation · Offline Support · Push Notifications · Performance · Platform Guidelines · App Store Deployment

---

### AI/ML Engineer — วิศวกร AI/ML
📁 [templates/tech/ai-ml-engineer.md](templates/tech/ai-ml-engineer.md)

**ทำอะไรได้:**
- Integrate LLM เข้า product (prompt engineering, RAG, function calling, agents)
- ออกแบบ prompt ที่ได้ผลลัพธ์แม่นยำ สม่ำเสมอ ปลอดภัย
- สร้าง RAG pipeline (chunking, embedding, vector store, retrieval, reranking)
- Build ML pipeline (data prep → training → evaluation → deployment)
- เลือก model ที่เหมาะกับ task (cost vs. quality vs. latency)
- Fine-tune model สำหรับ domain-specific tasks
- ออกแบบ evaluation framework (automated metrics + human eval)
- Optimize AI cost (caching, prompt optimization, model routing)
- AI safety (content filtering, hallucination detection, PII protection)

**Skills:** LLM Integration · Prompt Engineering · RAG · ML Pipeline · Model Selection · Fine-tuning · Evaluation · Cost Optimization · AI Safety

---

### Security Engineer — วิศวกรความปลอดภัย
📁 [templates/tech/security-engineer.md](templates/tech/security-engineer.md)

**ทำอะไรได้:**
- Threat modeling (STRIDE/DREAD) — ระบุ threats, attack vectors, trust boundaries
- Security code review ตรวจ OWASP Top 10 + business logic flaws
- ออกแบบ authentication & authorization ที่ปลอดภัย (MFA, RBAC, ABAC)
- ป้องกัน injection ทุกรูปแบบ (SQL, XSS, Command, SSRF, Path Traversal)
- เลือกใช้ encryption, hashing, signing อย่างถูกต้อง
- API security (rate limiting, CORS, API key management)
- Penetration testing ตาม OWASP methodology
- สร้าง incident response playbook
- Compliance mapping (PDPA, GDPR, SOC2, PCI-DSS)

**Skills:** Threat Modeling · Security Code Review · Auth Design · Input Validation · Cryptography · API Security · Penetration Testing · Incident Response · Compliance

---

### Technical Writer — นักเขียนเทคนิค
📁 [templates/tech/technical-writer.md](templates/tech/technical-writer.md)

**ทำอะไรได้:**
- เขียน API documentation พร้อม examples ที่ copy-paste ได้
- เขียน Getting Started / Quick Start guide
- เขียน Architecture Decision Record (ADR)
- เขียน Runbook / Playbook สำหรับ operations
- เขียน User guide / Help docs
- เขียน Changelog / Release notes
- เขียน Onboarding docs สำหรับ developer ใหม่
- สร้าง architecture diagram, flow chart (Mermaid)

**Skills:** API Documentation · Getting Started Guide · Architecture Docs · Runbooks · User Guides · Release Notes · Code Documentation · Diagrams

---

### SRE (Site Reliability Engineer) — วิศวกรความน่าเชื่อถือ
📁 [templates/tech/sre-engineer.md](templates/tech/sre-engineer.md)

**ทำอะไรได้:**
- กำหนด SLO/SLI/Error Budget ที่ measurable
- Setup monitoring & alerting ที่ actionable (ไม่ alert spam)
- Lead incident response: detect → triage → mitigate → resolve
- เขียน blameless postmortem พร้อม action items
- Capacity planning + auto-scaling strategy
- Implement reliability patterns (circuit breaker, retry, failover, graceful degradation)
- ออกแบบ chaos engineering experiments
- สร้าง on-call runbooks + optimize alert quality
- ลด MTTR (Mean Time to Recovery)

**Skills:** SLO/SLI/Error Budget · Monitoring & Alerting · Incident Management · Postmortem · Capacity Planning · Reliability Patterns · Chaos Engineering · On-Call Optimization

> **SRE vs. DevOps:** DevOps เน้น build & deploy (CI/CD + infra). SRE เน้น keep it running (monitoring, SLO, incident, postmortem).

---

## ใช้ Agent ไหนดี? (Quick Guide)

```
╔══════════════════════════════════════════════════════════════╗
║  อยากทำอะไร?                              → ใช้ตัวไหน       ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  — Marketing —                                               ║
║  ทำโปรโมชั่น / Flash Sale / Bundle        → Campaign Planner ║
║  โพสต์ content ลง social media            → Content Creator  ║
║  เขียน listing บน marketplace             → Listing Optimizer║
║                                                              ║
║  — Sales —                                                   ║
║  วิเคราะห์ยอดขาย / หาสาเหตุยอดตก        → Sales Analyst    ║
║  ดูแลลูกค้าเก่า / เพิ่ม retention         → CRM Manager     ║
║                                                              ║
║  — Operations —                                              ║
║  เช็คสต็อก / สั่งของ / ของใกล้หมดอายุ    → Inventory Manager║
║  จัดการ project / ติดตาม task             → Project Coord.   ║
║                                                              ║
║  — Customer Experience —                                     ║
║  ตอบลูกค้า / จัดการ complaint             → Customer Support ║
║  ดูแล community / กระตุ้น engagement      → Community Manager║
║                                                              ║
║  — Finance —                                                 ║
║  วิเคราะห์กำไร-ขาดทุน / budget           → Financial Analyst║
║  ตั้งราคาสินค้า / เปรียบเทียบคู่แข่ง      → Pricing Strategist║
║                                                              ║
║  — HR —                                                      ║
║  เขียน JD / สัมภาษณ์ / นโยบาย            → HR Advisor       ║
║  จัด training / พัฒนาทีม                 → Training Coord.  ║
║                                                              ║
║  — Tech —                                                    ║
║  เขียน API / database / server logic      → Backend Engineer ║
║  สร้าง UI / component / หน้าเว็บ          → Frontend Engineer║
║  ทำ feature ครบทั้ง stack (UI+API+DB)      → Fullstack Eng.  ║
║  CI/CD / deploy / infrastructure          → DevOps Engineer  ║
║  ออกแบบ architecture / เลือก stack        → System Architect ║
║  วิเคราะห์ data / SQL / dashboard         → Data Analyst     ║
║  เขียน test / QA / automation             → QA Engineer      ║
║  สร้าง mobile app (iOS/Android)           → Mobile Engineer  ║
║  integrate AI / LLM / ML                  → AI/ML Engineer   ║
║  security review / pentest / compliance   → Security Engineer║
║  เขียน API docs / guide / runbook         → Technical Writer ║
║  SLO / monitoring / incident response     → SRE              ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

## Cross-Team Workflows

บางสถานการณ์ต้องใช้หลาย agent ต่อกัน:

### Business Workflows
| สถานการณ์ | Flow |
|---|---|
| ระบาย overstock | Inventory Manager → Campaign Planner |
| เปิดตัวสินค้าใหม่ | Pricing Strategist → Listing Optimizer → Content Creator → Campaign Planner |
| ทบทวนประสิทธิภาพ | Sales Analyst → Campaign Planner (ปรับ campaign) |
| ดูแลลูกค้า end-to-end | Customer Support → CRM Manager (follow-up) |
| วางแผนงบ marketing | Financial Analyst → Campaign Planner |
| Crisis management | Community Manager → Customer Support (escalation) |
| Onboard พนักงานใหม่ | HR Advisor → Training Coordinator |

### Tech Workflows
| สถานการณ์ | Flow |
|---|---|
| สร้าง feature ใหม่ | System Architect → Backend Engineer (API) → Frontend Engineer (UI) → QA Engineer → DevOps Engineer |
| MVP / Prototype | System Architect (design) → Fullstack Engineer (implement ทั้ง stack) → QA Engineer |
| Performance issue | Data Analyst (identify) → Backend Engineer (optimize API/query) → DevOps Engineer (scale) |
| Data-driven decision | Data Analyst → Sales Analyst → Campaign Planner |
| Tech debt cleanup | System Architect (prioritize) → Backend/Frontend Engineer (refactor) → QA Engineer (regression) |
| Production incident | SRE (detect & triage) → Backend/Frontend Engineer (fix) → QA Engineer (verify) → SRE (postmortem) |
| Mobile app launch | System Architect → Mobile Engineer (implement) → QA Engineer (test) → DevOps Engineer (CI/CD) |
| เพิ่ม AI feature | AI/ML Engineer (design + prototype) → Backend Engineer (integrate API) → Frontend Engineer (UI) |
| Security audit | Security Engineer (threat model + pentest) → Backend/Frontend Engineer (fix) → Security Engineer (verify) |
| เขียน docs | Technical Writer + Backend Engineer (review accuracy) |
| Define SLO | SRE + System Architect + Product team |

---

## โครงสร้างไฟล์

```
agent/
├── README.md                                ← คุณอยู่ที่นี่
└── templates/
    ├── _onboarding.md                       ← คู่มือ customize agent
    ├── README.md                            ← index สั้นๆ
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

## วิธีใช้งาน

1. **เลือก** agent ที่ต้องการจากรายการด้านบน
2. **Copy** ไฟล์ `.md` ไปยัง project ของคุณ
3. **เปิดใช้ครั้งแรก** → agent จะถามชุดคำถามเพื่อ customize ตัวเอง
4. **ตอบคำถาม** → agent อัปเดต `[PLACEHOLDER]` ทั้งหมดให้ตรงกับธุรกิจ
5. **พร้อมใช้** → agent ทำงานเจาะจงกับ project ของคุณ

> ดูรายละเอียดเพิ่มเติมที่ [templates/_onboarding.md](templates/_onboarding.md)
