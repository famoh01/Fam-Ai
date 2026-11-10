# AIFinder Ultimate V2.4 — GitHub Pages Static Build

รันบน **GitHub Pages** ได้เลย **ไม่ต้องมีโฟลเดอร์ `data/` และ `public/`** และไม่ต้องรัน Node server

## สิ่งที่รวมไว้ในโฟลเดอร์นี้

| ไฟล์ | รายละเอียด |
|------|------------|
| `index.html` | หน้าเว็บหลัก (script ชี้แบบ relative) |
| `app.js` | Frontend + โหมด static (ฝัง API mock + เรียก HF โดยตรง) |
| `embedded-data.js` | ข้อมูล products / links / insights + top ~300 โมเดล (ไม่ต้องมี data/) |

## วิธี Deploy บน GitHub Pages

1. สร้าง repo ใหม่ (หรือใช้ repo เดิม)
2. อัปโหลด **เฉพาะไฟล์ในโฟลเดอร์ `gh-pages/`** นี้ไปที่ root ของ repo หรือใส่ใน branch `gh-pages`
3. ไปที่ **Settings → Pages**
   - Source: Deploy from a branch
   - Branch: `main` (หรือ `gh-pages`) / folder: `/ (root)`
4. รอสักครู่ แล้วเปิด `https://<username>.github.io/<repo>/`

หรือใช้ GitHub Actions + `peaceiris/actions-gh-pages` ก็ได้

## ฟีเจอร์ที่ใช้งานได้ในโหมด Static

- Model Directory (embedded top models + **Live HF API** จากเบราว์เซอร์)
- AI Products browser
- All Links browser
- Stats / Compare / Prompt templates
- UI ครบทุกแท็บ

## ฟีเจอร์ที่ต้องใช้ Backend จริง

- Chat กับ OpenAI / Anthropic / Google (ต้องการ API key บน server)
- Web Research (fetch หน้าเว็บ)
- Docker Server Manager
- Projects / History ที่บันทึกบน server
- Code Analyzer ที่พึ่ง backend

ถ้าต้องการฟีเจอร์เต็ม ให้ใช้เวอร์ชัน Node (`npm start`) แล้ว deploy บน Render / Railway / VPS ตาม `RENDER-SETTINGS.txt`

## หมายเหตุ PORT

ในโหมด GitHub Pages **ไม่มี PORT** เพราะเป็น static hosting  
เวอร์ชัน Node ใช้ `process.env.PORT || 8080` และ bind `0.0.0.0` อยู่แล้ว (เหมาะกับ Render)

## ขนาด

- ไม่มี `models-seed.json` ขนาดใหญ่ (~3–24MB)
- ไฟล์ทั้งหมดในโฟลเดอร์นี้รวมกันประมาณ ~270KB
