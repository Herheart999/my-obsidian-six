---
title: "AWS vs Azure ต่างกันอย่างไร"
date: 2026-05-09
tags: [aws, azure, cloud-computing, comparison, cloud]
sources: ["Cloud HM - AWS vs Azure"]
confidence: high
---

# AWS vs Azure ต่างกันอย่างไร

Source: https://blog.cloudhm.co.th/aws-vs-azure/
Accessed: 2026-05-09

## สรุปย่อ

บทความเปรียบเทียบ Amazon Web Services (AWS) และ Microsoft Azure สองผู้ให้บริการคลาวด์รายใหญ่ที่สุดในโลก AWS เริ่มให้บริการก่อนในเดือนมีนาคม 2006 ส่วน Azure เริ่มในเดือนกุมภาพันธ์ 2010 AWS มีส่วนแบ่งตลาดประมาณ 40% ส่วน Azure ประมาณ 30% บทความวิเคราะห์ความแตกต่างใน 11 มิติหลักเพื่อช่วยองค์กรเลือกใช้งานให้เหมาะสม

## ประเด็นสำคัญ

### 1. Compute

- **AWS** — บริการพื้นฐานคือ EC2 ผู้ใช้สามารถสร้าง Instance (VM) จาก Image ที่ AWS มีให้หรือสร้าง Image เอง เลือก Spec ได้ตามต้องการ (CPU, Memory, Disk) และเลือกวาง Instance ได้ผ่าน Region และ Availability Zone
- **Azure** — บริการพื้นฐานคือ Virtual Machines สามารถสร้าง VM จาก Image ที่มีให้หรือทำ Image เอง ระบุ Core, Memory, Region และ AZ ได้เช่นกัน

### 2. Storage

- **AWS** — มี Temporary storage ที่จะหายไปเมื่อ Terminate EC2 มี Block Storage ชื่อ EBS แปะกับ EC2 เพื่อกันข้อมูลหาย และ Object Storage ชื่อ S3 รองรับการติดตั้ง Relational/NoSQL Database และ Big Data
- **Azure** — มี Temporary storage ใน Drive D (Windows) หรือ /dev/sdb (Linux) มี Block Storage ชื่อ Azure Disk Storage และ Object Storage ชื่อ Blob Storage รองรับ Database และ Big Data ผ่าน HDInsight

### 3. Network

- **AWS** — ใช้ Virtual Private Cloud (VPC) สร้าง Isolated network บน AWS Infrastructure ภายใน VPC สร้าง Subnet, Route table, Private IP range และ Network gateway ได้
- **Azure** — ใช้ Virtual Network (VNET) สร้าง Isolated network พร้อม Subnet, Route table, Private IP Address range และ Network Gateway
- ทั้งสองรายมี Solution เชื่อมต่อ On-Premise data center ผ่าน VPN หรือ Private Link

### 4. ราคา

**AWS** มี 3 แบบ:
- On demand — คิดตามการใช้งานจริง รายชั่วโมงถึงรายวินาที (Pay-as-you-go)
- Reserved — จองล่วงหน้า 1-3 ปี ถูกกว่า On demand 40-60%
- Spot — จ่ายตามราคาที่รับได้ ถูกกว่า On demand 50-90% แต่ Instance อาจถูก Terminate ถ้า Resource ไม่พอ

**Azure** มี 3 แบบเช่นกัน:
- Pay-as-you-go — คิดรายนาที/วินาที
- Reserved VM Instances — จอง 1-3 ปี
- Spot — ใช้ Resource ส่วนเกิน ถูกกว่า Pay-as-you-go สูงสุด 90% อาจถูก Terminate เมื่อ Resource ไม่พอ
- นอกจากนี้ยังมี Pre-paid ที่ต้องเติม Azure credit ก่อนสร้าง VM

### 5. Support

ทั้งสองรายมี Free Basic Plan สำหรับ Billing, Health check, White papers และ Best practice

**AWS** — มี 3 Plans คือ Developer, Business และ Enterprise
**Azure** — ราคา Support เป็น Flat rate รายเดือน มี Developer, Standard และ Professional Direct

### 6. Integration และ Open Source

- **AWS** — รองรับ Open Source หลากหลาย เช่น Jenkins, GitHub เหมาะกับ Linux
- **Azure** — สะดวกสำหรับผู้ใช้ Windows tools เช่น Visual Basic, SQL Database, Active Directory สามารถใช้ AD User เดียวกับ Microsoft 365 ได้ เหมาะกับ .NET Developer

### 7. Container และ Orchestration

- **AWS** — Support Docker, Kubernetes, Hadoop, Machine Learning, IoT, Mobile app และ HPC
- **Azure** — Support Hadoop ผ่าน HDInsight, Windows Server 2016 Docker, Windows/Linux containers และ Hyper-V containers

### 8. Compliance

- **AWS** — มี Certificate จำนวนมาก หน่วยงานรัฐบาล USA ใช้เยอะ เช่น ITAR, DISA, HIPAA, CJIS, FIPs
- **Azure** — Microsoft เคลมมี Certification มากกว่า 50 ใบ ส่วนใหญ่คล้าย AWS

### 9. User-friendly Console

- **AWS** — Feature หลากหลายมาก แต่ต้องใช้เวลาเรียนรู้
- **Azure** — ใช้งานง่ายสำหรับ Windows admin ไม่ต้องเรียนรู้มาก สามารถ Integrate Windows Server On-Premises กับ Cloud ทำ Hybrid Cloud ได้

### 10. License

- **AWS** — มี Option ซื้อ License ใหม่ Bundle กับ EC2/RDS หรือใช้ BYOL (Bring Your Own License) แต่ Microsoft License ต้องมี SA (Software Assurance) จึงใช้ได้
- **Azure** — มี License Mobility สำหรับ Application Server แต่ต้องเลือก Server ให้ตรงเงื่อนไข ถ้าไม่ตรงต้องจ่ายเพิ่ม

### 11. Hybrid Cloud

- **AWS** — มี Snowball edge สำหรับ transfer file ขึ้น AWS (รองรับ 100 TB), Partner กับ VMware, และ AWS Outposts สำหรับวาง Infrastructure ที่ Data Center ใกล้บริษัทเพื่อลด Latency
- **Azure** — เหมาะกับ Hybrid Cloud มาก รองรับ Azure StorSimple, Hybrid SQL Server, Azure VMware Solution และ Azure Stack ที่ใช้ฟังก์ชัน Public Cloud เกือบทั้งหมดบน On-Premises Data Center โดยจ่ายแบบ Pay-as-you-go

### สรุปการเลือกใช้งาน

ทั้งสอง Providers มีบริการคล้ายกันมาก ไม่มีใครด้อยกว่าหรือดีกว่าในภาพรวม การเลือกใช้ขึ้นอยู่กับความสะดวกและความถนัดของผู้ใช้ ทั้งสองรายมี Demo ให้ทดสอบได้

## คำสำคัญ

- AWS
- Azure
- EC2
- Virtual Machines
- VPC
- VNET
- Pay-as-you-go
- Reserved Instance
- Spot Instance
- Hybrid Cloud
- BYOL
- License Mobility

## ดูเพิ่ม

- [[09-aws-cloud]]
- [[03-devops]]
