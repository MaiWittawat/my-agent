# 🎯 Agent Onboarding Guide — วิธี Customize Agent ให้เข้ากับ Project ของคุณ

---

## วิธีใช้งาน

### Step 1: เลือก Agent ที่ต้องการ
เลือกจาก `README.md` ว่าต้องการ agent ตัวไหน แล้ว copy ไฟล์ `.md` ไปไว้ใน project ของคุณ

### Step 2: เปิดใช้งาน Agent ครั้งแรก
เมื่อเปิดใช้ agent ครั้งแรก agent จะถามชุดคำถาม **Self-Configuration Questions** เพื่อ customize ตัวเองให้เข้ากับธุรกิจของคุณ

### Step 3: Agent อัปเดตตัวเอง
หลังจากได้คำตอบ agent จะอัปเดตค่า `[PLACEHOLDER]` ทั้งหมดในไฟล์ให้ตรงกับธุรกิจจริง

### Step 4: พร้อมใช้งาน
agent ที่ customize แล้วจะทำงานเจาะจงกับ project ของคุณทันที

---

## โครงสร้าง Placeholder ที่ต้อง Customize

ทุก agent template จะมี placeholder เหล่านี้ที่ต้องกรอก:

| Placeholder | ความหมาย | ตัวอย่าง |
|---|---|---|
| `[BRAND_NAME]` | ชื่อแบรนด์/บริษัท | JK Tako-yaki Shoppu |
| `[INDUSTRY]` | ประเภทธุรกิจ | F&B, E-commerce, SaaS |
| `[AGENT_NAME]` | ชื่อของ agent | ไนซ์, มิ้นท์ |
| `[AGENT_GENDER]` | เพศของ agent | หญิง, ชาย, ไม่ระบุ |
| `[AGENT_PERSONALITY]` | บุคลิกของ agent | มั่นใจ ฉลาด มีพลัง |
| `[TARGET_AUDIENCE]` | กลุ่มเป้าหมาย | วัยรุ่น, วัยทำงาน |
| `[CHANNELS]` | ช่องทางที่ใช้ | Shopee, LINE, Facebook |
| `[PRODUCTS_SERVICES]` | สินค้า/บริการหลัก | แป้งทาโกะยากิ |
| `[CONSTRAINT_*]` | ข้อจำกัดทางธุรกิจ | Margin ≥ 30% |

---

## คำถามที่ Agent จะถามเมื่อเปิดใช้ครั้งแรก

Agent แต่ละตัวจะมี **Self-Configuration Questions** เฉพาะ แต่คำถามพื้นฐานที่ทุกตัวจะถามคือ:

1. **ชื่อแบรนด์/บริษัทคืออะไร?**
2. **ธุรกิจทำเกี่ยวกับอะไร? (สินค้า/บริการหลัก)**
3. **กลุ่มเป้าหมายคือใคร?**
4. **ใช้ช่องทางไหนบ้าง? (platform, social media, marketplace)**
5. **มีข้อจำกัดหรือกฎเหล็กอะไรที่ต้องรักษาเสมอ?**
6. **ต้องการให้ agent มีบุคลิกแบบไหน? (ชื่อ, เพศ, tone การพูด)**

---

## Tips

- **อย่าลบ Section โครงสร้าง** — แค่แทนที่ `[PLACEHOLDER]` ด้วยข้อมูลจริง
- **Knowledge Base** (Section 8) ควรอัปเดตเรื่อยๆ เมื่อมีข้อมูลใหม่
- **Business Constraints** (Section 4) สำคัญมาก — เป็นกฎเหล็กที่ agent จะไม่ละเมิด
- สามารถมี agent หลายตัวใน 1 project และให้ทำงานร่วมกันได้
