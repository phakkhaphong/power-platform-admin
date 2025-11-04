# Module 4: แบบฝึกหัดปฏิบัติ
## Implementing a Robust Security Framework

---

## แบบฝึกหัด 4.1: แสดงแผนที่ Security Layers

**วัตถุประสงค์:** แสดงแผนที่ Security Layers สำหรับแอปพลิเคชันหนึ่ง

**สถานการณ์:**
บริษัท ABC Corp ต้องการสร้าง HR Management App ที่:
- มี HR Team (20 คน) สามารถ CRUD ทุกอย่าง
- มี Managers (50 คน) สามารถ Read ได้แต่ไม่สามารถ Edit Salary
- มี Employees (500 คน) สามารถ Read ข้อมูลของตนเองเท่านั้น
- ต้องใช้ MFA
- ต้องใช้ Dataverse Database

**ขั้นตอน:**

1. สร้างเอกสาร "Security Layers Mapping"

2. **Layer 1: Microsoft Entra ID**
   - สร้าง Security Groups:
     - HR-Team-SG
     - Managers-SG
     - Employees-SG
   - ตั้งค่า MFA:
     - Enable MFA สำหรับ Security Groups ทั้งหมด
   - Conditional Access:
     - กำหนด Policy ที่เหมาะสม

3. **Layer 2: Environment Security**
   - สร้าง Environment: "HR-Production"
   - Assign Security Groups:
     - HR-Team-SG → System Administrator
     - Managers-SG → System Customizer
     - Employees-SG → User

4. **Layer 3: Dataverse Security**
   - สร้าง Tables:
     - Employee Information
     - Salary Information
     - Performance Reviews
   - สร้าง Security Roles:
     - **HR Full Access**
       - Employee Information: Create, Read, Write, Delete
       - Salary Information: Create, Read, Write, Delete
       - Performance Reviews: Create, Read, Write, Delete
     - **Manager Read Access**
       - Employee Information: Read
       - Salary Information: Read (แต่ Field-Level Security ป้องกัน)
       - Performance Reviews: Read
     - **Employee Self-Service**
       - Employee Information: Read (เฉพาะ Record ของตนเอง)
       - Salary Information: Read (เฉพาะ Record ของตนเอง)
       - Performance Reviews: Read (เฉพาะ Record ของตนเอง)

5. **Layer 4: App-Level Security**
   - สร้าง Model-driven App: "HR Management"
   - ตั้งค่า App Permissions:
     - Share กับ Security Groups ที่เหมาะสม
   - ตั้งค่า Connection Permissions:
     - ใช้ Connectors ที่เหมาะสม

6. สร้างแผนภาพ Security Layers

**ผลลัพธ์ที่คาดหวัง:**
- แผนที่ Security Layers ที่ชัดเจน
- ความเข้าใจการทำงานร่วมกันของ Security Layers

---

## แบบฝึกหัด 4.2: สร้าง Custom Security Role

**วัตถุประสงค์:** สร้าง Custom Security Role ใน Dataverse และ Assign ให้กับ User

**ขั้นตอน:**

**ส่วนที่ 1: สร้าง Custom Security Role**

1. เข้าสู่ Power Platform Admin Center
2. เลือก Environment ที่มี Dataverse
3. ไปที่ **Settings** > **Users + permissions** > **Security roles**
4. คลิก **New role**
5. ตั้งค่าพื้นฐาน:
   - **Role Name:** "Sales Read Only - Custom"
   - **Business Unit:** เลือก Root Business Unit หรือ Business Unit ที่เหมาะสม
   - **Description:** "Custom role for Sales team with read-only access"

6. ไปที่ Tab **Core Records**
7. ตั้งค่า Permissions สำหรับ Tables หลัก:
   - **Accounts:**
     - Organization: Read ✅
   - **Contacts:**
     - Organization: Read ✅
   - **Leads:**
     - Organization: Read ✅
   - **Opportunities:**
     - Organization: Read ✅

8. ไปที่ Tab **Customization**
9. ตั้งค่า Permissions สำหรับ:
   - **Solutions:** Read ✅ (เพื่อให้เห็น Apps)
   - **Customizations:** Read ✅

10. บันทึก Security Role

**ส่วนที่ 2: Assign Security Role ให้ User**

1. ไปที่ **Settings** > **Users + permissions** > **Users**
2. ค้นหาและเลือก User ที่ต้องการ
3. คลิก **Manage security roles**
4. เลือก Security Role ที่สร้างไว้: "Sales Read Only - Custom"
5. คลิก **OK**

**ส่วนที่ 3: ทดสอบ Security Role**

1. (ถ้าเป็นไปได้) Login เป็น User ที่ Assign Role นั้น
2. ตรวจสอบว่า:
   - ✅ สามารถเห็น Accounts, Contacts, Leads, Opportunities
   - ✅ สามารถ Read Records ได้
   - ❌ ไม่สามารถ Create, Edit, หรือ Delete Records ได้

**ผลลัพธ์ที่คาดหวัง:**
- Custom Security Role ที่ใช้งานได้
- ความเข้าใจการตั้งค่า Permissions
- เอกสารที่บันทึกการตั้งค่า

---

## แบบฝึกหัด 4.3: ตั้งค่า Tenant-Level Security Settings

**วัตถุประสงค์:** ตั้งค่า Tenant-Level Security Settings

**ขั้นตอน:**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Settings** > **Tenant settings** (หรือ **Admin Settings**)

**หมายเหตุ:** ใน PPAC เวอร์ชันล่าสุด การตั้งค่า Tenant Isolation และ Manage sharing ได้ย้ายไปอยู่ที่ **Settings** > **Security** > **Identity and Access** แล้ว

3. **ตรวจสอบและตั้งค่า Tenant Isolation:**
   - ไปที่ **Settings** > **Security** > **Identity and Access** > **Tenant isolation**
   - ตรวจสอบ Settings:
     - **Allow connectors to share data across different environments**
     - **Block connections that send data to services outside the tenant**
   - บันทึกการตั้งค่าปัจจุบัน

4. **ตั้งค่า Manage sharing:**
   - ไปที่ **Settings** > **Security** > **Identity and Access** > **Manage sharing**
   - ตรวจสอบ Settings:
     - **Allow makers to share canvas apps**
     - **Allow makers to share cloud flows**
     - **Allow makers to share custom connectors**

5. **ตั้งค่า Environment Creation:**
   - ไปที่ **Environments**
   - ตรวจสอบ Settings:
     - **Allow users to create environments**
   - ระบุว่าใครสามารถสร้างได้ (Security Groups)

6. **ตั้งค่า Analytics:**
   - ไปที่ **Analytics**
   - ตรวจสอบ Settings:
     - **Allow makers to see tenant-level analytics**

7. **ตั้งค่า Security:**
   - ไปที่ **Settings** > **Security** > **Identity and Access** (หรือ **Settings** > **Tenant settings** > **Security**)
   - ตรวจสอบ Settings:
     - **Allow users to access Dataverse**
     - **Allow users to access Power Platform**
     - **Enable Conditional Access** (หมายเหตุ: Conditional Access มักจะตั้งค่าใน Microsoft Entra ID)

8. **สร้างเอกสาร "Tenant Security Settings":**
   - บันทึกการตั้งค่าทั้งหมด
   - เพิ่ม Recommendations

**ผลลัพธ์ที่คาดหวัง:**
- บันทึกการตั้งค่า Tenant-Level Security
- ความเข้าใจการตั้งค่าที่สำคัญ
- เอกสารที่สามารถใช้เป็น Reference

**หมายเหตุ:** ในสภาพแวดล้อมจริง ควรปรึกษากับ Security Team ก่อนทำการเปลี่ยนแปลง Settings ที่สำคัญ

