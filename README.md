# ✦ Genshin Companion — ตัวช่วยเล่น Genshin Impact

เว็บแอปภาษาไทยสำหรับช่วยวางแผนการเล่น Genshin Impact ทำจาก HTML + CSS + JS ล้วนๆ
ไม่มี dependency ภายนอก (นอกจาก Google Fonts) เปิดไฟล์เดียวก็ใช้งานได้เลย

## ฟีเจอร์หลัก

| หน้า | ฟีเจอร์ |
|------|---------|
| 📅 **วันนี้** | Resin Tracker (บันทึก localStorage), Daily Checklist รีเซ็ตอัตโนมัติทุกวัน, โดเมนที่เปิดตามวัน, Wish Pity Tracker |
| 👤 **ตัวละคร** | แสดงตัวละครทั้งหมด, กรองตามธาตุ/มี/ไม่มี, ติ๊กเพิ่ม/ลบตัวละครที่ตัวเองมี (บันทึก localStorage) |
| ⚔️ **ทีม** | แนะนำ Team Comp 6 ทีม, แสดงสีเขียวเมื่อมีตัวละครครบ, บอกว่าขาดใครถ้ายังไม่ครบ |
| 🗺️ **แผนที่** | SVG Map ของ Teyvat ทั้ง 6 ภูมิภาค, คลิกจุดเพื่อดูวัตถุดิบ, กรองตามภูมิภาค |
| 📖 **บิลด์** | Build Guide สำหรับ 8 ตัวละครยอดนิยม (Artifact, Weapon, Stats, Tips) |

---

## วิธี Deploy บน GitHub Pages

### ขั้นตอนที่ 1 — สร้าง Repository

1. ไปที่ [github.com](https://github.com) แล้ว Login
2. กดปุ่ม **New** (สีเขียว) ที่มุมบนขวา
3. ตั้งชื่อ Repository เป็น `genshin-companion` (หรือชื่ออื่น)
4. ตั้งเป็น **Public** (จำเป็นสำหรับ GitHub Pages ฟรี)
5. กด **Create repository**

### ขั้นตอนที่ 2 — อัพโหลดไฟล์

**วิธีที่ 1 — ผ่านหน้าเว็บ GitHub (ง่ายที่สุด)**

```
1. ใน repository ที่สร้างใหม่ กด "uploading an existing file"
2. ลากไฟล์ index.html และ README.md ใส่
3. กด "Commit changes"
```

**วิธีที่ 2 — ผ่าน Git Command Line**

```bash
git clone https://github.com/YOUR_USERNAME/genshin-companion.git
cd genshin-companion
# copy ไฟล์ index.html และ README.md ลงโฟลเดอร์นี้
git add .
git commit -m "Initial commit: Genshin Companion App"
git push origin main
```

### ขั้นตอนที่ 3 — เปิดใช้ GitHub Pages

1. ใน Repository ไปที่ **Settings** (เฟืองด้านบน)
2. เลือกเมนู **Pages** ทางซ้าย
3. ใต้ "Branch" เลือก **main** แล้วโฟลเดอร์ **/ (root)**
4. กด **Save**
5. รอประมาณ 1–3 นาที แล้วเว็บจะขึ้น URL ที่:

```
https://YOUR_USERNAME.github.io/genshin-companion/
```

---

## การเพิ่มตัวละครใหม่

เปิดไฟล์ `index.html` หาส่วน `const CHARS = [` แล้วเพิ่มบรรทัดตามรูปแบบนี้:

```javascript
{id:32, name:'ชื่อตัวละคร', el:'Pyro', wpn:'Sword', stars:5, role:'Main DPS', owned:false},
```

- `el` ใส่: `Pyro`, `Hydro`, `Anemo`, `Electro`, `Cryo`, `Geo`, `Dendro`
- `wpn` ใส่: `Sword`, `Polearm`, `Claymore`, `Bow`, `Catalyst`
- `stars` ใส่: `4` หรือ `5`
- `owned` ใส่: `true` (ค่า default) หรือ `false`

## การเพิ่ม Build Guide

หาส่วน `const BUILDS = {` แล้วเพิ่มตามรูปแบบ:

```javascript
'ชื่อตัวละคร': {
  el: 'Pyro',
  role: 'Main DPS',
  artifact: 'ชื่อ Artifact Set (4pc)',
  alt: 'ทางเลือกสำรอง',
  weapons: ['อาวุธที่ 1 (ดีสุด)', 'อาวุธที่ 2', 'อาวุธ F2P'],
  mainStats: ['Sands: HP%', 'Goblet: Pyro DMG%', 'Circlet: Crit Rate/DMG'],
  subStats: ['Crit Rate', 'Crit DMG', 'HP%'],
  talent: 'Skill > Burst > Normal',
  book: 'ชื่อ Talent Book / วันที่ฟาร์ม',
  tip: '🔑 Tips บรรทัดที่ 1\n🔑 Tips บรรทัดที่ 2\n🔑 Tips บรรทัดที่ 3'
},
```

---

## แผนพัฒนาต่อ

ฟีเจอร์ที่เพิ่มได้ในอนาคต:

- [ ] เชื่อมต่อ **Enka.Network API** ดึงข้อมูลจริงจาก UID
- [ ] เพิ่มตัวละครและ Build Guide ให้ครบทุกตัว
- [ ] **Artifact Optimizer** คำนวณ stat ที่ดีที่สุด
- [ ] **Resin Calculator** คำนวณว่าจะฟาร์มเสร็จเมื่อไหร่
- [ ] **Event Calendar** แสดงกิจกรรมที่กำลังจะมาถึง
- [ ] Dark/Light mode toggle
- [ ] PWA (Progressive Web App) ติดตั้งบนมือถือได้

---

## License

MIT — ใช้งาน แก้ไข แจกจ่ายได้อิสระ ไม่มีข้อจำกัด

---

*สร้างโดย Claude | ข้อมูลอัพเดทถึง Version 5.x*
