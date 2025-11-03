# Module 5: Preventing Data Leaks with Data Loss Prevention (DLP) Policies

## ภาพรวม

โมดูลนี้ครอบคลุม Data Loss Prevention (DLP) Policies ซึ่งเป็นเครื่องมือสำคัญในการป้องกันการเปิดเผยข้อมูลสำคัญขององค์กรโดยไม่ตั้งใจ ผู้เข้าร่วมจะได้เรียนรู้วิธีการทำงานของ DLP Policies โดยการจัดประเภท Connectors เป็น Business, Non-Business, และ Blocked groups กลยุทธ์ DLP แบบหลายชั้นจะถูกนำเสนอเป็นแนวทางที่แนะนำสำหรับการสร้างสมดุลระหว่าง Security และ Productivity

## เนื้อหา

### 1. How DLP Policies Work

#### ทฤษฎี

**Data Loss Prevention (DLP) Policies คืออะไร?**

DLP Policies เป็นกลไกควบคุมการไหลของข้อมูลระหว่าง Connectors ใน Power Platform เพื่อป้องกัน:
- การเปิดเผยข้อมูลสำคัญ (Data Exfiltration)
- การเชื่อมต่อที่ไม่ได้รับอนุญาตระหว่าง Services
- การใช้งาน Connectors ที่ไม่เหมาะสม

**Connector Groups:**

DLP Policies แบ่ง Connectors ออกเป็น 3 กลุ่ม:

1. **Business Group** (สีเขียว)
   - Connectors ที่ได้รับอนุญาตให้ใช้กับข้อมูลทางธุรกิจ
   - ตัวอย่าง: SharePoint, Microsoft 365, Dataverse, SQL Server

2. **Non-Business Group** (สีแดง)
   - Connectors สำหรับบริการส่วนตัวหรือภายนอก
   - ตัวอย่าง: Gmail, Twitter, Facebook, Personal OneDrive

3. **Blocked Group** (สีเทา)
   - Connectors ที่ถูก Block ไม่ให้ใช้งาน
   - ไม่สามารถใช้ใน Flows หรือ Apps ได้

**กฎการทำงาน:**

- Connectors ใน Business Group **สามารถ**ใช้งานร่วมกับ Connectors ใน Business Group อื่นได้
- Connectors ใน Non-Business Group **สามารถ**ใช้งานร่วมกับ Connectors ใน Non-Business Group อื่นได้
- Connectors ใน Business Group **ไม่สามารถ**ใช้งานร่วมกับ Connectors ใน Non-Business Group ได้ (Blocked)
- Connectors ใน Blocked Group **ไม่สามารถ**ใช้งานได้เลย

**ตัวอย่าง:**
- ✅ SharePoint + Dataverse = อนุญาต (Business + Business)
- ✅ Gmail + Twitter = อนุญาต (Non-Business + Non-Business)
- ❌ SharePoint + Gmail = Blocked (Business + Non-Business)

**อ้างอิง:**
- [Data Loss Prevention](https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention)

---

### 2. A Multi-Layered DLP Strategy

#### ทฤษฎี

**กลยุทธ์ DLP แบบหลายชั้น (Multi-Layered DLP Strategy):**

**ชั้นที่ 1: Tenant-Wide DLP Policy**
- นโยบายพื้นฐานสำหรับทั้ง Tenant
- ครอบคลุม Connectors ที่ใช้ทั่วไป
- ตั้งค่าเป็น Default สำหรับ Environments ใหม่
- มักจะเข้มงวด (Strict)

**ชั้นที่ 2: Environment-Specific DLP Policies**
- นโยบายเฉพาะสำหรับ Environment แต่ละตัว
- ยืดหยุ่นตามความต้องการของแต่ละ Environment
- Override หรือ Supplement Tenant Policy
- ตัวอย่าง:
  - Production Environment: เข้มงวด
  - Development Environment: ผ่อนปรนกว่า

**ชั้นที่ 3: Department/Team-Specific Policies**
- นโยบายสำหรับทีมหรือแผนกเฉพาะ
- ใช้ Environment-Specific Policies
- ตัวอย่าง:
  - Finance Environment: Block Social Media Connectors
  - Marketing Environment: อนุญาต Social Media แต่ Block Finance Connectors

**Best Practices:**

1. **เริ่มจาก Tenant-Wide Policy**
   - สร้าง Baseline ที่ปลอดภัย
   - ครอบคลุม Connectors หลัก

2. **เพิ่ม Environment-Specific Policies เมื่อจำเป็น**
   - ไม่ควรสร้างมากเกินไป
   - แต่ละ Policy ควรมีเหตุผลที่ชัดเจน

3. **Documentation**
   - บันทึกเหตุผลของแต่ละ Policy
   - บันทึกการยกเว้น (Exceptions)

4. **Regular Review**
   - ทบทวน Policies เป็นประจำ
   - อัปเดตตาม Connectors ใหม่

**อ้างอิง:**
- [Data Loss Prevention Policies](https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention)

---

### 3. Applying DLP Policies

#### ทฤษฎี

**วิธีการสร้างและใช้ DLP Policies:**

**1. สร้าง DLP Policy**
- กำหนดชื่อและประเภท (Tenant/Environment)
- จัดกลุ่ม Connectors
- บันทึก Policy

**2. Scope Policies**
- Tenant-Wide: ใช้กับ Environments ทั้งหมด
- Environment-Specific: ใช้กับ Environment เฉพาะ

**3. Policy Priority**
- Environment-Specific Policy Override Tenant Policy
- ใช้ Environment-Specific Policy เมื่อมี Conflict

**4. Testing**
- ทดสอบ Policy ก่อนใช้งานจริง
- ตรวจสอบว่า Flow/App ที่มีอยู่ยังทำงานได้
- แจ้งผู้ใช้เกี่ยวกับการเปลี่ยนแปลง

**5. Monitoring**
- ติดตาม Policy Violations
- ตรวจสอบ Audit Logs
- ทบทวนและปรับปรุง

**อ้างอิง:**
- [Create DLP Policy](https://learn.microsoft.com/en-us/power-platform/admin/create-dlp-policy)

---

## สรุป Module 5

### จุดสำคัญที่ควรจำ

1. **DLP Policies ป้องกัน Data Leaks** - โดยควบคุมการเชื่อมต่อระหว่าง Connectors

2. **กลยุทธ์ Multi-Layered มีประสิทธิภาพ** - การใช้ Tenant-Wide และ Environment-Specific Policies ร่วมกัน

3. **การทดสอบสำคัญ** - ทดสอบ Policy ก่อนใช้งานจริงเพื่อหลีกเลี่ยงผลกระทบที่ไม่คาดคิด

### คำถามทบทวน

1. Connector Groups ทั้ง 3 กลุ่มมีอะไรบ้าง และทำงานอย่างไร?
2. ทำไมกลยุทธ์ Multi-Layered DLP จึงมีประสิทธิภาพ?
3. ควรทดสอบ DLP Policy อย่างไรก่อนใช้งานจริง?

### ขั้นตอนถัดไป

- เตรียมความพร้อมสำหรับ Module 6: Proactive Monitoring & Tenant-Wide Analytics
- ทบทวน DLP Policies ที่มีอยู่ใน Organization
- วางแผน Multi-Layered DLP Strategy สำหรับ Environment ต่างๆ

