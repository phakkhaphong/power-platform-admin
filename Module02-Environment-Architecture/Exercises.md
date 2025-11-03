# Module 2: แบบฝึกหัดปฏิบัติ
## Designing a Scalable Environment Architecture

---

## แบบฝึกหัด 2.1: ออกแบบ Environment Strategy สำหรับองค์กรสมมติ

**วัตถุประสงค์:** ออกแบบ Environment Strategy สำหรับองค์กรสมมติ

**สถานการณ์:**
บริษัท ABC Corp มีโครงสร้างดังนี้:
- ฝ่าย IT (50 คน) - พัฒนา Corporate Apps
- ฝ่าย HR (20 คน) - มี HR Management System
- ฝ่ายขาย (100 คน) - ใช้ CRM System
- ฝ่ายการเงิน (30 คน) - มี Finance Management System
- ผู้ใช้ทั่วไป (500 คน) - ต้องการสร้าง Personal Productivity Apps

**ขั้นตอน:**

1. สร้างเอกสาร "Environment Strategy Document"
2. กำหนด Environments ตามลำดับต่อไปนี้:

   **Production Environments:**
   - [ ] ตั้งชื่อ Environment สำหรับแต่ละฝ่าย
   - [ ] ระบุประเภท (Type): Production, Sandbox, Trial
   - [ ] ระบุ Region (เลือกตามที่อยู่ของผู้ใช้หลัก)
   - [ ] ระบุ Purpose (วัตถุประสงค์)

   **Development/Testing Environments:**
   - [ ] กำหนด Dev Environment สำหรับแต่ละ Production Environment
   - [ ] กำหนด Test/UAT Environment สำหรับแต่ละ Production Environment

3. สร้างตารางสรุป:

| Environment Name | Type | Purpose | Region | Target Users | Storage Capacity |
|------------------|------|---------|--------|--------------|------------------|
| HR-Prod | Production | HR Management | Southeast Asia | HR Team | 10 GB |
| HR-Dev | Sandbox | HR Development | Southeast Asia | IT Developers | 2 GB |
| HR-Test | Sandbox | HR Testing | Southeast Asia | HR Team, IT | 2 GB |
| ... | ... | ... | ... | ... | ... |

4. เพิ่มส่วน "Governance Rules":
   - ใครสามารถสร้าง Environments ใหม่ได้?
   - Naming Convention เป็นอย่างไร?
   - Retention Policy สำหรับ Environments ที่ไม่ใช้งาน?
   - Backup Strategy?

**ผลลัพธ์ที่คาดหวัง:**
- เอกสาร Environment Strategy ที่ครบถ้วน
- ความเข้าใจในการออกแบบ Environment Architecture

---

## แบบฝึกหัด 2.2: เปลี่ยนชื่อและตั้งค่าความปลอดภัยของ Default Environment

**วัตถุประสงค์:** เปลี่ยนชื่อและตั้งค่าความปลอดภัยของ Default Environment

**ขั้นตอน:**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Environments**
3. ค้นหาและเลือก Default Environment (ชื่อเดิมคือ "Default")
4. เปลี่ยนชื่อ Environment:
   - คลิกที่ชื่อ Environment หรือคลิก "Edit"
   - เปลี่ยนชื่อเป็น "Personal Productivity" หรือชื่ออื่นที่เหมาะสม
   - บันทึกการเปลี่ยนแปลง

5. ตั้งค่าความปลอดภัย:
   - ไปที่ **Security** > **Users**
   - ตรวจสอบรายชื่อผู้ใช้ที่มีสิทธิ์เข้าถึง
   - (ถ้ามีสิทธิ์) จำกัดการเข้าถึงผ่าน Security Groups:
     - ไปที่ **Access** > **Security Groups**
     - เพิ่มหรือลบ Security Groups

6. ตรวจสอบ Settings อื่นๆ:
   - **Settings** > **Product**
     - ตรวจสอบว่ามี Product ใดบ้างที่เปิดใช้งาน
   - **Settings** > **Update Management**
     - ตรวจสอบ Early Access Settings

7. สร้างเอกสาร "Default Environment Configuration":
   - บันทึกชื่อใหม่
   - บันทึก Security Settings
   - บันทึก DLP Policies ที่ใช้ (ถ้ามี)
   - บันทึกวันที่และผู้ทำการเปลี่ยนแปลง

**ผลลัพธ์ที่คาดหวัง:**
- Default Environment ที่มีชื่อใหม่และมีความปลอดภัยมากขึ้น
- เอกสาร Configuration ที่อัปเดต

**หมายเหตุ:** ในสภาพแวดล้อมจริง ควรมีการทดสอบและแจ้งผู้ใช้ก่อนทำการเปลี่ยนแปลง

---

## แบบฝึกหัด 2.3: สร้าง Environment ใหม่และตั้งค่าความปลอดภัยด้วย Microsoft Entra ID Security Groups

**วัตถุประสงค์:** สร้าง Environment ใหม่และตั้งค่าความปลอดภัยด้วย Microsoft Entra ID Security Groups

**ขั้นตอน:**

**ส่วนที่ 1: สร้าง Security Groups (ถ้ายังไม่มี)**

1. เข้าสู่ [Microsoft 365 Admin Center](https://admin.microsoft.com/)
2. ไปที่ **Groups** > **Active groups**
3. สร้าง Security Groups 3 กลุ่ม (ถ้ายังไม่มี):
   - **PP-Admin-[EnvironmentName]** - สำหรับ Administrators
   - **PP-Maker-[EnvironmentName]** - สำหรับ Makers/Developers
   - **PP-User-[EnvironmentName]** - สำหรับ End Users
4. เพิ่มสมาชิกในแต่ละ Group

**ส่วนที่ 2: สร้าง Environment**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Environments**
3. คลิก **+ New**
4. กรอกข้อมูล:
   - **Name:** "Test-Dev-[YourInitials]" (ใช้ชื่อที่ไม่ซ้ำ)
   - **Type:** เลือก "Sandbox" (สำหรับการทดลอง)
   - **Region:** เลือก Region ที่เหมาะสม
   - **Purpose:** "Training and Development"
   - **Create a database for this environment:** ✅ (เลือกเพื่อสร้าง Dataverse)
5. คลิก **Save**
6. รอจนกว่า Environment จะสร้างเสร็จ (อาจใช้เวลาหลายนาที)

**ส่วนที่ 3: ตั้งค่าความปลอดภัย**

1. เมื่อ Environment สร้างเสร็จ คลิกที่ Environment
2. ไปที่ **Access** > **Security Groups**
3. เพิ่ม Security Groups ที่สร้างไว้:
   - คลิก **+ Add security group**
   - ค้นหาและเลือก Groups ที่สร้างไว้
   - กำหนด Role:
     - PP-Admin → System Administrator
     - PP-Maker → System Customizer หรือ Maker
     - PP-User → User หรือ Viewer

4. ไปที่ **Security** > **Users**
5. ตรวจสอบว่า Users ถูก Assign ผ่าน Security Groups

**ส่วนที่ 4: ตั้งค่าเพิ่มเติม**

1. ไปที่ **Settings** > **Product**
2. ตรวจสอบว่า Products ใดเปิดใช้งาน:
   - Power Apps
   - Power Automate
   - Power Pages
   - Power Virtual Agents

3. ไปที่ **Settings** > **Update Management**
4. ตรวจสอบ Update Settings

**ส่วนที่ 5: สร้างเอกสาร**

1. สร้างเอกสาร "Environment Creation Checklist":
   - ✅ Environment สร้างเสร็จ
   - ✅ Security Groups ถูก Assign
   - ✅ Users สามารถเข้าถึงได้
   - ✅ Products เปิดใช้งาน
   - ✅ Naming Convention ถูกต้อง
   - ✅ Region ถูกต้อง

**ผลลัพธ์ที่คาดหวัง:**
- Environment ใหม่ที่สร้างเสร็จและพร้อมใช้งาน
- Security Configuration ที่เหมาะสม
- เอกสารที่บันทึกการตั้งค่า

**หมายเหตุ:** 
- สำหรับ Production Environments ควรมีกระบวนการ Approval
- ควรทดสอบการเข้าถึงก่อนใช้งานจริง

