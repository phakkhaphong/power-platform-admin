# Module 6: แบบฝึกหัดปฏิบัติ
## Proactive Monitoring & Tenant-Wide Analytics

---

## แบบฝึกหัด 6.1: เข้าถึงและวิเคราะห์ Analytics Dashboard ใน PPAC

**วัตถุประสงค์:** เข้าถึงและวิเคราะห์ Analytics Dashboard ใน PPAC

**ขั้นตอน:**

**ส่วนที่ 1: เข้าถึง Analytics Dashboard**

1. เข้าสู่ Power Platform Admin Center
2. ไปที่ **Analytics** (เมนูด้านซ้าย)
3. สำรวจส่วนต่างๆ:

   **Usage Analytics:**
   - ไปที่ **Analytics** > **Usage**
   - ตรวจสอบ:
     - Apps: จำนวน Apps ที่ใช้งาน
     - Flows: จำนวน Flows ที่ใช้งาน
     - Users: จำนวน Users ที่ใช้งาน
     - Usage Trends: กราฟแสดงแนวโน้ม

   **Capacity Analytics:**
   - ไปที่ **Analytics** > **Capacity**
   - ตรวจสอบ:
     - Database Capacity: การใช้งานฐานข้อมูล
     - File Capacity: การใช้งานไฟล์
     - Log Capacity: การใช้งาน Logs
     - Capacity Trends: กราฟแสดงแนวโน้ม

**ส่วนที่ 2: วิเคราะห์ Usage Data**

1. **Apps Usage Analysis:**
   - ไปที่ **Analytics** > **Usage** > **Apps**
   - บันทึกข้อมูล:
     - Top 5 Apps by Usage
     - Apps ที่ไม่มีการใช้งาน (Orphaned Apps)
     - Usage Trends (เพิ่มขึ้น/ลดลง)
     - Active Users per App

2. **Flows Usage Analysis:**
   - ไปที่ **Analytics** > **Usage** > **Flows**
   - บันทึกข้อมูล:
     - Top 5 Flows by Runs
     - Flows ที่ไม่มีการใช้งาน (Orphaned Flows)
     - Success Rate
     - Failed Runs

3. **Users Analysis:**
   - ไปที่ **Analytics** > **Usage** > **Users**
   - บันทึกข้อมูล:
     - Top 5 Active Users
     - Users ที่ไม่ใช้งาน
     - User Adoption Rate

**ส่วนที่ 3: ระบุ Orphaned Resources**

1. ไปที่ **Analytics** > **Resources**
2. ตรวจสอบ Orphaned Resources:
   - Apps ที่ไม่มีการใช้งาน (30+ วัน)
   - Flows ที่ไม่มีการใช้งาน (30+ วัน)
   - Connectors ที่ไม่มีการใช้งาน

3. สร้างรายการ "Orphaned Resources for Cleanup":
   - ชื่อ Resource
   - ประเภท (App/Flow/Connector)
   - วันใช้งานล่าสุด
   - Owner
   - แนะนำ (Delete/Archive/Keep)

**ส่วนที่ 4: สร้างรายงาน Analytics**

1. สร้างเอกสาร "Analytics Report - [Date]":
   - Executive Summary
   - Top Performers
   - Orphaned Resources
   - Capacity Usage
   - Trends
   - Recommendations

**ผลลัพธ์ที่คาดหวัง:**
- ความคุ้นเคยกับ Analytics Dashboards
- รายงาน Analytics ที่มีประโยชน์
- ความเข้าใจข้อมูลการใช้งาน

---

## แบบฝึกหัด 6.2: เข้าถึงและวิเคราะห์ Audit Logs

**วัตถุประสงค์:** เข้าถึงและวิเคราะห์ Audit Logs

**ขั้นตอน:**

**ส่วนที่ 1: เข้าถึง Audit Logs**

1. เข้าสู่ [Microsoft Purview Compliance Portal](https://compliance.microsoft.com/)
2. ไปที่ **Audit** (เมนูด้านซ้าย)
3. (ถ้าเป็นครั้งแรก) อาจต้องเปิดใช้งาน Audit Logging:
   - ตรวจสอบว่ามีสิทธิ์เข้าถึงหรือไม่
   - ถ้าไม่มี อาจต้องติดต่อผู้ดูแลระบบ

**ส่วนที่ 2: ค้นหา Audit Records**

1. ไปที่ **Audit** > **Search**
2. ตั้งค่าการค้นหา:

   **Date Range:**
   - เลือกช่วงเวลา: 7 วันล่าสุด หรือตามต้องการ

   **Activities:**
   - เลือก "Power Platform activities" หรือ
   - เลือกกิจกรรมเฉพาะ เช่น:
     - Create environment
     - Modify security roles
     - Export solution
     - Create app

   **Users:**
   - (ถ้าต้องการ) เลือก User เฉพาะ
   - หรือปล่อยว่างเพื่อดูทั้งหมด

3. คลิก **Search**
4. รอผลการค้นหา (อาจใช้เวลาหลายนาที)

**ส่วนที่ 3: วิเคราะห์ Audit Records**

1. ตรวจสอบผลลัพธ์:
   - จำนวน Records ที่พบ
   - รายละเอียดของแต่ละ Record:
     - Date/Time
     - User
     - Activity
     - Item
     - Result (Success/Failure)

2. **วิเคราะห์ Security Events:**
   - ค้นหา "Security role changes"
   - ระบุว่าใครเปลี่ยน Security Roles
   - ตรวจสอบว่าการเปลี่ยนแปลงถูกต้องหรือไม่

3. **วิเคราะห์ Environment Events:**
   - ค้นหา "Environment creation"
   - ระบุว่าใครสร้าง Environments
   - ตรวจสอบว่าตาม Policy หรือไม่

4. **วิเคราะห์ Data Access:**
   - ค้นหา "Data access events"
   - ระบุว่าใครเข้าถึงข้อมูล
   - ตรวจสอบว่ามีการเข้าถึงที่ผิดปกติหรือไม่

**ส่วนที่ 4: Export Audit Logs**

1. หลังจากค้นหาแล้ว คลิก **Export results**
2. เลือก Format:
   - CSV (สำหรับ Excel)
   - JSON (สำหรับ Analysis Tools)
3. ดาวน์โหลดไฟล์

**ส่วนที่ 5: สร้างรายงาน Audit**

1. สร้างเอกสาร "Audit Report - [Date Range]":
   - Search Criteria
   - Summary
   - Key Findings
   - Anomalies/Concerns
   - Recommendations

**ผลลัพธ์ที่คาดหวัง:**
- ความเข้าใจการเข้าถึงและใช้ Audit Logs
- ความสามารถในการวิเคราะห์ Audit Data
- รายงาน Audit ที่มีประโยชน์

**หมายเหตุ:** 
- Audit Logs อาจมี Latency (ความล่าช้า)
- บาง Organizations อาจมี Retention Policy สำหรับ Audit Logs
- ต้องมีสิทธิ์ที่เหมาะสมในการเข้าถึง Audit Logs

---

## แบบฝึกหัด 6.3: เชื่อมต่อ Power Platform Environment กับ Azure Application Insights

**วัตถุประสงค์:** เชื่อมต่อ Power Platform Environment กับ Azure Application Insights (Conceptual)

**หมายเหตุ:** Exercise นี้เป็นแบบ Conceptual เนื่องจากต้องมี Azure Subscription และ Application Insights Resource

**ขั้นตอน:**

**ส่วนที่ 1: สร้าง Azure Application Insights Resource**

1. เข้าสู่ [Azure Portal](https://portal.azure.com/)
2. คลิก **+ Create a resource**
3. ค้นหา "Application Insights"
4. คลิก **Create**
5. กรอกข้อมูล:
   - **Name:** "PowerPlatform-Monitoring-[YourName]"
   - **Resource Group:** สร้างใหม่หรือเลือกที่มี
   - **Region:** เลือก Region ที่เหมาะสม
   - **Application Type:** Web
6. คลิก **Review + create**
7. คลิก **Create**
8. รอจนกว่าจะสร้างเสร็จ

**ส่วนที่ 2: รับ Instrumentation Key**

1. ไปที่ Application Insights Resource ที่สร้าง
2. ไปที่ **Overview**
3. คัดลอก **Instrumentation Key** หรือ **Connection String**
4. เก็บไว้สำหรับใช้ในขั้นตอนถัดไป

**ส่วนที่ 3: ใช้ Custom Telemetry ใน Canvas App**

1. เปิด Canvas App ใน Power Apps Studio
2. เพิ่ม Custom Telemetry (ใช้ Flow หรือ Custom Connector)

**ส่วนที่ 4: สร้าง Dashboard และ Alerts**

1. ใน Application Insights ไปที่ **Dashboard**
2. เพิ่ม Widgets:
   - Custom Events
   - Exceptions
   - Performance Metrics

3. ตั้งค่า Alerts:
   - ไปที่ **Alerts** > **New alert rule**
   - ตั้งค่า Alert Condition และ Action

**ส่วนที่ 5: สร้างเอกสาร Configuration**

1. สร้างเอกสาร "Application Insights Integration Guide":
   - Azure Resources
   - Integration Points
   - Monitoring Strategy
   - Cost Estimation

**ผลลัพธ์ที่คาดหวัง:**
- ความเข้าใจการเชื่อมต่อ Application Insights
- Configuration Guide สำหรับการใช้งานจริง
- ความเข้าใจประโยชน์ของ Advanced Monitoring

**หมายเหตุ:** 
- การใช้ Application Insights มีค่าใช้จ่าย
- ควรประเมิน Cost ก่อนใช้งานจริง
- ใช้กับ Mission-Critical Applications เป็นหลัก

