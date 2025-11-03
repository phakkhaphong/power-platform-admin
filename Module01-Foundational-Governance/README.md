# Module 1: Foundational Governance & Admin Center

## ภาพรวม

โมดูลนี้จะวางหลักการพื้นฐานของการกำกับดูแล Power Platform โดยเริ่มจาก Licensing เป็นกลไกควบคุมหลัก ผู้เข้าร่วมจะได้สำรวจความรับผิดชอบของผู้ดูแลระบบ Power Platform และเรียนรู้การใช้งาน Power Platform Admin Center (PPAC) ที่ทันสมัยและเน้นผลลัพธ์ ความรู้พื้นฐานนี้มีความสำคัญอย่างยิ่งสำหรับการจัดการแพลตฟอร์มอย่างมีประสิทธิภาพ

## เนื้อหา

### 1. ความเข้าใจเกี่ยวกับ Power Platform Licensing

#### ทฤษฎี

Power Platform Licensing เป็นชั้นแรกของการกำกับดูแล แบ่งออกเป็น 3 แบบหลัก:

**Microsoft 365 Licenses**
- รวมอยู่ใน Microsoft 365 Business Standard/Enterprise
- อนุญาตให้สร้างแอป Canvas, Power Automate flows, Power Pages
- จำกัดการใช้งานต่อผู้ใช้ต่อเดือน
- ใช้ได้กับ Default Environment และ Custom Environments แบบไม่มี Dataverse

**Premium/Pay-per-App Plans**
- Power Apps per-app/per-user plans
- Power Automate per-flow/per-user plans
- ให้สิทธิ์เข้าถึง Premium connectors และ Dataverse
- เหมาะสำหรับผู้ใช้ที่ต้องการฟีเจอร์ขั้นสูง

**Pay-as-you-go**
- รูปแบบการชำระเงินตามการใช้งานจริง
- เหมาะสำหรับโปรเจกต์ระยะสั้นหรือการทดสอบ
- สามารถควบคุมต้นทุนได้ตามการใช้งานจริง

**อ้างอิง:** [Power Platform Licensing](https://learn.microsoft.com/en-us/power-platform/admin/power-platform-licensing-azure)

---

### 2. บทบาทของผู้ดูแลระบบ Power Platform

#### ทฤษฎี

ผู้ดูแลระบบ Power Platform มีความรับผิดชอบหลายด้าน:

**Environment Management**
- สร้าง จัดการ และลบ Environments
- กำหนด Environment Strategy
- ควบคุมการเข้าถึง Environment

**Security Administration**
- กำหนด Security Roles และ Permissions
- จัดการ Data Loss Prevention (DLP) Policies
- ตรวจสอบและวิเคราะห์ Audit Logs

**Monitoring and Analytics**
- ติดตามการใช้งาน Apps และ Flows
- ระบุผู้สร้างหลัก (Top Makers)
- ตรวจหาทรัพยากรที่ไม่ใช้งาน (Orphaned Resources)

**Governance Implementation**
- กำหนดนโยบายและมาตรฐาน
- ใช้ CoE Starter Kit หรือ Managed Environments
- สร้าง Center of Excellence (CoE)

**อ้างอิง:** [Admin Responsibilities](https://learn.microsoft.com/en-us/power-platform/admin/admin-documentation)

---

### 3. การใช้งาน Power Platform Admin Center (PPAC)

#### ทฤษฎี

Power Platform Admin Center เป็นศูนย์กลางการจัดการ Power Platform ที่ทันสมัยและเน้นผลลัพธ์

**ส่วนหลักของ PPAC:**

**Home/Dashboard**
- ภาพรวม Health Status
- Quick Actions
- Recent Activities
- Resource Summary

**Environments**
- รายการ Environments ทั้งหมด
- Environment Details (Type, Region, Storage)
- Security Settings
- Environment Variables

**Analytics**
- Usage Analytics
- Adoption Reports
- Top Makers
- Orphaned Resources
- Capacity Reports

**Data Policies (DLP)**
- Tenant-wide Policies
- Environment-specific Policies
- Policy Rules และ Connector Groups

**Admin Settings**
- Tenant Settings
- Integration Settings
- Environment Settings

**Resources**
- Capacity Management
- Power Platform Requests
- Support Tickets

**อ้างอิง:** [Navigate PPAC](https://learn.microsoft.com/en-us/power-platform/admin/admin-documentation)

---

## สรุป Module 1

### จุดสำคัญที่ควรจำ

1. **Licensing เป็นกลไกควบคุมแรก** - การเลือก License Plan ที่เหมาะสมจะกำหนดขอบเขตการใช้งานและฟีเจอร์ที่เข้าถึงได้

2. **บทบาทผู้ดูแลระบบครอบคลุมหลายด้าน** - จาก Environment Management ไปจนถึง Governance Implementation

3. **PPAC เป็นศูนย์กลางการจัดการ** - การเข้าใจโครงสร้างและฟังก์ชันของ PPAC จะช่วยเพิ่มประสิทธิภาพในการทำงาน

### คำถามทบทวน

1. License Plan แบบใดที่เหมาะสมสำหรับผู้ใช้ที่ต้องการสร้าง Canvas Apps เพียงไม่กี่ตัว?
2. งานใดบ้างที่ผู้ดูแลระบบควรทำทุกวัน?
3. ส่วนใดของ PPAC ที่ใช้ตรวจสอบการใช้งาน Apps และ Flows?

### ขั้นตอนถัดไป

- เตรียมความพร้อมสำหรับ Module 2: Designing a Scalable Environment Architecture
- ทบทวนรายชื่อ Environments ปัจจุบันใน Organization
- พิจารณา Environment Strategy ที่เหมาะสมสำหรับ Organization

