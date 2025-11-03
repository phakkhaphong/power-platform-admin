# Module 7: Advanced Governance: CoE Kit vs. Managed Environments

## ภาพรวม

โมดูลสุดท้ายนี้กล่าวถึงตัวเลือกเชิงกลยุทธ์ระหว่างเครื่องมือกำกับดูแลที่มีประสิทธิภาพสองตัว: CoE Starter Kit และ Managed Environments เราจะเปรียบเทียบฟีเจอร์, ความพยายามในการตั้งค่า, และผลกระทบด้าน Licensing การเข้าใจ Trade-off นี้เป็นสิ่งสำคัญสำหรับการตัดสินใจที่ถูกต้องเกี่ยวกับอนาคตของการกำกับดูแลในองค์กรของคุณ

## เนื้อหา

### 1. The Center of Excellence (CoE) Starter Kit

#### ทฤษฎี

**CoE Starter Kit คืออะไร?**

CoE Starter Kit เป็นชุดเครื่องมือฟรีและ Open Source จาก Microsoft สำหรับการกำกับดูแล Power Platform ที่ครอบคลุม มันประกอบด้วย:
- **Apps** - สำหรับการจัดการและรายงาน
- **Flows** - สำหรับการทำ Automated Governance
- **Reports** - สำหรับ Analytics และ Insights
- **Documentation** - สำหรับการใช้งานและ Best Practices

**Components หลัก:**

1. **Admin - Command Center**
   - จัดการ Environments, Apps, Flows
   - ติดตาม Adoption
   - จัดการ Governance Policies

2. **Developer Compliance Center**
   - ตรวจสอบ Compliance ของ Apps/Flows
   - ติดตาม DLP Policy Violations
   - จัดการ Certifications

3. **Governance**
   - Automated Governance Flows
   - Notification Systems
   - Approval Workflows

4. **Nurture**
   - Training Resources
   - Best Practices
   - Community Engagement

5. **Inventory**
   - Automatic Inventory ของ Resources
   - Dependency Tracking
   - Impact Analysis

**ข้อดี:**
- ✅ ฟรี (Free)
- ✅ Feature-Rich และ Comprehensive
- ✅ Customizable
- ✅ Community Support
- ✅ Open Source

**ข้อเสีย:**
- ❌ ต้อง Setup และ Maintain เอง
- ❌ ต้องการ Technical Knowledge
- ❌ อาจซับซ้อนสำหรับ Organizations เล็ก
- ❌ ต้องมี Dedicated Resources สำหรับ Maintenance

**อ้างอิง:**
- [CoE Starter Kit](https://learn.microsoft.com/en-us/power-platform/guidance/coe/starter-kit)
- [CoE Documentation](https://learn.microsoft.com/en-us/power-platform/guidance/coe/)

---

### 2. Managed Environments

#### ทฤษฎี

**Managed Environments คืออะไร?**

Managed Environments เป็น Premium Feature ที่ Microsoft สร้างไว้ในตัวสำหรับการกำกับดูแล Power Platform ที่ Simplified และ Out-of-the-Box

**Features หลัก:**

1. **Sharing Limits**
   - จำกัดจำนวน Users ที่ Apps/Flows สามารถ Share ได้
   - ช่วยป้องกันการ Share แบบไม่จำกัด

2. **Solution Checker**
   - ตรวจสอบ Solutions ก่อน Deployment
   - Enforce Best Practices

3. **Custom Analytics**
   - Analytics แบบ Custom
   - Enhanced Reporting

4. **Data Policies**
   - Enhanced DLP Policy Management
   - Better Policy Enforcement

5. **Limits and Controls**
   - Resource Limits
   - API Limits
   - Better Control

**ข้อดี:**
- ✅ Built-in และ Ready to Use
- ✅ ไม่ต้อง Setup ซับซ้อน
- ✅ Microsoft Maintained
- ✅ Integrated กับ PPAC
- ✅ Simplified Governance

**ข้อเสีย:**
- ❌ Premium Licensing Required
- ❌ ต้องมี Power Apps Premium per User License หรือ Power Platform per App License สำหรับทุก Users ที่ใช้ Managed Environment
- ❌ Feature Set อาจน้อยกว่า CoE Kit
- ❌ Customization จำกัด

**Licensing Requirements:**
- **Power Apps Premium per User License** - สำหรับทุก Users ที่ใช้งาน Apps ใน Managed Environment
- หรือ **Power Platform per App License** - สำหรับ Users ที่ใช้ Apps ใน Managed Environment
- **หมายเหตุ:** Licensing Requirements มีผลกระทบต่อ Cost อย่างมาก

**อ้างอิง:**
- [Managed Environments](https://learn.microsoft.com/en-us/power-platform/admin/managed-environment-overview)
- [Managed Environments Licensing](https://learn.microsoft.com/en-us/power-platform/admin/managed-environment-licensing)

---

### 3. Strategic Comparison and Licensing Impact

#### ทฤษฎี

**การเปรียบเทียบเชิงกลยุทธ์:**

**CoE Starter Kit:**
- **Investment:** Time และ Technical Resources
- **Ongoing Cost:** Maintenance Time
- **Flexibility:** สูงมาก
- **Scalability:** ดี (ขึ้นอยู่กับการ Setup)

**Managed Environments:**
- **Investment:** Premium Licensing
- **Ongoing Cost:** Licensing (Recurring)
- **Flexibility:** จำกัด
- **Scalability:** ดี (Built-in)

**Hybrid Approach:**
- ใช้ CoE Kit สำหรับ Comprehensive Governance
- ใช้ Managed Environments สำหรับ Production Environments
- Combine Benefits ของทั้งสอง

**Decision Factors:**
1. **Budget** - มี Budget สำหรับ Premium Licensing หรือไม่?
2. **Technical Resources** - มี Resources สำหรับ Setup/Maintain CoE หรือไม่?
3. **Scale** - Organization มีขนาดเท่าใด?
4. **Requirements** - ต้องการ Features อะไรบ้าง?
5. **Timeline** - ต้องการ Solution แบบ Immediate หรือสามารถ Setup ได้?

**อ้างอิง:**
- [Governance Comparison](https://learn.microsoft.com/en-us/power-platform/admin/managed-environment-overview)

---

## สรุป Module 7

### จุดสำคัญที่ควรจำ

1. **CoE Kit ฟรีแต่ซับซ้อน** - เหมาะสำหรับ Organizations ที่ต้องการ Comprehensive Governance และมี Technical Resources

2. **Managed Environments ง่ายแต่ต้องจ่าย** - เหมาะสำหรับ Organizations ที่ต้องการ Simple Solution และมี Budget สำหรับ Premium Licensing

3. **การตัดสินใจต้องพิจารณาหลายปัจจัย** - Budget, Resources, Requirements, Timeline

### คำถามทบทวน

1. CoE Starter Kit และ Managed Environments ต่างกันอย่างไร?
2. Licensing Requirements ของ Managed Environments มีผลกระทบต่อ Cost อย่างไร?
3. Organization ของคุณควรเลือกใช้ Solution แบบใด?

### ขั้นตอนถัดไป

- ทบทวน Governance Strategy ของ Organization
- ประเมิน Budget และ Resources
- วางแผน Implementation ของ Solution ที่เลือก
- เริ่ม Implementation ตามแผน

---

## สรุปหลักสูตร Power Platform Administration

หลักสูตรนี้ครอบคลุม:

1. **Foundational Governance** - Licensing, Admin Roles, PPAC Navigation
2. **Environment Architecture** - Strategy, Default Environment, Security
3. **Solutions & ALM** - Solutions, Deployment, ALM Practices
4. **Security Framework** - Multi-layered Security, Dataverse Security, Tenant Settings
5. **DLP Policies** - Data Loss Prevention, Multi-layered Strategy
6. **Monitoring & Analytics** - PPAC Analytics, Audit Logs, Application Insights
7. **Advanced Governance** - CoE Kit vs. Managed Environments

**Next Steps:**
- ประยุกต์ความรู้ที่ได้เรียนรู้
- เริ่ม Implementation ใน Organization
- ต่อยอดความรู้ด้วย Advanced Topics
- เข้าร่วม Community และ Share Experiences

