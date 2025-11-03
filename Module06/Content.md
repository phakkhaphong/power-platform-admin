# Module 6: Proactive Monitoring & Tenant-Wide Analytics

## ภาพรวม

การกำกับดูแลที่มีประสิทธิภาพต้องการข้อมูลเชิงลึกที่ขับเคลื่อนด้วยข้อมูล โมดูลนี้แนะนำเครื่องมือติดตามและวิเคราะห์ที่มีอยู่ใน Power Platform เราจะสำรวจ Dashboards ในตัวที่ PPAC สำหรับติดตามการใช้งานและระบุความเสี่ยง ตลอดจนตัวเลือกขั้นสูง เช่น การเชื่อมต่อกับ Azure Application Insights สำหรับแอปที่สำคัญ

## เนื้อหา

### 1. Analytics Dashboards in PPAC

#### ทฤษฎี

**Analytics Dashboards ใน Power Platform Admin Center:**

Power Platform Admin Center มี Dashboards หลายแบบสำหรับการติดตามและวิเคราะห์:

**Usage Analytics**
- ติดตามการใช้งาน Apps, Flows, และ Connectors
- ระบุ Top Users และ Top Apps
- ตรวจสอบ Adoption Trends
- วิเคราะห์ Usage Patterns

**Capacity Analytics**
- ติดตาม Database Capacity
- ติดตาม File Capacity
- ติดตาม Log Capacity
- ตรวจสอบ Capacity Alerts

**Adoption Reports**
- ติดตาม Adoption Metrics
- ระบุ Active Users
- วิเคราะห์ Engagement Levels

**Orphaned Resources**
- ระบุ Apps ที่ไม่มีการใช้งาน
- ระบุ Flows ที่ไม่มีการใช้งาน
- ช่วยในการ Cleanup และ Cost Optimization

**Maker Analytics**
- ติดตาม Top Makers
- วิเคราะห์ Maker Productivity
- ระบุ Power Users

**อ้างอิง:**
- [Analytics in PPAC](https://learn.microsoft.com/en-us/power-platform/admin/analytics)

---

### 2. Accessing Audit Logs

#### ทฤษฎี

**Audit Logs คืออะไร?**

Audit Logs บันทึกกิจกรรมทั้งหมดที่เกิดขึ้นใน Power Platform สำหรับ:
- Security Compliance
- Troubleshooting
- Investigation
- Compliance Reporting

**ข้อมูลใน Audit Logs:**
- **Who:** ผู้ใช้ที่ทำกิจกรรม
- **What:** กิจกรรมที่ทำ
- **When:** เวลาและวันที่
- **Where:** Environment ที่เกิดกิจกรรม
- **Result:** ผลลัพธ์ (Success/Failure)

**ประเภทของ Audit Events:**
- User Activity (Login, Logout)
- Environment Creation/Deletion
- Security Role Changes
- Data Access
- App/Flow Creation/Modification
- DLP Policy Changes
- Solution Import/Export

**การเข้าถึง Audit Logs:**
- Microsoft Purview Compliance Portal
- Power Platform Admin Center (บางส่วน)
- PowerShell (สำหรับ Export)

**อ้างอิง:**
- [Audit Logs](https://learn.microsoft.com/en-us/power-platform/admin/logging-powerapps)
- [Microsoft Purview](https://learn.microsoft.com/en-us/purview/)

---

### 3. Advanced Monitoring with Application Insights

#### ทฤษฎี

**Azure Application Insights คืออะไร?**

Azure Application Insights เป็น Service สำหรับ Application Performance Monitoring (APM) และ Telemetry ที่สามารถเชื่อมต่อกับ Power Platform เพื่อ:
- Real-time Monitoring
- Error Tracking
- Performance Analytics
- Custom Telemetry

**ประโยชน์:**
- ตรวจสอบ Performance ของ Apps/Flows แบบ Real-time
- ตรวจจับ Errors และ Exceptions
- วิเคราะห์ Usage Patterns
- สร้าง Custom Dashboards
- ตั้งค่า Alerts

**การเชื่อมต่อกับ Power Platform:**
- ใช้ Custom Telemetry ใน Canvas Apps
- ใช้ Flow Actions สำหรับ Logging
- ใช้ Application Insights Connector

**Use Cases:**
- Mission-Critical Apps
- High-Traffic Applications
- Applications ที่ต้องการ Detailed Monitoring
- Applications ที่ต้องการ Custom Metrics

**อ้างอิง:**
- [Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)
- [Power Platform and Application Insights](https://learn.microsoft.com/en-us/power-platform/admin/monitor-solutions)

---

## สรุป Module 6

### จุดสำคัญที่ควรจำ

1. **Analytics Dashboards ให้ข้อมูลเชิงลึก** - ใช้เพื่อติดตามการใช้งานและระบุ Orphaned Resources

2. **Audit Logs สำคัญสำหรับ Compliance** - บันทึกกิจกรรมทั้งหมดสำหรับ Security และ Compliance

3. **Application Insights สำหรับ Advanced Monitoring** - ใช้สำหรับ Applications ที่ต้องการ Detailed Monitoring

### คำถามทบทวน

1. Analytics Dashboards ใน PPAC มีอะไรบ้าง และใช้ประโยชน์อย่างไร?
2. Audit Logs มีประโยชน์อย่างไรสำหรับ Security และ Compliance?
3. เมื่อไหร่ควรใช้ Application Insights แทน Built-in Analytics?

### ขั้นตอนถัดไป

- เตรียมความพร้อมสำหรับ Module 7: Advanced Governance: CoE Kit vs. Managed Environments
- ทบทวน Analytics และ Monitoring Strategy ของ Organization
- วางแผนการติดตามและวิเคราะห์สำหรับ Environments ใหม่

