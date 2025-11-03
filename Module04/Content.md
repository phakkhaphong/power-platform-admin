# Module 4: Implementing a Robust Security Framework

## ภาพรวม

โมดูลนี้อธิบายโมเดลความปลอดภัยหลายชั้นของ Power Platform ตั้งแต่การ Authentication ระดับ Tenant ไปจนถึงการควบคุมการเข้าถึงข้อมูลแบบละเอียด เราจะเจาะลึกการตั้งค่า Dataverse Security รวมถึงการใช้ Business Units และ Security Roles หลักการ Least Privilege จะถูกเน้นเป็น Best Practice หลัก

## เนื้อหา

### 1. The Layered Security Model

#### ทฤษฎี

Power Platform ใช้โมเดลความปลอดภัย 4 ชั้น:

**Layer 1: Microsoft Entra ID (Azure AD)**
- **Authentication** - ระบุตัวตนผู้ใช้
- **Multi-Factor Authentication (MFA)**
- **Conditional Access Policies**
- **Single Sign-On (SSO)**
- **User Provisioning/Deprovisioning**

**Layer 2: Environment Security**
- **Environment Access Control**
- **Environment Security Groups**
- **Environment Variables (สำหรับเก็บ Secrets)**
- **Environment-level Permissions**

**Layer 3: Dataverse Security**
- **Security Roles** - กำหนด Permissions ระดับ Table/Record
- **Business Units** - แบ่งโครงสร้างองค์กร
- **Field-Level Security** - ควบคุมการเข้าถึง Field แบบละเอียด
- **Hierarchy Security** - Security แบบลำดับชั้น

**Layer 4: App-Level Security**
- **App Permissions** - ควบคุมการเข้าถึงแอป
- **Connection Permissions** - ควบคุมการใช้ Connectors
- **Sharing Controls** - ควบคุมการแชร์ Apps/Flows

**หลักการ Least Privilege:**
- ให้สิทธิ์เฉพาะที่จำเป็นเท่านั้น
- เริ่มจากสิทธิ์ต่ำสุด แล้วค่อยๆ เพิ่มเมื่อจำเป็น
- ทบทวนสิทธิ์เป็นประจำ
- ใช้ Security Roles ที่เหมาะสม

**อ้างอิง:**
- [Security Overview](https://learn.microsoft.com/en-us/power-platform/admin/security-overview)
- [Security Roles and Privileges](https://learn.microsoft.com/en-us/power-platform/admin/security-roles-privileges)

---

### 2. Configuring Dataverse Security

#### ทฤษฎี

**Security Roles:**
Security Roles กำหนด Permissions ที่ผู้ใช้สามารถทำได้กับ Tables และ Records

**Types of Permissions:**
- **Create** - สร้าง Records ใหม่
- **Read** - อ่าน Records
- **Write** - แก้ไข Records
- **Delete** - ลบ Records
- **Append** - เชื่อมต่อ Records (เช่น Attachment)
- **Append To** - ให้สิทธิ์ Record อื่นเชื่อมต่อมา
- **Assign** - กำหนด Ownership
- **Share** - แชร์ Records

**Scope Levels:**
- **Organization** - ทั้ง Organization
- **Business Unit** - เฉพาะ Business Unit
- **Business Unit and Child** - Business Unit และลูก
- **Parent Business Unit** - Parent Business Unit
- **User** - เฉพาะ Records ที่ User เป็น Owner

**Business Units:**
- โครงสร้างองค์กรที่แบ่ง Users และ Records
- ช่วยในการแบ่งแยกข้อมูลระหว่างหน่วยงาน
- รองรับ Hierarchy (Parent-Child)

**อ้างอิง:**
- [Security Roles](https://learn.microsoft.com/en-us/power-platform/admin/security-roles-privileges)
- [Business Units](https://learn.microsoft.com/en-us/power-platform/admin/create-edit-business-units)

---

### 3. Tenant-Level Security Settings

#### ทฤษฎี

**Tenant-Level Security Settings สำคัญ:**

**Tenant Isolation**
- ป้องกันการ Exfiltrate ข้อมูลออกนอก Tenant
- ควบคุมการเชื่อมต่อระหว่าง Environments
- ป้องกันการใช้ Connectors ที่ไม่ได้รับอนุญาต

**Restrict Tenant-Level Analytics**
- ควบคุมการเข้าถึง Analytics
- ป้องกันการเปิดเผยข้อมูลการใช้งาน

**Sharing Settings**
- ควบคุมการแชร์ Apps/Flows
- กำหนดว่าใครสามารถ Share ได้บ้าง

**Environment Creation**
- ควบคุมว่าใครสามารถสร้าง Environments ใหม่ได้
- กำหนด Capacity Limits

**Connector Sharing**
- ควบคุมการแชร์ Custom Connectors

**อ้างอิง:**
- [Tenant Settings](https://learn.microsoft.com/en-us/power-platform/admin/tenant-settings)

---

## สรุป Module 4

### จุดสำคัญที่ควรจำ

1. **Security Model มี 4 ชั้น** - แต่ละชั้นมีบทบาทสำคัญในการป้องกัน

2. **Security Roles กำหนด Permissions** - ใช้หลักการ Least Privilege ในการกำหนด

3. **Tenant-Level Settings สำคัญ** - การตั้งค่าที่ถูกต้องจะช่วยป้องกัน Data Exfiltration

### คำถามทบทวน

1. Security Layers ทั้ง 4 ชั้นมีอะไรบ้าง และแต่ละชั้นทำหน้าที่อะไร?
2. Scope Levels ของ Security Roles มีอะไรบ้าง และใช้เมื่อไหร่?
3. Tenant Isolation มีความสำคัญอย่างไร?

### ขั้นตอนถัดไป

- เตรียมความพร้อมสำหรับ Module 5: Preventing Data Leaks with DLP Policies
- ทบทวน Security Roles ที่มีอยู่ใน Organization
- วางแผน Security Strategy สำหรับ Environment ใหม่

