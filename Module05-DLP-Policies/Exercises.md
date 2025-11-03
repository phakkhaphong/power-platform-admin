# Module 5: แบบฝึกหัดปฏิบัติ
## Preventing Data Leaks with DLP Policies

---

## แบบฝึกหัด 5.1: สร้าง DLP Policy ที่ Block Connectors บางตัว

**วัตถุประสงค์:** สร้าง DLP Policy ที่ Block Connectors บางตัว

**ขั้นตอน:**

**ส่วนที่ 1: สำรวจ Connectors ที่มีอยู่**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Data** > **Data loss prevention** > **Policies**
3. (ถ้ามี Policy อยู่แล้ว) เปิดดู Policy ที่มีอยู่
4. สังเกต Connector Groups:
   - Business connectors
   - Non-business connectors
   - Blocked connectors

**ส่วนที่ 2: สร้าง DLP Policy ใหม่**

1. คลิก **+ New policy**
2. ตั้งค่าพื้นฐาน:
   - **Policy Name:** "Training DLP Policy - [YourName]"
   - **Policy Type:** เลือก "Environment policy" (สำหรับ Environment เฉพาะ) หรือ "Tenant policy" (สำหรับทั้ง Tenant)
   - **หมายเหตุ:** สำหรับการทดลอง ควรใช้ Environment policy

3. **เลือก Environment** (ถ้าเลือก Environment policy):
   - เลือก Environment ที่เหมาะสม (แนะนำใช้ Sandbox)

4. คลิก **Next**

**ส่วนที่ 3: จัดกลุ่ม Connectors**

1. **Business Connectors:**
   - คลิก **+ Add connector** ในส่วน Business
   - ค้นหาและเพิ่ม:
     - SharePoint
     - Office 365 Outlook
     - Microsoft Dataverse
     - SQL Server
   - คลิก **Add**

2. **Non-Business Connectors:**
   - คลิก **+ Add connector** ในส่วน Non-Business
   - ค้นหาและเพิ่ม:
     - Gmail
     - Twitter
     - Facebook
     - Personal OneDrive
   - คลิก **Add**

3. **Blocked Connectors:**
   - คลิก **+ Add connector** ในส่วน Blocked
   - ค้นหาและเพิ่ม Connectors ที่ต้องการ Block
   - คลิก **Add**

4. คลิก **Save policy**

**ส่วนที่ 4: ทดสอบ DLP Policy**

1. ไปที่ [Power Automate](https://make.powerautomate.com/)
2. สร้าง Flow ใหม่:
   - คลิก **+ Create** > **Instant cloud flow**
   - ตั้งชื่อ: "Test DLP Policy"
   
3. **ทดสอบ Business + Business:**
   - เพิ่ม Trigger: SharePoint - When an item is created
   - เพิ่ม Action: Dataverse - Create a new row
   - บันทึก Flow
   - ควรสำเร็จ ✅

4. **ทดสอบ Business + Non-Business:**
   - แก้ไข Flow เดิม
   - ลบ Action: Dataverse
   - เพิ่ม Action: Gmail - Send an email
   - บันทึก Flow
   - ควรถูก Block ❌ (แสดง Error Message)

5. **ทดสอบ Non-Business + Non-Business:**
   - สร้าง Flow ใหม่
   - เพิ่ม Trigger: Gmail - When a new email arrives
   - เพิ่ม Action: Twitter - Post a tweet
   - บันทึก Flow
   - ควรสำเร็จ ✅

**ส่วนที่ 5: สร้างเอกสารสรุป**

1. สร้างเอกสาร "DLP Policy Configuration":
   - Policy Name, Policy Type, Environment
   - Connector Groups (Business, Non-Business, Blocked)
   - Test Results

**ผลลัพธ์ที่คาดหวัง:**
- DLP Policy ที่ทำงานได้ถูกต้อง
- ความเข้าใจการทำงานของ DLP Policies
- เอกสารที่บันทึกการตั้งค่า

---

## แบบฝึกหัด 5.2: พัฒนากลยุทธ์ DLP แบบหลายชั้น

**วัตถุประสงค์:** พัฒนากลยุทธ์ DLP แบบหลายชั้นสำหรับองค์กรสมมติ

**สถานการณ์:**
บริษัท XYZ Corp มีโครงสร้างดังนี้:
- Corporate IT - ต้องการ DLP Policy ที่เข้มงวด
- Finance Department - ต้อง Block Social Media, อนุญาต Finance Systems
- Marketing Department - อนุญาต Social Media, Block Finance Systems
- HR Department - ต้องป้องกันข้อมูลส่วนบุคคล
- Default/Training Environment - ผ่อนปรนสำหรับการเรียนรู้

**ขั้นตอน:**

1. สร้างเอกสาร "Multi-Layered DLP Strategy"

2. **ชั้นที่ 1: Tenant-Wide DLP Policy**
   - สร้าง Policy ชื่อ "Corporate Baseline DLP"
   - กำหนด Business Connectors: Microsoft 365, Dataverse, Azure Services, SQL Server
   - กำหนด Non-Business Connectors: Social Media, Personal Services
   - กำหนด Blocked Connectors: Connectors ที่มีความเสี่ยงสูง

3. **ชั้นที่ 2: Environment-Specific Policies**
   - Finance-Production: Block Social Media, เพิ่ม Finance Connectors
   - Marketing-Production: อนุญาต Social Media, Block Finance Connectors
   - HR-Production: เพิ่ม HR Connectors, ตั้งค่าเข้มงวดสำหรับ External Sharing

4. สร้างตารางเปรียบเทียบ:
   - Environment, Inherit Tenant, Additional Business, Additional Blocked, Reason

5. สร้างแผนภาพกลยุทธ์ DLP

**ผลลัพธ์ที่คาดหวัง:**
- กลยุทธ์ DLP แบบหลายชั้นที่ครอบคลุม
- ความเข้าใจการวางแผน DLP Policies
- เอกสารที่สามารถใช้เป็น Reference

---

## แบบฝึกหัด 5.3: สร้างและใช้ DLP Policy กับ Environment เฉพาะ

**วัตถุประสงค์:** สร้างและใช้ DLP Policy กับ Environment เฉพาะ

**ขั้นตอน:**

**ส่วนที่ 1: สร้าง Environment-Specific DLP Policy**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Data** > **Data loss prevention** > **Policies**
3. คลิก **+ New policy**
4. ตั้งค่า:
   - **Policy Name:** "Production Environment DLP - [YourName]"
   - **Policy Type:** เลือก "Environment policy"
5. เลือก Environment ที่ต้องการ (แนะนำใช้ Sandbox สำหรับทดลอง)
6. คลิก **Next**

**ส่วนที่ 2: จัดกลุ่ม Connectors**

1. **Business Connectors:**
   - เพิ่ม Connectors หลัก: SharePoint, Office 365 Outlook, Microsoft Teams, Dataverse, Azure Blob Storage, SQL Server

2. **Non-Business Connectors:**
   - เพิ่ม Connectors ส่วนตัว: Gmail, Personal OneDrive, Twitter, Facebook

3. **Blocked Connectors:**
   - เพิ่ม Connectors ที่ต้องการ Block

4. คลิก **Save policy**

**ส่วนที่ 3: ตรวจสอบ Policy Application**

1. ไปที่ **Environments**
2. เลือก Environment ที่ใช้ Policy
3. ไปที่ **Data policies** (ใน Environment Details)
4. ตรวจสอบว่า DLP Policy ถูก Apply แล้ว

**ส่วนที่ 4: ทดสอบ Policy**

1. ไปที่ Power Automate
2. สร้าง Flow ใน Environment ที่ใช้ Policy
3. **ทดสอบ Scenario 1: Business + Business**
   - Trigger: SharePoint - When an item is created
   - Action: Dataverse - Create a new row
   - บันทึก - ควรสำเร็จ ✅

4. **ทดสอบ Scenario 2: Business + Non-Business**
   - แก้ไข Flow เดิม
   - เปลี่ยน Action เป็น: Gmail - Send an email
   - บันทึก - ควรถูก Block ❌

5. **ตรวจสอบ Error Message:**
   - อ่าน Error Message ที่แสดง
   - ระบุว่า Policy ไหนที่ Block การทำงาน
   - บันทึก Error Message

**ส่วนที่ 5: สร้างรายงานการใช้งาน**

1. สร้างเอกสาร "DLP Policy Implementation Report":
   - Policy Information
   - Connector Groups
   - Test Results
   - Impact Assessment

**ผลลัพธ์ที่คาดหวัง:**
- DLP Policy ที่ใช้งานได้และมีผลกับ Environment
- ความเข้าใจกระบวนการ Apply Policies
- เอกสารรายงานการใช้งาน

**หมายเหตุ:** 
- ในสภาพแวดล้อมจริง ควรแจ้งผู้ใช้ก่อน Apply Policy ใหม่
- ควรมีระยะเวลา Transition สำหรับการปรับ Flow/App ที่มีอยู่

