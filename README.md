# AIFinder Ultimate V2.4 — GitHub Pages Static Build

ชุดนี้จัดโครงสร้างให้พร้อมสำหรับ GitHub Pages โดย **ไม่มีโฟลเดอร์ `gh-pages/` ซ้อนอีกชั้น**

## ไฟล์ที่ต้องอยู่ระดับเดียวกับ `index.html`
- `index.html`
- `app.js`
- `embedded-data.js`

ไม่ต้องมี `Data/` หรือ `public/` เพิ่มสำหรับหน้า Static นี้ เพราะข้อมูลหลักถูกฝังไว้ใน `embedded-data.js` แล้ว

## GitHub Pages
1. สร้าง Repository
2. อัปโหลด `index.html`, `app.js`, `embedded-data.js` และ `README.md` ลง **หน้าแรกของ Repository**
3. Settings → Pages
4. Source: Deploy from a branch
5. Branch: `main` / `/ (root)`
6. Save แล้วรอ GitHub Pages สร้างเว็บไซต์

## ข้อจำกัด
ฟีเจอร์ Chat, Web Research, Projects, History, Docker Server และ Code Analyzer บางส่วนต้องใช้ Backend จริง จึงไม่สามารถทำงานครบด้วย GitHub Pages แบบ Static ได้
