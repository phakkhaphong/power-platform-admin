# Module 3: แบบฝึกหัดปฏิบัติ
## Solutions & Application Lifecycle Management (ALM)

---

## แบบฝึกหัด 3.1: สร้าง Solution ง่ายๆ ที่รวม Canvas App และ Flow

**วัตถุประสงค์:** สร้าง Solution ง่ายๆ ที่รวม Canvas App และ Flow

**ขั้นตอน:**

**ส่วนที่ 1: สร้าง Canvas App**

1. เข้าสู่ Power Apps Studio
2. สร้าง Canvas App ใหม่:
   - ไปที่ [Power Apps](https://make.powerapps.com/)
   - เลือก Environment ที่เหมาะสม (แนะนำใช้ Sandbox)
   - คลิก **+ Create** > **Canvas app from blank**
   - ตั้งชื่อ: "Training App - [YourName]"
   - เลือก Tablet หรือ Phone format
   - คลิก **Create**

3. เพิ่ม Controls พื้นฐาน:
   - เพิ่ม Text Input ชื่อ "txtName"
   - เพิ่ม Button ชื่อ "btnGreet"
   - เพิ่ม Label ชื่อ "lblMessage"
   
4. ตั้งค่า Button:
   - ตั้งค่า OnSelect ของ btnGreet:
   ```
   UpdateContext({greeting: "Hello, " & txtName.Text & "!"})
   ```
   - ตั้งค่า Text ของ lblMessage:
   ```
   greeting
   ```

5. บันทึก App

**ส่วนที่ 2: สร้าง Flow**

1. ไปที่ [Power Automate](https://make.powerautomate.com/)
2. สร้าง Cloud Flow ใหม่:
   - คลิก **+ Create** > **Instant cloud flow**
   - ตั้งชื่อ: "Training Flow - [YourName]"
   - เลือก Trigger: "Manual trigger"
   - คลิก **Create**

3. เพิ่ม Action:
   - เพิ่ม Action "Compose"
   - ตั้งค่า Inputs: "Training Flow executed successfully"
   
4. บันทึก Flow

**ส่วนที่ 3: สร้าง Solution และเพิ่ม Components**

1. ไปที่ [Power Apps Maker Portal](https://make.powerapps.com/)
2. ไปที่ **Solutions** (เมนูด้านซ้าย)
3. สร้าง Solution ใหม่:
   - คลิก **+ New solution**
   - ตั้งชื่อ: "Training Solution - [YourName]"
   - Display Name: "Training Solution - [YourName]"
   - Publisher: เลือก Default Publisher หรือสร้างใหม่
   - Version: "1.0.0.0"
   - คลิก **Create**

4. เพิ่ม Canvas App เข้า Solution:
   - เปิด Solution ที่สร้าง
   - คลิก **+ Add existing** > **App** > **Canvas app**
   - เลือก "Training App - [YourName]" ที่สร้างไว้
   - คลิก **Add**

5. เพิ่ม Flow เข้า Solution:
   - คลิก **+ Add existing** > **Automation** > **Cloud flow**
   - เลือก "Training Flow - [YourName]" ที่สร้างไว้
   - คลิก **Add**

**ส่วนที่ 4: ตรวจสอบ Solution**

1. ตรวจสอบว่า Solution มี Components:
   - Canvas App
   - Flow
   - Publisher Information
   - Version

2. คลิก **Export solution** (เพื่อดู Options)
   - ตรวจสอบ Export Options:
     - Managed
     - Unmanaged
   
3. สร้างเอกสารสรุป:
   - ชื่อ Solution
   - Components ที่รวมอยู่
   - Version
   - Publisher

**ผลลัพธ์ที่คาดหวัง:**
- Solution ที่มี Canvas App และ Flow
- ความเข้าใจในการรวม Components เข้าด้วยกัน

---

## แบบฝึกหัด 3.2: แปลง Unmanaged Solution เป็น Managed Solution

**วัตถุประสงค์:** แปลง Unmanaged Solution เป็น Managed Solution และสังเกตความแตกต่าง

**ขั้นตอน:**

**ส่วนที่ 1: Export Unmanaged Solution**

1. ไปที่ Solution ที่สร้างไว้ใน Exercise 3.1
2. คลิก **Export solution**
3. ตรวจสอบ Settings:
   - **Version:** 1.0.0.0 (หรือเวอร์ชันที่เหมาะสม)
   - **Export as:** เลือก **Unmanaged**
4. คลิก **Export**
5. รอจนกว่า Solution จะ Export เสร็จ
6. ดาวน์โหลดไฟล์ .zip

**ส่วนที่ 2: Import เป็น Managed Solution**

1. ไปที่ Environment อื่น (หรือ Environment เดิมถ้ามี)
2. ไปที่ **Solutions**
3. คลิก **Import solution**
4. เลือกไฟล์ .zip ที่ดาวน์โหลดมา
5. คลิก **Next**
6. ตรวจสอบ Package Details:
   - Package Type: Unmanaged
   - Components ที่จะ Import
7. คลิก **Import**
8. รอจนกว่าจะ Import เสร็จ

**ส่วนที่ 3: Export เป็น Managed Solution**

1. กลับไปที่ Solution ใน Environment ต้นทาง
2. คลิก **Export solution**
3. ตรวจสอบ Settings:
   - **Version:** 1.0.0.1 (เพิ่ม Version)
   - **Export as:** เลือก **Managed**
4. คลิก **Export**
5. ดาวน์โหลดไฟล์ .zip

**ส่วนที่ 4: Import Managed Solution**

1. ไปที่ Environment ปลายทาง (แนะนำใช้ Environment ใหม่)
2. Import Managed Solution ที่ Export มา
3. สังเกตความแตกต่าง:
   - Solution จะแสดงเป็น Managed
   - ไม่สามารถแก้ไข Components โดยตรงได้

**ส่วนที่ 5: ทดสอบความแตกต่าง**

1. **ใน Unmanaged Solution:**
   - เปิด Canvas App ใน Solution
   - พยายามแก้ไข (ควรทำได้)

2. **ใน Managed Solution:**
   - เปิด Canvas App ใน Managed Solution
   - พยายามแก้ไข (ควรทำไม่ได้หรือจำกัด)

3. **การลบ Components:**
   - ลองลบ Component จาก Unmanaged Solution (ควรทำได้)
   - ลองลบ Component จาก Managed Solution (ควรทำไม่ได้)

**ส่วนที่ 6: สร้างเอกสารสรุป**

1. สร้างตารางเปรียบเทียบ:

| Feature | Unmanaged | Managed |
|---------|-----------|---------|
| Can Edit App | ✅ | ❌ |
| Can Delete Flow | ✅ | ❌ |
| Can Add Components | ✅ | ⚠️ Limited |
| Recommended Use | Development | Production |

**ผลลัพธ์ที่คาดหวัง:**
- ความเข้าใจความแตกต่างระหว่าง Managed และ Unmanaged
- ความสามารถในการ Export/Import Solutions

---

## แบบฝึกหัด 3.3: Deploy Solution จาก Development Environment ไปยัง Test Environment

**วัตถุประสงค์:** Deploy Solution จาก Development Environment ไปยัง Test Environment

**ขั้นตอน:**

**ส่วนที่ 1: เตรียม Solution สำหรับ Deployment**

1. ไปที่ Solution ใน Dev Environment
2. ใช้ Solution Checker:
   - คลิก **Solution Checker** > **Run**
   - รอจนกว่าจะตรวจสอบเสร็จ
   - ตรวจสอบ Results:
     - Errors (ต้องแก้ไข)
     - Warnings (ควรแก้ไข)
     - Information (แนะนำ)

3. แก้ไข Issues (ถ้ามี)
4. อัปเดต Version:
   - คลิก **Edit solution**
   - เปลี่ยน Version เป็นเวอร์ชันใหม่ (เช่น 1.0.1.0)
   - บันทึก

**ส่วนที่ 2: Export Managed Solution**

1. คลิก **Export solution**
2. ตั้งค่า:
   - **Version:** เวอร์ชันล่าสุด
   - **Export as:** Managed
3. คลิก **Export**
4. ดาวน์โหลดไฟล์ .zip
5. ตั้งชื่อไฟล์ให้สื่อความหมาย:
   - "TrainingSolution_1.0.1.0_Managed.zip"

**ส่วนที่ 3: ตรวจสอบไฟล์ Solution**

1. เปิดไฟล์ .zip (ไม่ต้อง Extract)
2. ตรวจสอบไฟล์ภายใน:
   - solution.xml
   - customizations.xml
   - [Content_Types].xml

**ส่วนที่ 4: Import ไปยัง Test Environment**

1. ไปที่ Test Environment (หรือ Environment ใหม่)
2. ไปที่ **Solutions**
3. คลิก **Import solution**
4. เลือกไฟล์ .zip
5. คลิก **Next**
6. ตรวจสอบ Package Details:
   - Package Type: Managed
   - Components
   - Dependencies (ถ้ามี)
7. คลิก **Import**
8. รอจนกว่าจะ Import เสร็จ
9. ตรวจสอบ Messages:
   - Success Messages
   - Warnings (ถ้ามี)
   - Errors (ถ้ามี)

**ส่วนที่ 5: ตรวจสอบการ Deploy**

1. เปิด Solution ที่ Import มา
2. ตรวจสอบ Components:
   - Canvas App ถูก Import หรือไม่
   - Flow ถูก Import หรือไม่
   - Version ถูกต้องหรือไม่

3. ทดสอบ Components:
   - เปิด Canvas App (ควรทำงานได้)
   - Run Flow (ควรทำงานได้)

**ส่วนที่ 6: สร้าง Deployment Documentation**

1. สร้างเอกสาร "Deployment Record":

**Deployment Information:**
- Source Environment: [ชื่อ Environment]
- Target Environment: [ชื่อ Environment]
- Solution Name: [ชื่อ Solution]
- Version: [Version Number]
- Deployment Date: [วันที่]
- Deployed By: [ชื่อผู้ Deploy]

**Components Deployed:**
- Canvas App: [ชื่อ App]
- Flow: [ชื่อ Flow]

**Deployment Notes:**
- Issues Encountered:
- Actions Taken:
- Post-Deployment Testing:
- Status: ✅ Success / ❌ Failed

**ผลลัพธ์ที่คาดหวัง:**
- Solution ถูก Deploy สำเร็จ
- เอกสาร Deployment ที่บันทึกการทำงาน
- ความเข้าใจกระบวนการ Deployment

