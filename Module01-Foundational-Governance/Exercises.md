# Module 1: แบบฝึกหัดปฏิบัติ
## Foundational Governance & Admin Center

---

## แบบฝึกหัด 1.1: ตรวจสอบและวิเคราะห์ License Plan

**วัตถุประสงค์:** ตรวจสอบและวิเคราะห์ License Plan ขององค์กร

**ขั้นตอน:**

1. เข้าสู่ [Microsoft 365 Admin Center](https://admin.microsoft.com/)
2. ไปที่ **Billing** > **Licenses**
3. ค้นหาและระบุ License ที่เกี่ยวข้องกับ Power Platform:
   - Microsoft Power Apps per app
   - Microsoft Power Automate per flow
   - Microsoft Power Platform
   - Microsoft 365 licenses (ที่รวม Power Platform)
4. สร้างตารางสรุป:
   - จำนวน License ที่มี
   - จำนวน License ที่ใช้งานแล้ว
   - จำนวน License ที่ว่าง
   - ราคาต่อ License ต่อเดือน

**ผลลัพธ์ที่คาดหวัง:**
- เอกสารสรุป License Status ขององค์กร
- คำแนะนำ License Plan ที่เหมาะสมสำหรับแต่ละประเภทผู้ใช้

---

## แบบฝึกหัด 1.2: สร้าง Checklist งานประจำสำหรับผู้ดูแลระบบ

**วัตถุประสงค์:** สร้าง Checklist งานประจำสำหรับผู้ดูแลระบบ Power Platform

**ขั้นตอน:**

1. สร้างเอกสาร Excel หรือ Word สำหรับ Checklist
2. แบ่งงานออกเป็น 3 ประเภท:
   
   **งานประจำ (Daily)**
   - [ ] ตรวจสอบ Health Status ของ Environments
   - [ ] ตรวจสอบ Alert และ Notification
   - [ ] ตรวจสอบ License Utilization
   
   **งานรายสัปดาห์ (Weekly)**
   - [ ] วิเคราะห์ Analytics Dashboard
   - [ ] ตรวจสอบ Orphaned Resources
   - [ ] รีวิว Security Roles และ Permissions
   - [ ] ตรวจสอบ DLP Policy Violations
   
   **งานรายเดือน (Monthly)**
   - [ ] สรุปรายงานการใช้งาน
   - [ ] Review Environment Strategy
   - [ ] อัปเดต Documentation
   - [ ] Training และ Knowledge Sharing

3. เพิ่มคอลัมน์สำหรับ:
   - ผู้รับผิดชอบ (Assignee)
   - วันครบกำหนด (Due Date)
   - สถานะ (Status)
   - หมายเหตุ (Notes)

**ผลลัพธ์ที่คาดหวัง:**
- Checklist งานประจำสำหรับผู้ดูแลระบบ
- เอกสารที่สามารถใช้งานจริงและอัปเดตได้

---

## แบบฝึกหัด 1.3: สำรวจและสร้างแผนที่ของ Power Platform Admin Center

**วัตถุประสงค์:** สำรวจและสร้างแผนที่ของ Power Platform Admin Center

**ขั้นตอน:**

1. เข้าสู่ [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/)
2. สำรวจแต่ละส่วนหลัก:
   
   **ส่วน Environments:**
   - ระบุจำนวน Environments ที่มี
   - ระบุประเภทของแต่ละ Environment
   - ตรวจสอบ Region ของแต่ละ Environment
   
   **ส่วน Analytics:**
   - เข้าสู่ Usage Analytics
   - บันทึกข้อมูล:
     - จำนวน Apps ที่ใช้งาน
     - จำนวน Flows ที่ใช้งาน
     - Top 5 Makers
     - Top 5 Apps by Usage
   
   **ส่วน Data Policies:**
   - ตรวจสอบว่ามี DLP Policies กี่ตัว
   - ระบุว่า Policies ใดเป็น Tenant-wide
   - ระบุว่า Policies ใดเป็น Environment-specific
   
   **ส่วน Admin Settings:**
   - ไปที่ Settings > Tenant Settings
   - ตรวจสอบ Tenant Isolation Settings
   - ตรวจสอบ Analytics Settings

3. สร้างเอกสาร "PPAC Navigation Map" ที่มี:
   - ภาพหน้าจอของแต่ละส่วน
   - คำอธิบายฟังก์ชันของแต่ละส่วน
   - ทางลัดหรือ Tips ที่มีประโยชน์

**ผลลัพธ์ที่คาดหวัง:**
- แผนที่นำทาง PPAC พร้อมคำอธิบาย
- ความคุ้นเคยกับโครงสร้างและฟังก์ชันของ PPAC

