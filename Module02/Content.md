# Module 2: Designing a Scalable Environment Architecture

## ภาพรวม

โมดูลนี้มุ่งเน้นที่การสร้างกลยุทธ์ Environment ที่แข็งแกร่ง ซึ่งเป็นรากฐานสำคัญของการกำกับดูแลที่มีประสิทธิภาพและการจัดการ Application Lifecycle Management (ALM) เราจะอภิปรายวิธีออกแบบสถาปัตยกรรมที่สนับสนุนความต้องการทางธุรกิจในขณะที่รักษาความปลอดภัยของทรัพย์สิน การจัดการ Default Environment ที่เหมาะสมเป็นจุดโฟกัสสำคัญเพื่อลดความเสี่ยงที่พบบ่อย

## เนื้อหา

### 1. การกำหนดกลยุทธ์สภาพแวดล้อม (Environment Strategy)

#### ทฤษฎี

Environment Strategy ที่ดีควรตอบสนองต่อความต้องการทางธุรกิจและรองรับการเติบโตในอนาคต

**ประเภทของ Environments:**

**Personal Productivity Environments**
- สำหรับการทดลองส่วนตัวและการเรียนรู้
- ผู้ใช้สามารถสร้าง Apps และ Flows ของตนเอง
- ไม่ควรเก็บข้อมูลสำคัญทางธุรกิจ
- ตัวอย่าง: Default Environment (ถ้าไม่ได้ใช้สำหรับการผลิต)

**Departmental Environments**
- สำหรับทีมหรือแผนกเฉพาะ
- แบ่งปันทรัพยากรร่วมกันภายในแผนก
- ตัวอย่าง: HR Environment, Finance Environment

**Application-Specific ALM Environments**
- สำหรับ Application Lifecycle Management
- มักมี 3 สภาพแวดล้อม: Development, Test/UAT, Production
- รองรับการ Deploy แบบ Professional
- ตัวอย่าง: CRM Dev, CRM Test, CRM Prod

**Shared Production Environments**
- สำหรับแอปพลิเคชันหลายตัวที่ใช้งานร่วมกัน
- ต้องมีการจัดการ Security และ Governance ที่เข้มงวด
- ตัวอย่าง: Corporate Apps Production

**อ้างอิง:** 
- [Environment Management Capabilities](https://learn.microsoft.com/en-us/power-platform/admin/environments-overview)
- [Create and Manage Environments](https://learn.microsoft.com/en-us/power-platform/admin/environments-overview)

---

### 2. การจัดการ Default Environment

#### ทฤษฎี

Default Environment เป็น Environment พิเศษที่:
- สร้างโดยอัตโนมัติสำหรับทุกองค์กร
- ทุกคนใน Tenant สามารถเข้าถึงได้ (ถ้าไม่มีการจำกัด)
- มักถูกใช้เป็นที่เก็บ Personal Productivity Apps
- เป็นความเสี่ยงด้าน Security หากไม่มีการจัดการที่เหมาะสม

**Best Practices:**

1. **Rename Default Environment**
   - เปลี่ยนชื่อให้สื่อความหมาย เช่น "Personal Productivity"
   - ช่วยลดความสับสนและสื่อถึงวัตถุประสงค์

2. **Restrict Access**
   - จำกัดการเข้าถึงผ่าน Microsoft Entra ID Security Groups
   - อนุญาตเฉพาะผู้ใช้ที่จำเป็นเท่านั้น

3. **Apply DLP Policies**
   - ใช้ DLP Policy ที่เข้มงวดสำหรับ Default Environment
   - ป้องกันการเชื่อมต่อกับระบบภายนอกที่เสี่ยง

4. **Regular Cleanup**
   - ตรวจสอบและลบ Resources ที่ไม่ใช้งาน
   - ใช้ Analytics เพื่อหา Orphaned Resources

5. **Documentation**
   - บันทึกนโยบายการใช้งาน Default Environment
   - สื่อสารกับผู้ใช้เกี่ยวกับขีดจำกัดและข้อกำหนด

**อ้างอิง:** [Default Environment](https://learn.microsoft.com/en-us/power-platform/admin/environments-overview#default-environment)

---

### 3. Environment Creation and Security

#### ทฤษฎี

การสร้าง Environment ใหม่และรักษาความปลอดภัยมีความสำคัญต่อการกำกับดูแล

**กระบวนการสร้าง Environment:**

1. **Planning**
   - กำหนดวัตถุประสงค์และขอบเขต
   - เลือก Type (Production, Sandbox, Trial)
   - เลือก Region
   - กำหนด Capacity Limits

2. **Creation**
   - สร้างผ่าน PPAC หรือ PowerShell
   - ตั้งชื่อตาม Naming Convention
   - เลือก Environment Type

3. **Security Configuration**
   - กำหนด Security Groups ที่สามารถเข้าถึงได้
   - สร้างหรือกำหนด Security Roles
   - ตั้งค่า DLP Policies

4. **Initial Setup**
   - เพิ่ม Dataverse (ถ้าจำเป็น)
   - สร้าง Business Units (ถ้าจำเป็น)
   - ตั้งค่า Environment Variables

**Security Groups:**
- ใช้ Microsoft Entra ID Security Groups เพื่อควบคุมการเข้าถึง
- แนะนำให้ใช้ Group-based Assignment แทนการ Assign แบบ Individual
- สร้าง Groups แยกตาม Role (Admin, Maker, User)

**อ้างอิง:**
- [Create Environment](https://learn.microsoft.com/en-us/power-platform/admin/create-environment)
- [Security Groups](https://learn.microsoft.com/en-us/power-platform/admin/control-user-access)

---

## สรุป Module 2

### จุดสำคัญที่ควรจำ

1. **Environment Strategy เป็นพื้นฐานสำคัญ** - การออกแบบที่ดีจะรองรับการเติบโตและลดความซับซ้อน

2. **Default Environment ต้องมีการจัดการ** - การตั้งชื่อใหม่และจำกัดการเข้าถึงจะช่วยลดความเสี่ยง

3. **Security Groups ช่วยในการจัดการ** - การใช้ Group-based Assignment จะทำให้การจัดการง่ายขึ้นและยืดหยุ่นกว่า

### คำถามทบทวน

1. Environment Strategy ควรพิจารณาปัจจัยใดบ้าง?
2. ทำไม Default Environment ถึงมีความเสี่ยงด้าน Security?
3. Security Groups มีข้อดีอย่างไรเมื่อเทียบกับการ Assign Users แบบ Individual?

### ขั้นตอนถัดไป

- เตรียมความพร้อมสำหรับ Module 3: Solutions & Application Lifecycle Management
- ทบทวน Environment Strategy ของ Organization ปัจจุบัน
- วางแผน Environment Architecture สำหรับโปรเจกต์ใหม่

