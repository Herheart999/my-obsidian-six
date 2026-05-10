---
title: คำสั่ง Linux พื้นฐาน
date: 2026-05-10
tags:
  - linux
  - commandline
  - beginner
  - shell
  - terminal
sources:
  - Linux Journey
  - Explain Shell
confidence: high
---

# คำสั่ง Linux พื้นฐาน

## สรุปย่อ

Linux command line (หรือ Terminal/Shell) คืออินเตอร์เฟซข้อความที่ใช้สื่อสารกับระบบปฏิบัติการ Linux ผู้ใช้พิมพ์คำสั่งลงใน terminal เพื่อควบคุมไฟล์ โฟลเดอร์ กระบวนการ และระบบต่าง ๆ โดยตรง การรู้คำสั่งพื้นฐานเป็นทักษะสำคัญสำหรับการพัฒนาซอฟต์แวร์ ดูแลระบบ (System Administration) รวมถึงงานด้านความปลอดภัยและคลาวด์

## ประเด็นสำคัญ

### 1. การเดินทางในระบบไฟล์ (Navigation)

| คำสั่ง | ความหมาย | ตัวอย่าง |
|---|---|---|
| `pwd` | แสดงตำแหน่งปัจจุบัน (Print Working Directory) | `pwd` |
| `ls` | แสดงรายการไฟล์ (List) | `ls`, `ls -la`, `ls -lh` |
| `cd` | เปลี่ยน directory (Change Directory) | `cd /home`, `cd ..`, `cd ~` |

> 💡 **Tips:** ใช้ `Tab` เพื่อ auto-complete ชื่อไฟล์หรือโฟลเดอร์

### 2. การจัดการไฟล์และโฟลเดอร์

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `mkdir` | สร้างโฟลเดอร์ | `mkdir myfolder`, `mkdir -p a/b/c` |
| `touch` | สร้างไฟล์เปล่า / อัปเดตเวลา | `touch file.txt` |
| `cp` | คัดลอกไฟล์/โฟลเดอร์ | `cp file.txt backup.txt`, `cp -r folder/ newfolder/` |
| `mv` | ย้ายหรือเปลี่ยนชื่อ | `mv old.txt new.txt`, `mv file.txt /tmp/` |
| `rm` | ลบไฟล์ | `rm file.txt`, `rm -r folder/`, `rm -rf folder/` |
| `rmdir` | ลบโฟลเดอร์ว่าง | `rmdir emptyfolder` |

> ⚠️ **ระวัง!** `rm -rf` ลบได้ทุกอย่างโดยไม่ถาม ใช้ด้วยความระมัดระวัง!

### 3. การอ่านเนื้อหาไฟล์

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `cat` | แสดงเนื้อหาไฟล์ทั้งหมด | `cat file.txt` |
| `less` | อ่านแบบ scroll ได้ (กด `q` ออก) | `less largefile.log` |
| `more` | คล้าย less แต่กด spacebar | `more file.txt` |
| `head` | แสดง 10 บรรทัดแรก | `head file.txt`, `head -n 5 file.txt` |
| `tail` | แสดง 10 บรรทัดสุดท้าย | `tail file.txt`, `tail -f file.log` |

> 💡 **Tips:** ใน `less` กด `/คำ` เพื่อ search, กด `n` ไปต่อ, `N` ย้อนกลับ

### 4. การจัดการ Permissions (สิทธิ์ไฟล์)

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `chmod` | เปลี่ยนสิทธิ์ไฟล์ | `chmod 755 script.sh`, `chmod +x file` |
| `chown` | เปลี่ยนเจ้าของไฟล์ | `sudo chown user:group file.txt` |

**โครงสร้าง permission (rwx):**
```
rwx rwx rwx
│   │   └── others (คนอื่น)
│   └────── group (กลุ่ม)
└────────── owner (เจ้าของ)

r = read (4), w = write (2), x = execute (1)
```

- `chmod 755 file` = `rwxr-xr-x`
- `chmod 644 file` = `rw-r--r--`
- `chmod +x file` = เพิ่มสิทธิ์ execute

### 5. ระบบและ Process

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `ps` | แสดง process ที่รันอยู่ | `ps aux` |
| `top` | แสดง process แบบ real-time | `top` (กด `q` ออก) |
| `htop` | top แบบสวยงาม (ต้องลงแยก) | `htop` |
| `kill` | ปิด process | `kill 1234`, `kill -9 1234` |
| `df` | ดูพื้นที่ดิสก์ | `df -h` |
| `du` | ดูขนาดไฟล์/โฟลเดอร์ | `du -sh folder/` |
| `free` | ดูการใช้ RAM | `free -h` |
| `uptime` | ดูเวลาที่ระบบทำงาน | `uptime` |

### 6. ผู้ใช้และสิทธิ์ผู้ดูแล (User & Sudo)

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `whoami` | แสดงชื่อผู้ใช้ปัจจุบัน | `whoami` |
| `id` | แสดง ID ผู้ใช้และกลุ่ม | `id` |
| `sudo` | รันคำสั่งในฐานะ superuser | `sudo apt update` |
| `su` | สลับไปใช้ user อื่น | `su - username` |
| `passwd` | เปลี่ยนรหัสผ่าน | `passwd` |

### 7. ค้นหาและ Text Processing

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `grep` | ค้นหาข้อความในไฟล์ | `grep "error" log.txt`, `grep -i "error" *.log` |
| `find` | ค้นหาไฟล์ | `find . -name "*.txt"` |
| `echo` | แสดงข้อความ | `echo "Hello"`, `echo $PATH` |
| `wc` | นับ บรรทัด/คำ/ตัวอักษร | `wc -l file.txt` |
| `sort` | เรียงลำดับข้อมูล | `sort file.txt`, `sort -r file.txt` |
| `uniq` | กรองข้อมูลซ้ำ | `sort file.txt | uniq` |

**Piping (`|`):** ส่ง output ของคำสั่งหนึ่งเป็น input ของอีกคำสั่ง
```bash
cat log.txt | grep "ERROR" | sort | uniq -c
```

### 8. Text Editors

| คำสั่ง | ใช้ทำอะไร |
|---|---|
| `nano` | Text editor ง่าย ๆ เหมาะกับมือใหม่ |
| `vim` / `vi` | Text editor ระดับปรมาจารย์ (ต้องฝึก) |

**Nano shortcuts:**
- `Ctrl+O` → บันทึก
- `Ctrl+X` → ออก
- `Ctrl+K` → ตัดบรรทัด
- `Ctrl+U` → วางบรรทัด

### 9. การขอความช่วยเหลือ

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `man` | คู่มือ (Manual page) | `man ls`, `man grep` |
| `--help` | แสดงวิธีใช้สั้น ๆ | `ls --help`, `cp --help` |
| `which` | หาตำแหน่งคำสั่ง | `which python` |
| `history` | แสดงประวัติคำสั่ง | `history`, `history | grep "apt"` |

### 10. อื่น ๆ ที่มักใช้บ่อย

| คำสั่ง | ใช้ทำอะไร | ตัวอย่าง |
|---|---|---|
| `clear` | ล้างหน้าจอ | `clear` หรือกด `Ctrl+L` |
| `exit` | ออกจาก terminal | `exit` |
| `alias` | สร้างชื่อย่อคำสั่ง | `alias ll='ls -la'` |
| `date` | แสดงวันและเวลา | `date` |
| `cal` | แสดงปฏิทิน | `cal` |
| `tree` | แสดงโครงสร้างไฟล์แบบต้นไม้ | `tree` (อาจต้องลงแยก) |

## จุดที่ควรจำ

- **`rm -rf` อันตรายสูง:** ลบไฟล์และโฟลเดอร์ได้ทุกอย่างโดยไม่ถามยืนยัน ใช้ด้วยความระมัดระวังอย่างยิ่ง
- **Piping (`|`) คืออะไร:** ส่ง output ของคำสั่งก่อนหน้าเป็น input ของคำสั่งถัดไป ช่วย chain คำสั่งได้ยืดหยุ่น
- **`sudo` ใช้ด้วยควระวัง:** รันคำสั่งในฐานะ superuser มีอำนาจเปลี่ยนแปลงระบบทั้งหมด
- **`tail -f` ดู log แบบ real-time:** เหมาะกับการ monitor log file ที่กำลังเขียนอยู่ เช่น server logs หรือ application logs
- **`chmod +x` ทำไฟล์รันได้:** เพิ่มสิทธิ์ execute ให้ script สามารถรันได้

## การประยุกต์ใช้งาน

- **Server Administration:** จัดการไฟล์ ดู process ตรวจสอบ disk space จัดการ user บน Linux servers
- **DevOps Automation:** เขียน shell scripts เพื่อ automate deployment, backup, monitoring (ดูเพิ่มใน [[03-devops]] และ [[10-devops-quick-reference]])
- **Security Analysis:** วิเคราะห์ logs ด้วย `grep` และ `awk`, ตรวจสอบ file permissions, หา process ที่น่าสงสัย (ดูเพิ่มใน [[02-cyber-security]])
- **Cloud Management:** จัดการ AWS EC2 instances หรือ cloud VMs ที่รัน Linux (ดูเพิ่มใน [[09-aws-cloud]])
- **Development Workflow:** ใช้ Git, Docker, และ development tools ผ่าน terminal ใน [[07-development-pipeline]]

## คำสำคัญ

- CLI (Command Line Interface)
- Shell / Bash
- Pipe (`|`)
- Redirect (`>`, `>>`)
- Permission bits
- Process / PID
- Sudo / Superuser
- Regex (Regular Expression)
- Shebang (`#!/bin/bash`)

## ดูเพิ่ม

- [[02-cyber-security]]
- [[03-devops]]
- [[07-development-pipeline]]
- [[09-aws-cloud]]
- [[10-devops-quick-reference]]
- [Linux Journey](https://linuxjourney.com)
- [Explain Shell](https://explainshell.com)
- [Bandit Wargames](https://overthewire.org/wargames/bandit/)
