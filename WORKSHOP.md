# Workshop: GitHub + Cloudflare + OpenCode

## 🎯 สิ่งที่จะได้เรียนรู้
- เชื่อม GitHub กับ Cloudflare Pages
- Deploy เว็บอัตโนมัติ (CI/CD)

---

## 📋 ขั้นตอน

### 1. สร้าง GitHub Repository

1. ไปที่ https://github.com/new
2. ตั้งชื่อ เช่น `my-first-web`
3. เลือก **Public**
4. Click **Create repository**

### 2. สร้างเว็บง่ายๆ

สร้างไฟล์ `index.html`:

```html
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>My First Web</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #667eea, #764ba2);
      color: white;
    }
    h1 { font-size: 3rem; }
  </style>
</head>
<body>
  <h1>Hello World! 🌍</h1>
</body>
</html>
```

### 3. Push ขึ้น GitHub

```bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/my-first-web.git
cd my-first-web

# สร้างไฟล์
# (วาง index.html ที่สร้างไว้ข้างบน)

# Commit & Push
git add .
git commit -m "Add first website"
git push origin main
```

### 4. เชื่อม Cloudflare Pages

1. ไปที่ https://pages.cloudflare.com
2. Click **Create a project**
3. เลือก **Connect to Git**
4. เลือก repository ที่สร้าง
5. **Build settings:**
   - Production branch: `main`
   - Build output directory: `/` (root)
6. Click **Save and Deploy**

### 5. ✅ เสร็จ!

จะได้ URL เช่น:
```
https://my-first-web.pages.dev
```

---

## 🔄 เมื่อมีการเปลี่ยนแปลง

เมื่อใดก็ตามที่ push code ใหม่ขึ้น GitHub:
1. Cloudflare จะ build อัตโนมัติ
2. Deploy ให้เอง

---

## 📚 คำสั่ง Git พื้นฐาน

```bash
git clone <url>     # ดาวน์โหลด repo
git add .           # เพิ่มไฟล์ที่แก้ไข
git commit -m "ข้อความ"  # บันทึกการแก้ไข
git push            # ส่งขึ้น GitHub
git pull            # ดึงการแก้ไขล่าสุด
```

---

## ❓ คำถามที่พบบ่อย

**Q: ทำไม deploy ไม่สำเร็จ?**
A: ตรวจสอบ Build logs ใน Cloudflare dashboard

**Q: เปลี่ยนชื่อ domain ได้ไหม?**
A: ได้ใน Cloudflare Pages → Custom domains

**Q: ใช้ domain ตัวเองได้ไหม?**
A: ได้ ใน Settings → Custom domains

---

## 🎉 สำเร็จแล้ว!

ตอนนี้มีเว็บไซต์ของตัวเองแล้ว!

**ขั้นต่อไป:**
- ลองเพิ่ม CSS, JavaScript
- ลองใช้ OpenCode ช่วยสร้างเว็บ
- เชื่อมกับ LINE Bot
