# Portfolio Camp for TCAS 1 — Website Implementation Plan

**วันที่:** 26 พฤศจิกายน 2569  
**Goal:** ให้เด็กเข้าใจว่าค่ายเหมาะกับตัวเอง ได้อะไร และสมัครได้ทันที  
**Website:** https://pepesx231.github.io/PortfolioCamp/  
**Repository:** https://github.com/PepesX231/PortfolioCamp  
**Base:** `main`, `index.html`, blob `472149f3f4260ae0df87a6738ff2f65de1034a04` (ตรวจ 26 พ.ย.)  
**Architecture:** ปรับ static landing page เดิม ไม่เปลี่ยน framework หรือระบบสมัคร; ใช้ HTML/CSS/Vanilla JS และ assets เดิมเป็นหลัก  
**Execution:** ทำทีละ Task ตามลำดับ ตรวจ acceptance criteria และ commit แยกเมื่อผ่าน ไม่ deploy จนผ่าน launch gate

## 1. Marketing audit

| ผู้ชม | สิ่งที่ต้องการ | ข้อความหลัก | หลักฐาน |
|---|---|---|---|
| มีผลงานแล้ว | ทำพอร์ตและเตรียมสัมภาษณ์ | มีผลงานแล้ว ทำพอร์ตให้พร้อม | ตัวอย่างพอร์ต, สิ่งที่จะเรียน |
| ยังไม่มีผลงาน | เริ่มต้นสร้างงานที่ใช้ต่อยอดพอร์ต | ยังไม่มี มาเริ่มสร้างเกม | เกมจริงของเด็ก HH, Workshop |
| ยังไม่รู้จะเข้าคณะไหน | เห็นเส้นทางมหาวิทยาลัย | คุยกับรุ่นพี่ที่เรียนอยู่จริง | ตารางพบรุ่นพี่ |
| ผู้ปกครอง | รู้ว่าจ่ายเพื่ออะไรและเรียนอย่างไร | 3 วัน ลงมือทำผลงานจริง | ราคา, ตาราง, ผลลัพธ์, ช่องทางติดต่อ |

**Positioning:** Portfolio First → Storytelling Second → Experience Third.

**ข้อแก้ไขจาก source เดิม**

- Hero มีหัวข้อทำพอร์ต แต่มีภาพเกมอย่างเดียว และไม่มีราคา/วันที่/CTA ในเนื้อหาหลัก: เพิ่มข้อมูลและภาพสองเส้นทาง
- Benefits ขึ้นเกมก่อนพอร์ต: สลับลำดับและระบุว่า 2 ผลลัพธ์แรกขึ้นกับ Track
- Track ยังขาดภาพจริง คลิปสัมภาษณ์ และคลิปผลงาน: เติมจากแผนล่าสุด
- Showcase เดิมมีเกมจริง 10 ผลงาน; ตามคำสั่งล่าสุด เปลี่ยนเป็น 7 คลิปจากชีตในแถวเดียว และเพิ่มพอร์ตจริงเมื่อมีสิทธิ์ใช้
- HamsVillage แยก 4 โซนและมี placeholder หลายจุด: ยุบเหลือการ์ดเดียวใน Benefits
- Seniors มี placeholder และตารางเวลาเก่า: ใช้เนื้อหายืนยันแล้ว ไม่สร้างรายชื่อหรือใช้ภาพคนแปลกหน้ามาแทนวิทยากร
- ยังไม่มี Special Guest: เพิ่มพี่ก๊อกและ ARAYA
- ตารางและ FAQ ไม่ตรง deliverables ล่าสุด: แก้ทั้งข้อมูลหลักและ dialog
- ราคาและ CTA อยู่ท้ายหน้า: นำข้อมูลสำคัญขึ้น Hero; ตรวจระบบรับสมัครและ tracking

**Primary CTA:** `สมัครเข้าร่วมกิจกรรม` → https://www.hamsterhub.co/portcamp

**ห้าม:** รับประกันสอบติด, รับประกันพอร์ตผ่านเกณฑ์ทุกคณะ, โฆษณารางวัล/เกียรติบัตรที่ไม่ยืนยัน, อธิบาย Mentor Checkpoint, Quest Gate, Portfolio Pass mechanics, Quick Reaction, Wave, ระดับบูธ, 4 Zones หรือระบบหลังบ้านในหน้าเว็บ

## 2. Global content and launch configuration

| Key | Value | Status |
|---|---|---|
| eventName | Portfolio Camp for TCAS 1 | confirmed |
| organizer | Hamster Hub | confirmed |
| dates | 4–6 ธันวาคม 2569 | confirmed |
| format | ออนไลน์ผ่าน Discord | confirmed |
| price | 190 บาท | มีอยู่ในเว็บเดิม; ยืนยันก่อนเผยแพร่ |
| registrationUrl | https://www.hamsterhub.co/portcamp | มีอยู่ในเว็บเดิม; ทดสอบปลายทาง |
| registrationClose | null | ยังไม่ยืนยัน; ห้ามใช้วันที่สมมุติ |
| contactUrl | https://page.line.me/jkm4247u?openQrModal=true | จากเว็บเดิม; ทดสอบ |
| privacyUrl | null | ขอ URL จริงก่อนเปิดรับข้อมูล |
| guestName | พี่ก๊อก จัตุพร รักไทยเจริญชีพ | ผู้ใช้ระบุ; ตรวจรูปและการสะกดกับวิทยากร |
| guestTopic | From Idea to Production | ใช้ชื่อที่ปรับคำสะกดจาก Form เป็น From |
| guestTime | 5 ธันวาคม 2569 เวลา 15:00 น. | confirmed; ไม่กำหนดเวลาจบเอง |

ใช้ config แหล่งเดียวใน `index.html` เช่น `EVENT` สำหรับราคา ลิงก์และวันปิดรับ; static HTML ต้องตรงกับ config ด้วย (ใช้ build script ขนาดเล็กเฉพาะหากจำเป็น ไม่เพิ่ม framework) ไม่แสดง `null`, `[รอข้อมูล]`, ชื่อไฟล์ หรือข้อความทีมงานบนหน้าเว็บ. ไม่แสดง countdown จนมีวันปิดรับจริง. เวลาใช้ ICT (UTC+7).

## 3. Page architecture / exact copy

ทุกข้อความในส่วนนี้เป็น copy สำหรับแสดงจริง ยกเว้นที่ระบุว่า internal. ใช้ข้อความตามนี้ ไม่เพิ่มคำโฆษณาเอง. ข้อความราคาใช้ได้เมื่อยืนยันแล้ว.

### 01 Navigation + Hero (`#hero`)

Navigation: `Hamster Hub` | `สิ่งที่จะได้รับ` | `เลือก Track` | `ตารางกิจกรรม` | `FAQ` | `สมัคร`

- Eyebrow: `Portfolio Camp for TCAS 1`
- H1 (2 บรรทัด): `มีผลงานแล้ว ทำพอร์ตให้พร้อม` / `ยังไม่มี มาเริ่มสร้างเกม`
- Supporting copy: `3 วัน เตรียมผลงานและพอร์ตสำหรับเข้ามหาวิทยาลัย`
- Event facts: `4–6 ธันวาคม 2569` · `ออนไลน์ผ่าน Discord` · `190 บาท`
- Primary CTA: `สมัครเข้าร่วมกิจกรรม` → registrationUrl
- Secondary link: `เลือก Track ที่เหมาะกับเรา` → `#tracks`
- Visual: แบ่ง 2 ฝั่ง พอร์ตด้านซ้าย เกมด้านขวา; ใช้ `img/t-portfolio.jpg` (กำกับ `ภาพตัวอย่างพอร์ต`) และ `vid/command-select.mp4` + `img/command-select.jpg` (กำกับ `ผลงานจริง: COMMAND SELECT`). มือถือใช้ `vid/command-select-sm.mp4` หรือ poster ตามเงื่อนไข performance. ไม่ทำวิดีโอใหม่
- Design: พื้นดำ ข้อความขาว เน้นสีส้มเดิมเฉพาะคำสำคัญ; ภาพไม่บัง CTA. ยกเลิก `white-space:nowrap` บน H1 มือถือ; ใช้ความสูง auto/min-height แทน fixed 100svh เมื่อข้อมูลล้น
- Acceptance: ที่ viewport 390×844 อ่าน H1, วัน, รูปแบบ, ราคา (เมื่อยืนยัน) และเห็น CTA โดยไม่ต้องเลื่อน; รูปไม่จำเป็นต้องอยู่ทั้งหมดใน first viewport

### 02 Benefits (`#benefits`)

H2: `3 วัน ได้อะไรบ้าง`

Intro: `เลือกทำพอร์ตหรือสร้างเกม แล้วพบรุ่นพี่และโชว์ผลงานไปด้วยกัน`

คง `.gal.store` / `#bstore` / controls เดิม. เรียง 5 การ์ดตามนี้:

| ลำดับ | Label | Heading | Supporting copy | Asset | Action |
|---|---|---|---|---|---|
| 1 | Portfolio Track | ทำพอร์ตให้พร้อม | เขียน SOP จัดรูปเล่ม และเล่าผลงานให้เข้าใจง่าย | `img/t-portfolio.jpg` | `sh-tpf` |
| 2 | Project Track | สร้างเกมชิ้นแรก | เริ่มสร้างผลงานด้วย Unity หรือ Roblox เพื่อต่อยอดทำพอร์ต | `vid/heart.mp4` / `img/heart.jpg` | `sh-tpj` |
| 3 | ทั้งสอง Track | เล่าผลงานให้น่าสนใจ | ฝึกสื่อสารผ่านข้อความ ภาพปก และคลิปนำเสนอ | `img/stock/recording.jpg` หรือ icon กล้อง+ภาพผลงานเดิม | ไม่มี |
| 4 | ทั้งสอง Track | พบรุ่นพี่มหาวิทยาลัย | รู้จักคณะ เปิดพอร์ตจริง และถามข้อสงสัย | `img/dek/dek69-1.jpg`, `dek69-13.jpg`, `dek69-6.jpg` เมื่อยืนยันสิทธิ์ | `sh-uni` |
| 5 | ทั้งสอง Track | สนุกไปกับ HamsVillage | พบเพื่อน ชมผลงาน และเปิดบูธของตัวเอง | `img/hv-2.jpg` | ไม่มี |

การ์ด 1 และ 2 ต้องมี label ชัดเจนว่าคนละ Track. การ์ด 5 คือ HamsVillage ทั้งหมดในหน้า public (ยกเว้นการกล่าวถึงในตาราง/FAQ). ลบปุ่มเปิด `sh-zones`. หากภาพพอร์ตเดิมเป็น mockup ให้แสดง `ภาพตัวอย่าง` ไม่อ้างเป็นพอร์ตสอบติด. หากภาพรุ่นพี่เดิมเป็นโปสเตอร์ย้อนหลัง ให้กำกับ `ภาพกิจกรรมที่ผ่านมา` หลังตรวจความจริง หรือใช้ข้อความแทน

### 03 Choose Your Track (`#tracks`)

H2: `เลือกทางที่ใช่`

Intro: `เลือกตามผลงานที่มี ไม่ใช่ระดับชั้น`

| Field | Portfolio Track | Project Track |
|---|---|---|
| Label | Portfolio Track | Project Track |
| Title | มีผลงานแล้ว | ยังไม่มีผลงาน |
| Subtitle | เอาผลงานที่มี มาเล่าให้เป็น | มาเริ่มสร้างผลงานชิ้นแรก |
| Skill 1 | เขียน SOP | คิดไอเดียเกม |
| Skill 2 | เขียนบรรยายผลงาน | ออกแบบเกม |
| Skill 3 | จัดรูปเล่ม Portfolio | สร้างเกมด้วย Unity หรือ Roblox |
| Skill 4 | ซ้อมสัมภาษณ์และแนะนำตัว | ฝึกนำเสนอเกม |
| Output headline | พอร์ต 1 เล่ม | เกม 1 เกม |
| Output sub | คลิปซ้อมสัมภาษณ์และคลิปนำเสนอผลงาน | คลิปนำเสนอสำหรับต่อยอดทำพอร์ต |
| CTA | เลือก Portfolio Track | เลือก Project Track |
| Detail button | รายละเอียด | รายละเอียด |
| Asset | `img/t-portfolio.jpg` | `img/heart.jpg` |

คง Comparison สองคอลัมน์บน desktop. มือถือ <=480px ให้ทดสอบ stacked cards เป็นค่าเริ่มต้นเพื่ออ่านง่าย; ไม่บังคับสองคอลัมน์ถ้าข้อความอ่านยาก. ทั้งสอง CTA ไป `#registration` และคง `data-track` ค่า `portfolio` / `project`.

#### Dialog `sh-tpf` — exact copy

Title: `Portfolio Track`

Intro: `นำผลงานที่มีมาเขียนพอร์ต ฝึกเล่าเรื่อง และเตรียมตัวสำหรับการสัมภาษณ์`

- `เขียน SOP` — `เล่าเหตุผลที่อยากเข้าคณะและเป้าหมายของตัวเอง`
- `เขียนบรรยายผลงาน` — `อธิบายไอเดีย วิธีทำ และสิ่งที่ได้เรียนรู้`
- `จัดรูปเล่ม` — `เลือกผลงานและจัดหน้าให้อ่านง่าย`
- `ซ้อมสัมภาษณ์` — `อัดคลิปแนะนำตัวและฝึกตอบคำถาม`
- `โชว์ผลงาน` — `เลือกผลงานเด่นที่สุด 1 ชิ้น พร้อมภาพปกและคลิปนำเสนอ 2 นาที`

Output: `รูปเล่ม Portfolio คลิปซ้อมสัมภาษณ์ และคลิปนำเสนอผลงาน`

#### Dialog `sh-tpj` — exact copy

Title: `Project Track`

Intro: `เริ่มจากพื้นฐาน แล้วสร้างเกมของตัวเองเพื่อใช้ต่อยอดทำพอร์ต`

- `Game Design` — `คิดไอเดียและออกแบบวิธีเล่น`
- `Game Development` — `ลงมือสร้างเกมด้วย Unity หรือ Roblox`
- `Storytelling` — `เล่าให้คนเข้าใจและเห็นจุดเด่นของเกม`
- `โชว์ผลงาน` — `ทำภาพปกและคลิปนำเสนอเกม 2 นาที`

Output: `เกม 1 เกม พร้อมคลิปนำเสนอผลงาน`

### 04 Real Student Works (`#showcase`)

H2: `ผลงานจริง จากเด็ก Hamster Hub`

Supporting: `จากไอเดียของนักเรียน สู่ผลงานที่เล่นได้จริง`

ตามคำสั่งล่าสุด แสดงคลิปจากชีตผลงานที่ผู้ใช้ให้มาแบบคละกันใน **แถวเลื่อนซ้ายขวาแถวเดียว** ทุกการ์ดขนาดเท่ากัน ไม่มีชิ้นเด่น ไม่แสดงเกรด คะแนน คำวิจารณ์ หรือเครดิตที่ไม่ได้ขอ. ทุกคลิปดาวน์โหลดจากลิงก์ในชีตและเข้ารหัสใหม่โดยคงความยาวเต็ม; poster มาจากเฟรมของคลิปเดียวกัน. เล่นอัตโนมัติแบบปิดเสียงและวนลูปเมื่อคลิปอยู่ในจอ (`preload="none"`), หยุดเมื่อเลื่อนพ้นจอหรือซ่อนแท็บ, เคารพ reduced motion และการกดหยุดของผู้ชม. ไม่ใช้ RE//SLASH ตามคำสั่งผู้ใช้. ยังไม่อ้างว่าคลิปเหล่านี้สร้างในค่ายสามวันนี้.

| ชื่อที่แสดง | แหล่งในชีต | ไฟล์ในเว็บ |
|---|---|---|
| Hydrosaur | โฟลเดอร์ Drive แถวแรก; ชื่อจากไฟล์ Hydrosaur.mp4 | `vid/showcase/hydrosaur.mp4` |
| Noas | Facebook | `vid/showcase/noas.mp4` |
| PITCH | Facebook | `vid/showcase/pitch.mp4` |
| Apocalypse Building | Instagram | `vid/showcase/apocalypse-building.mp4` |
| Heart of Remember | Instagram | `vid/showcase/heart-of-remember.mp4` |
| 5 Min till we drown | Drive | `vid/showcase/5-mins-till-we-drown.mp4` |
| TLAMAN | Instagram | `vid/showcase/tlaman.mp4` |

แหล่งไฟล์ตรงของทุกคลิปและภาพ poster อยู่ใน `assets-sources.md`. คลิปเก่าและภาพ `img/hof/` ยังเก็บไว้ในรีโป แต่ไม่แสดงใน Showcase รอบนี้.

เพิ่มกลุ่มพอร์ตจริงเมื่อได้รับไฟล์และสิทธิ์ใช้เท่านั้น:
- Heading: `ตัวอย่างพอร์ตของรุ่นพี่`
- Caption: ชื่อคณะและมหาวิทยาลัยที่ยืนยันจริง
- Asset: `img/portfolio-examples/` (ชื่อใหม่ที่เสนอ; ไม่ใช่ไฟล์ที่มีแล้ว)
- ปกปิดชื่อเต็ม เลขประจำตัว ที่อยู่ เบอร์โทร QR ที่เผยข้อมูลส่วนตัว ฯลฯ
- ถ้ายังไม่มี ให้ซ่อนกลุ่มพอร์ตจริงทั้งหมด ไม่สร้าง social proof เทียม. ใช้ `img/t-portfolio.jpg` เป็นภาพตัวอย่างเฉพาะ Hero/Track/Benefits

### 05 Special Guest (การ์ดในตารางวันที่ 5 ธ.ค.)

Eyebrow: `SPECIAL GUEST`

หัวข้อในการ์ด: `From Idea to Production`

Topic: `From Idea to Production`

Speaker: `พี่ก๊อก จัตุพร รักไทยเจริญชีพ`

Role: `หนึ่งในผู้พัฒนาเกม ARAYA`

Copy: `จากโปรเจกต์ธีสิสสู่เกมสยองขวัญสัญชาติไทยบน Steam เรียนรู้วิธีพัฒนาไอเดียและสื่อสารผลงานให้คนสนใจ`

Time: `5 ธันวาคม 2569 · 15:00 น.`

Layout: ตามคำสั่งล่าสุด ย้ายจาก standalone section ไปเป็นการ์ดเด่นที่กดขยายรายละเอียดได้ในตารางวันที่ 5 ธ.ค. 15:00 น. ใช้รูปพี่ก๊อกที่ผู้ใช้ส่งมาในแชต 27 พ.ย. 2569 (`img/guest/jatuporn.webp`) ในแถวตาราง; ภาพเกม ARAYA ยังไม่ใส่จนได้รับสิทธิ์ใช้. ใช้ชื่อ หัวข้อ และลิงก์ `รู้จักเกม ARAYA` → https://store.steampowered.com/app/466740/ARAYA/ . ไม่ใช้ stock portrait แทนบุคคลจริงหรือฉากรุนแรงสำหรับสื่อเด็ก

Source: Steam ยืนยันเกมและผู้พัฒนา MAD Virtual Reality Studio; บทสัมภาษณ์ Mango Zero ปี 2559 ยืนยันชื่อและที่มาจากธีสิส; SSRU ยืนยันเป็นวิทยากรจากทีม ARAYA. ไม่อ้างตำแหน่งงานปัจจุบัน รางวัล หรือยอดขายโดยไม่มีหลักฐาน

### 06 Meet the Seniors (`#seniors`)

H2: `อยากเข้ามหาวิทยาลัยไหน มาคุยกับรุ่นพี่ที่เรียนอยู่จริง`

จัด 3 การ์ด ไม่ต้องใช้ภาพบุคคลที่ไม่ใช่ผู้เข้าร่วมจริง:

| Date | Title | Copy | Time |
|---|---|---|---|
| 4 ธ.ค. | รู้จักคณะและมหาวิทยาลัย | แต่ละคณะเรียนอะไร และควรเตรียมตัวอย่างไร | 20:00–21:00 |
| 5 ธ.ค. | เปิดพอร์ตจริงของรุ่นพี่ | ดูตัวอย่างการเลือกผลงานและการเล่าเรื่องในพอร์ต | 19:00–20:00 |
| 6 ธ.ค. | ถามตอบเรื่องมหาวิทยาลัย | ถามข้อสงสัยและวางแผนเส้นทางของตัวเอง | 19:00–20:00 |

เมื่อมีรายชื่อยืนยัน เพิ่มชื่อเล่น ชื่อ คณะ สาขา มหาวิทยาลัย รูป และหัวข้อคนละหนึ่งบรรทัด; ไม่เพิ่มโลโก้มหาวิทยาลัยเพื่อสื่อว่าเป็น partner หากไม่ได้อนุญาต. วาง section นี้ก่อน Student Works ตามคำสั่งล่าสุด. ใช้ภาพห้องเรียนมหาวิทยาลัยจาก Unsplash พร้อมป้าย `ภาพประกอบบรรยากาศมหาวิทยาลัย`; ไม่อ้างว่าเป็นมหาวิทยาลัยที่ร่วมงาน. หากไม่มีรูปผู้เข้าร่วมจริง ใช้การ์ดตัวอักษรแบบกระชับบนมือถือ; แสดง `รายชื่อรุ่นพี่จะประกาศเพิ่มเติม` ได้เฉพาะเมื่อทีมมีแผนประกาศจริง

อัปเดต `sh-uni` ให้ใช้ข้อความและเวลาตารางนี้; ตัดรายละเอียดที่ซ้ำโดยไม่จำเป็น. ไม่อธิบายระบบปลดล็อก แต่ถ้ายังมีเงื่อนไขเข้าชมจริงให้แจ้งสั้น ๆ ว่า `กิจกรรมเปิดพอร์ตสำหรับผู้ผ่านภารกิจในค่าย` หลังทีมยืนยันเงื่อนไข เพื่อไม่ทำให้ผู้สมัครเข้าใจผิด

### 07 Activity Schedule (`#schedule`)

H2: `ตารางกิจกรรม`

Tabs: `4 ธ.ค.` | `5 ธ.ค.` | `6 ธ.ค.`. คง keyboard arrow navigation และ selected tab เดิม. ระบุหัวข้อของวันเหนือรายการ (source เดิมมี DAYS.title แต่ไม่ได้ render)

| วัน | เวลา | ข้อความที่แสดง |
|---|---|---|
| 4 ธ.ค. | 19:00–20:00 | เปิดค่ายและแนะนำกิจกรรม |
| 4 ธ.ค. | 20:00–21:00 | รุ่นพี่แนะนำคณะและมหาวิทยาลัย |
| 5 ธ.ค. | 13:00–15:00 | Workshop ตาม Track |
| 5 ธ.ค. | 15:00 | From Idea to Production กับพี่ก๊อก |
| 5 ธ.ค. | ช่วงบ่าย | ลงมือทำผลงาน |
| 5 ธ.ค. | 19:00–20:00 | เปิดพอร์ตจริงของรุ่นพี่ |
| 5 ธ.ค. | 20:00–21:00 | ลงมือทำผลงาน |
| 6 ธ.ค. | 13:00–15:00 | ทำผลงานให้เสร็จ |
| 6 ธ.ค. | 15:00 | ส่งผลงาน |
| 6 ธ.ค. | 16:00–18:00 | HamsVillage Showcase |
| 6 ธ.ค. | 19:00–20:00 | University Q&A |
| 6 ธ.ค. | 20:00–21:00 | ปิดกิจกรรม |

Day titles: `ค้นหาเส้นทาง` / `ลงมือสร้าง` / `โชว์ผลงาน`. เหนือรายการแต่ละวันแสดงเวลารวม `19:00–21:00` / `13:00–21:00` / `13:00–21:00`. รายการพี่ก๊อก 15:00 กดขยายเพื่ออ่านรายละเอียดและลิงก์เกมได้; ยังไม่ระบุเวลาจบที่ไม่ยืนยัน.

Workshop sublabels: `Portfolio Track: เขียนพอร์ตและ SOP` / `Project Track: ออกแบบและสร้างเกม`.

หมายเหตุภายใน: 19:00 วันแรก, 13:00 วัน 2–3, 15:00 ส่งงาน อิงแผนเดิมและต้องยืนยัน; เวลาบรรยายจบของพี่ก๊อกยังไม่ทราบ. ไม่แสดงเวลาซ้ำซ้อนหรือกิจกรรมภายใน. ไม่เพิ่ม Mentor Checkpoints หรือเวลาเตรียมบูธ. หากมีช่วงพักที่เด็กจำเป็นต้องรู้ ให้แจ้งใน participant guide หลังสมัคร

### 08 Registration (`#registration`)

H2: `เริ่มต้นเส้นทางของตัวเอง`

Subtitle: `Portfolio Camp for TCAS 1`

Price: `190 บาท` (ยืนยันก่อนเผยแพร่)

Facts: `4–6 ธันวาคม 2569` / `ออนไลน์ผ่าน Discord`

Deadline (แสดงเฉพาะเมื่อยืนยัน): `ปิดรับสมัคร {วัน เดือน} เวลา {HH:mm} น.`

Primary CTA: `สมัครเข้าร่วมกิจกรรม`

Secondary: `สมัครอย่างไร`

Selected Track: `Track ที่เลือก: Portfolio Track` หรือ `Track ที่เลือก: Project Track`. ถ้ายังไม่เลือก ซ่อนบรรทัดนี้. ไม่บังคับเลือกก่อนเปิดหน้าสมัคร

Dialog `sh-how`:
1. `กดสมัครเข้าร่วมกิจกรรม`
2. `กรอกข้อมูลและเลือก Track`
3. `ยืนยันการสมัครตามขั้นตอนบนเว็บไซต์`
4. `ติดตามข้อมูลเข้าค่ายจากทีมงาน`

สิ่งที่ต้องเตรียม: `คอมพิวเตอร์หรือโน้ตบุ๊ก อินเทอร์เน็ต และบัญชี Discord` / `Portfolio Track: ไฟล์ผลงานที่มี` / `Project Track: ติดตั้งโปรแกรมตามที่ทีมแจ้ง`.

ยืนยันกระบวนการสมัครจริงกับทีม; ไม่เพิ่มขั้นตอนจ่ายเงินที่ยังไม่ได้ตรวจ. คง query `?track=portfolio` และ `?track=project` เฉพาะถ้าหน้าปลายทางรองรับ; หากไม่รองรับ ให้ใช้ URL ปกติและให้ผู้สมัครเลือกในฟอร์ม

### 09 FAQ (`#faq`)

H2: `คำถามที่พบบ่อย`

| Question | Answer |
|---|---|
| ไม่มีพื้นฐาน สมัครได้ไหม? | ได้ เลือก Project Track แล้วเริ่มสร้างเกมจากพื้นฐาน |
| อยู่ ม.4 หรือ ม.5 สมัครได้ไหม? | หากอยู่ในกลุ่มผู้สมัครที่กิจกรรมเปิดรับ สามารถเลือก Track ตามความพร้อมของผลงานได้ | 
| มีผลงานที่ไม่ใช่เกม สมัครได้ไหม? | ได้ หากมีผลงานที่ต้องการนำไปทำพอร์ต สามารถเลือก Portfolio Track |
| ยังไม่รู้ว่าจะเข้าคณะไหน สมัครได้ไหม? | ได้ มาค้นหาเส้นทางและถามข้อสงสัยกับรุ่นพี่มหาวิทยาลัย |
| ต้องเตรียมอะไรบ้าง? | คอมพิวเตอร์หรือโน้ตบุ๊ก อินเทอร์เน็ต และบัญชี Discord หากเลือก Portfolio Track ให้เตรียมไฟล์ผลงานที่มี |
| ต้องเดินทางไหม? | ไม่ต้อง กิจกรรมจัดออนไลน์ผ่าน Discord และ HamsVillage |
| จบค่ายแล้วได้อะไร? | Portfolio Track ได้ทำรูปเล่มพอร์ตและคลิปซ้อมสัมภาษณ์ ส่วน Project Track ได้สร้างเกม ทั้งสอง Track มีคลิปนำเสนอผลงาน 2 นาที |
| เข้าค่ายแล้วสอบติดแน่นอนไหม? | ค่ายช่วยเตรียมผลงานและพอร์ต การรับเข้าศึกษาขึ้นอยู่กับเกณฑ์ของแต่ละมหาวิทยาลัย |

ก่อน launch ยืนยันช่วงชั้นที่เปิดรับ; หากยืนยันว่า ม.4 และ ม.5 สมัครได้ ให้แทนคำตอบข้อ 2 ด้วย `ได้ เลือก Track ตามความพร้อมของผลงาน ไม่ใช่ระดับชั้น`. หากยังไม่ยืนยัน ให้ซ่อนข้อ 2 และตอบผ่านทีมงานแทน. ไม่ใส่ข้อมูลเกียรติบัตรที่ไม่ยืนยัน

### Footer

- `จัดโดย Hamster Hub`
- `ภาพผลงานจริงและภาพตัวอย่างมีป้ายกำกับตามประเภท`
- `การรับเข้าศึกษาขึ้นอยู่กับเกณฑ์ของแต่ละมหาวิทยาลัย`
- `เว็บไซต์ Hamster Hub` → https://www.hamsterhub.co/
- `ติดต่อทีมงาน` → contactUrl
- `นโยบายความเป็นส่วนตัว` → privacyUrl ที่ตรวจสอบแล้ว (ห้ามใช้ข้อความ `[รอลิงก์จากทีม]`)

## 4. Visual system

- คง Noto Sans Thai และสไตล์ Apple เดิม: typography ใหญ่ ภาพเด่น พื้นขาว/ดำ/เทาอ่อน
- Tokens เดิม `--bg:#fff`, `--alt:#f5f5f7`, `--ink:#1d1d1f`, `--mute:#515154`, `--blue:#0071e3`; track portfolio `#0057b8`, project `#b25000`
- H1 desktop 56–72px; mobile 30–40px ตามความกว้าง; H2 desktop 44–52px, mobile 28–32px; body 16–19px; ข้อความรองไม่ต่ำกว่า 14px
- Section padding desktop 80–120px; mobile 48–72px. Container max 1200px; mobile gutter 16px
- Primary button สูงอย่างน้อย 48px. Navigation mobile ต้องเห็นปุ่มสมัครตลอดโดยไม่ต้องเลื่อนแนวนอน; ซ่อนลิงก์รองเมื่อจำเป็น
- ใช้ภาพจริงก่อน ไม่ใช้ animation เพื่อซ่อนเนื้อหา; hero video muted + playsinline, poster fallback, pause control, respect reduced motion
- ไม่สร้าง section HamsVillage, Storytelling หรือ Booth แยก; ไม่เพิ่มกราฟิกตกแต่งที่ไม่ช่วยสื่อสาร

## 5. Asset manifest

ชื่อไฟล์ในคอลัมน์ Existing ตรวจจาก source เดิมแล้วว่าอ้างถึง แต่ยังไม่ได้ตรวจ bytes/HTTP status ทุกไฟล์. ทดสอบก่อนใช้. External sources เป็นหน้าต้นทางที่ค้นพบจริง; ไม่ใช่ไฟล์ที่ดาวน์โหลดเข้า repository แล้ว

| Slot | Existing / proposed path | Source / action | Usage rules |
|---|---|---|---|
| Hero portfolio / Portfolio card | `img/t-portfolio.jpg` | เดิม | ป้ายภาพตัวอย่าง |
| Hero game | `vid/command-select.mp4`, `vid/command-select-sm.mp4`, `img/command-select.jpg` | เดิม | ผลงานจริง: COMMAND SELECT |
| Project card | `vid/heart.mp4`, `img/heart.jpg` | เดิม | ใช้ poster เมื่อ offscreen |
| HamsVillage | `img/hv-2.jpg` | เดิม | ภาพระบบจริงหากทีมยืนยัน |
| Seniors past assets | `img/dek/dek69-1.jpg`, `dek69-13.jpg`, `dek69-6.jpg` | เดิม | ตรวจว่าเป็นอะไร; ไม่อ้างเป็นผู้มาร่วมรอบนี้ |
| Showcase clips | `vid/showcase/*.mp4`, `img/showcase/*.webp` | ลิงก์ในชีตผู้ใช้; รายการตรงใน §3.04 และ `assets-sources.md` | 7 คลิปแถวเดียว, poster จากวิดีโอ, autoplay muted loop เฉพาะที่มองเห็น, ไม่ preload, ไม่แสดงเกรด |
| University atmosphere | `img/stock/university-lecture-hall.webp` | https://unsplash.com/photos/empty-university-lecture-hall-desks-F8t2VGnI47I | ภาพประกอบ ไม่ใช่ partner หรือผู้เข้าร่วม |
| Storytelling card | `img/stock/recording.webp` | https://unsplash.com/photos/camera-microphone-and-laptop-set-up-for-recording-jC2BNWcwFTA | ภาพตัวอย่างการอัดคลิป ไม่ใช่ผู้เรียนจริง; ดาวน์โหลดจากหน้าภาพ |
| Recording backup | `img/stock/recording-alt.jpg` | https://unsplash.com/photos/man-filming-with-professional-camera-setup-sPeIJ0ebl8c | ใช้เฉพาะถ้าภาพแรกไม่เหมาะ; ไม่อ้างบุคคลเป็นผู้ร่วมค่าย |
| Generic learning backup | `img/stock/student-work.jpg` | https://unsplash.com/photos/a-student-smiles-while-working-on-his-laptop-VBIMtDdjuWc | ทางเลือกสำหรับภาพเรียนออนไลน์ ไม่ใช่ testimonial; ตรวจ model rights |
| ARAYA artwork | `img/guest/araya.jpg` | https://store.steampowered.com/app/466740/ARAYA/ | ขออนุญาตใช้ภาพจากเจ้าของสิทธิ์; ไม่ใช้ภาพสยองรุนแรง; ใช้ลิงก์เกมแทนได้ |
| Guest portrait | `img/guest/jatuporn.webp` | ผู้ใช้ส่งภาพในแชต 27 พ.ย. 2569 | แสดงในการ์ดตารางวันที่ 5; ไม่ใช้ภาพจากบทสัมภาษณ์ |
| Actual seniors | `img/seniors/` | ทีมกิจกรรม | รูปจริง + อนุญาตเผยแพร่ |
| Actual portfolio | `img/portfolio-examples/` | ทีมกิจกรรม | ปกปิดข้อมูลส่วนบุคคล |
| Social share | `img/og.jpg` (อ้างใน metadata เดิม) | ตรวจว่าไฟล์มีจริง; ถ้าต้องสร้างใหม่ ให้รวมภาพพอร์ตและเกมเดิม + ชื่อ/วันที่ | 1200×630 |

### External asset procedure

- [x] เปิดหน้าต้นทางและตรวจใบอนุญาต/ความเหมาะสมของภาพจริง — เพิ่มภาพประกอบ Unsplash 2 ภาพ; ฟอนต์ใช้ OFL
- [x] ดาวน์โหลดภาพที่อนุญาตลง `img/stock/` เป็น WebP; ไม่ hotlink ภาพภายนอกและไม่ใช้ภาพ Google แบบไร้ต้นทาง
- [x] บันทึก `assets-sources.md`: path, source URL, author, license/permission, วันที่ดาวน์โหลด
- [x] Resize ภาพที่ใช้จริงเป็น WebP/JPEG ตามความเหมาะสม, width 800–1600px, ตั้ง width/height/aspect-ratio กัน layout shift
- [x] กำหนด alt ที่อธิบายภาพ; decorative image ใช้ alt=""; lazy-load ภาพใต้ fold
- [x] ถ้าไม่มีภาพที่ใช้ได้ ใช้ typography/icon/ภาพเดิมที่ตรงประเด็น ไม่แสดงช่องสีเทา `รอภาพจริง`

Unsplash License: https://unsplash.com/license (อนุญาตใช้ภาพทั่วไปเชิงพาณิชย์ แต่ไม่ใช่การอนุญาตอัตโนมัติสำหรับทุกสิทธิ์บุคคล/เครื่องหมายการค้า). ภาพ ARAYA และรูปวิทยากรยังไม่มีหลักฐานอนุญาตนำมาใช้ในโฆษณาค่าย

## 6. Implementation checklist

### Task 1 — ตรวจ baseline และล็อกข้อมูล (P0, Marketing + Dev)

Files: `index.html`, `planning.md`, create `assets-sources.md`.

- [x] อ่าน `index.html` ทั้ง HTML/CSS/JS; สำรองผ่าน branch ใหม่ ไม่แก้ `main` โดยตรง
- [ ] ตรวจ config §2 กับทีม, ยืนยันราคา ช่วงชั้น ลิงก์ วันปิดรับ เงื่อนไข Portfolio Reveal และตาราง — ยังรอราคา ช่วงชั้น privacy เงื่อนไขพอร์ต ตาราง และสิทธิ์ภาพจากทีม
- [ ] เปิดเว็บเดิมและทดสอบสมัครโดยไม่ส่งข้อมูลจริง; ตรวจ URL/redirect/query — ทดสอบปลายทางแล้วตอบ HTTP 404; ไม่แก้หน้าสมัครตามคำสั่งผู้ใช้
- [x] บันทึกภาพหน้าจอ desktop/mobile เป็น baseline และรายการ asset ที่เปิดไม่ได้
- [x] Check: ข้อมูลที่ไม่ยืนยันถูกแยกจากข้อมูล public, ไม่มีการสร้างข้อเท็จจริงเอง

### Task 2 — Hero + navigation (P0, Dev)

Files: `index.html` (`.hero`, `#heroVid`, `.hero-media`, `.tabbar`, media queries).

- [ ] แทน copy ทั้งหมดตาม §3.01; เพิ่ม CTA/secondary link/date/format/price — ทำครบยกเว้นราคา ซึ่งซ่อนไว้จนยืนยัน
- [x] ทำ 2-panel visual จาก assets เดิม; ปรับ mobile stacking หรือ crop ตามความเหมาะสม
- [x] แก้ CSS ที่ซ้ำเกี่ยวกับ hero height, nowrap, mask และ margin; ตรวจ video JS ไม่ throw เมื่อ asset ไม่พร้อม
- [x] เพิ่ม pause/play button ที่มี accessible name และหยุด autoplay เมื่อ reduced motion/offscreen; ใช้ poster fallback
- [x] Check: 390×844, 768×1024, 1440×900 อ่านข้อมูลหลักและกด CTA ได้; ไม่มี horizontal overflow

### Task 3 — Benefits + Tracks (P0, Dev + Graphic)

Files: `index.html` (`#benefits`, `#bstore`, `.cmp2`, `#tracks`, `#sh-tpf`, `#sh-tpj`, `#sh-zones`).

- [x] เรียง 5 cards และ copy ตาม §3.02
- [x] ใส่ภาพจริงเดิมแทน placeholder ใน Tracks; เพิ่มผลลัพธ์คลิปและรายละเอียด dialog
- [x] ลบ standalone `#village`, `sh-zones`, `data-sheet="sh-zones"` และ JS/CSS ที่ใช้งานเฉพาะ section นี้ หลังตรวจ dependency
- [x] คง `#bstore`, `.sarrows`, `.ar` และ track selection handlers; ถ้าลบ element ให้ guard JS ทุกจุดที่ query element นั้น
- [x] Check: ไม่เหลือคำว่า `รอภาพ` หรือข้อความ 4 Zones; เปิด/ปิด dialog และคืน focus ได้; CTA แต่ละ Track เลือกถูกต้อง

### Task 4 — Proof + Guest + Seniors (P0, Marketing + Dev)

Files: `index.html`, `vid/showcase/`, `img/showcase/`, `img/guest/`, `img/portfolio-examples/`, `assets-sources.md`.

- [x] เปลี่ยน Showcase เป็นคลิป 7 ผลงานจากชีตผู้ใช้ในแถวเดียว การ์ดเท่ากัน และตัด RE//SLASH; ไม่แสดงเกรด/คะแนน/คำวิจารณ์. สิทธิ์เผยแพร่ผลงานนักเรียนก่อนเปิดเว็บจริงยังต้องยืนยันกับทีม
- [x] ย้ายพี่ก๊อกและ ARAYA เป็นการ์ดขยายได้ในตารางวันที่ 5 ธ.ค.; เพิ่มรูปพี่ก๊อกจากไฟล์ที่ผู้ใช้ส่งมา. ภาพเกม ARAYA ยังไม่ใส่
- [x] ย้าย `#seniors` ก่อน `#showcase`, เพิ่มภาพมหาวิทยาลัยที่ติดป้ายภาพประกอบ, ทำการ์ดมือถือให้กระชับ และคง `sh-uni`; ซ่อน profile ที่ไม่ยืนยัน
- [ ] เพิ่ม portfolio proof เมื่อได้รับไฟล์จริงที่ปกปิดข้อมูล — ผู้ใช้ให้รอปกพอร์ตไว้ก่อน; ไม่แสดง placeholder
- [x] Check: ผู้ชมไม่เข้าใจผิดว่า stock photo คือผู้เข้าร่วมจริง หรือเกมเก่าคือผลงานที่สร้างในค่ายนี้

### Task 5 — Schedule + Registration + FAQ (P0, Dev)

Files: `index.html` (`DAYS`, `FAQ`, `REG`, `#registration`, `#sh-how`, `#sh-uni`, footer).

- [x] แทน DAYS และ FAQ ตาม §3; render day title; รองรับ row เวลาแบบจุดเวลาและช่วงเวลา; workshop split แสดงถูกต้อง
- [ ] ปรับ dialog สมัครและรายละเอียดสิ่งที่ต้องเตรียม; ยืนยัน track query support — ปรับข้อความแล้ว; ไม่ส่ง `?track=` เพราะปลายทาง 404 และยังยืนยันการรองรับไม่ได้
- [x] ใช้ registration config เดียวกันทุก CTA; deadline conditional; แก้ `dataLayer` event ให้จำแนก `hero`, `nav`, `registration` ชัดเจน
- [ ] ใส่ privacy link ที่ได้รับการยืนยัน; ลบข้อความรอข้อมูล — ยังไม่มี URL ที่ยืนยัน; ซ่อนลิงก์แทนข้อความรอ
- [x] Check: เวลารวม 4 ธ.ค. 19–21, 5–6 ธ.ค. 13–21; 5 ธ.ค. 15:00, 19–20, 20–21 และ 6 ธ.ค. 16–18, 19–20, 20–21 ตรงกันทุกส่วน; ไม่สร้างเวลาจบพี่ก๊อก

### Task 6 — SEO, accessibility, performance (P1, Dev)

Files: `index.html`, `img/og.jpg`, `assets-sources.md`.

Exact metadata:
- Title: `Portfolio Camp for TCAS 1 | ทำพอร์ตและสร้างเกมใน 3 วัน | Hamster Hub`
- Description: `มีผลงานแล้ว ทำพอร์ตให้พร้อม ยังไม่มี มาเริ่มสร้างเกม พบรุ่นพี่มหาวิทยาลัยและผู้พัฒนา ARAYA วันที่ 4–6 ธันวาคม 2569 ออนไลน์ผ่าน Discord`
- OG title: `Portfolio Camp for TCAS 1`
- OG description: `มีผลงานแล้ว ทำพอร์ตให้พร้อม ยังไม่มี มาเริ่มสร้างเกม | 4–6 ธันวาคม 2569`
- Canonical: `https://pepesx231.github.io/PortfolioCamp/` (หากเปลี่ยนโดเมนจริงให้แก้ทุก metadata)

- [x] ตรวจ favicon, OG image URL, language `th`, heading hierarchy (H1 เดียว)
- [x] ตรวจ keyboard navigation, focus, dialog close (Esc), FAQ accordion, tab aria states
- [x] ใช้ touch targets ≥44px; ทดสอบ contrast ของข้อความเทาและปุ่มบนพื้นดำ
- [x] ลดโหลดวิดีโอที่ไม่เห็น; poster mobile; lazy images; หลีกเลี่ยง layout shift; ตรวจ GSAP fallback หากไม่โหลด
- [x] รวม CSS override ที่ซ้ำเฉพาะส่วนแก้ ไม่ rewrite CSS ทั้งไฟล์โดยไม่มีเหตุผล — ยุบ CSS เดิมที่ซ้ำและมี component เก่าในงานปรับโครงหน้า; `index.html` ลดจาก 93.9 KB เหลือประมาณ 44 KB
- [x] ตรวจ JS ไม่มี error เมื่อย้าย/ลบ section; script ไม่พึ่ง DOM ที่ถูกลบ
- [x] Check: Lighthouse mobile เป้าหมาย Performance ≥85, Accessibility ≥95 (เป้าทดสอบ ไม่ใช่ผลวัด); LCP ≤2.5s, CLS ≤0.1 บน field data เมื่อมีข้อมูล

### Task 7 — QA + launch gate (P0, Owner + Dev)

- [ ] ทดสอบ Chrome, Safari; มือถือ 360, 390, 430px; tablet 768px; desktop 1440px — Chromium ครบทุกขนาดและ Playwright WebKit ที่ 390/1440px ผ่าน; Safari app เปิดไม่ได้เพราะ Mac ล็อก
- [ ] ทดสอบจริง Hero CTA, nav CTA, ทั้งสอง Track CTA, FAQ, modal, carousel touch/keyboard — ปุ่มและ tracking ทำงานในเครื่อง; ปลายทางสมัครยัง 404
- [x] ทดสอบโหลดแบบเครือข่ายช้า; ปิด animation และปิด JavaScript ตรวจข้อมูลสำคัญยังอ่านได้ (เพิ่ม static fallback ให้ schedule/FAQ ที่สร้างด้วย JS ตามจำเป็น)
- [ ] ตรวจ broken images/links, console errors, ราคา วันจัด วันปิดรับ ตำแหน่งวิทยากรและสิทธิ์ภาพ — ภาพและ internal links ผ่าน; ลิงก์สมัคร 404 และสิทธิ์ภาพ/ข้อมูลยังรอทีม
- [ ] ให้เด็กที่มีผลงานและไม่มีผลงานอย่างละ 1–2 คน ทดลองดู Hero 5 วินาทีแล้วถามว่า `กิจกรรมนี้คืออะไร / เหมาะกับใคร / ต้องกดอะไร` โดยไม่บอกคำตอบ — ยังไม่ได้ทดสอบกับนักเรียนจริง
- [ ] ให้ทีมตรวจข้อมูลสำคัญและ privacy link ก่อน deploy — ยังไม่ได้รับการยืนยันจากทีม
- [ ] Commit และ deploy เมื่อ P0 ผ่าน; เปิด URL จริงบน GitHub Pages ตรวจซ้ำหลัง deploy — ยังไม่ deploy หรือ push ตามคำสั่งผู้ใช้; ปลายทางสมัครยัง 404

## 7. Measurement

คง `select_track`, `register_click`, `line_click` ที่เว็บเดิม push เข้า `dataLayer`; ตรวจว่ามี analytics consumer จริง ไม่ถือว่า push แล้วเท่ากับวัดผลได้

| Metric | Definition |
|---|---|
| Registration CTR | unique sessions ที่กดสมัคร / landing sessions |
| Track preference | unique sessions ที่เลือกแต่ละ Track / sessions ที่เลือก Track |
| Registration conversion | ผู้สมัครสำเร็จ / landing sessions ในช่วงเดียวกัน (เชื่อมข้อมูลระบบรับสมัครอย่างเหมาะสม) |
| Hero clarity | จำนวนผู้ทดสอบที่เข้าใจเป้าหมายและเลือกเส้นทางถูก / ผู้ทดสอบทั้งหมด |

ไม่ตั้ง KPI ตัวเลขโดยไม่มี baseline. หากวัด completion ไม่ได้ ให้รายงาน CTR แยก ห้ามตีความเป็นยอดสมัคร

## 8. Decisions, dependencies and scope

**ต้องยืนยัน:** ราคา 190 บาท, วันและเวลาปิดรับสมัคร, ชั้นเรียนที่สมัครได้, ลิงก์ privacy, กระบวนการสมัครจริง, เงื่อนไขเข้าชมพอร์ตรุ่นพี่, เวลาช่วง Workshop/ส่งงาน, รูปและสิทธิ์วิทยากร/รุ่นพี่/ผลงานนักเรียน. ผู้ใช้ระบุเวลาพี่ก๊อกเริ่ม 15:00 แต่ไม่ได้ระบุเวลาจบ

**ตัดสินใจตามคำสั่งล่าสุด:** Hero เน้นสอง Track และพอร์ตขึ้นก่อน, Seniors อยู่ก่อน Student Works, Guest อยู่ในตารางวันที่ 5 ธ.ค., ยุบ HamsVillage เป็น Benefits, ใช้ fallback ตัวอักษรแทนภาพที่ไม่อนุญาต. ปกพอร์ตจริงรอรอบถัดไป. เป็นการจัดหน้า ไม่ใช่ผลทดสอบผู้ใช้

**Out of scope:** แก้ระบบ HamsVillage, Quick Reaction, Booth Waves, จัดระดับบูธ, Mentor workflow, ระบบชำระเงิน, สร้าง framework ใหม่, เปลี่ยนโดเมน, deploy/commit โดยไม่ได้รับคำสั่ง

**สถานะเอกสาร (อัปเดต 27 พ.ย. 2569):** ปรับเว็บไซต์ใน branch `codex/portfolio-camp-planning` ตามคำสั่งล่าสุดแล้ว: ภาพประกอบมหาวิทยาลัย/การอัดคลิป, คลิปผลงาน, Seniors ก่อน Student Works, Guest ในตาราง และเวลารวมทั้งสามวัน. ทดสอบ rendered website, interactions และ responsive; ยังไม่ deploy/push. ราคา สิทธิ์ภาพ และข้อมูลตาม launch gate ยังรอทีมยืนยัน

## สถานะการดำเนินงาน 27 พฤศจิกายน 2569

- Source: ปรับ `index.html` โดยคง HTML/CSS/Vanilla JS; ลบ HamsVillage 4 Zones, placeholder และ GSAP ที่ไม่ใช้. Showcase ล่าสุดเป็นคลิป 7 ผลงานจากชีตในแถวเดียว; เพิ่มรูปพี่ก๊อกที่ผู้ใช้ส่ง, ภาพประกอบ Unsplash 2 ภาพ และบันทึกที่มาใน `assets-sources.md`. ไม่มีภาพ ARAYA ที่ยังไม่ได้รับสิทธิ์.
- Browser QA: Chromium และ Playwright WebKit ที่ 320, 390, 768, 1440px (ยังไม่ได้เปิด Safari app); ไม่มี horizontal overflow หรือ console error. คลิป Showcase ทั้ง 7 เล่นได้จริงทั้งสอง browser, ตารางสลับวัน/เปิดการ์ด Guest ได้, Track แจ้งให้เลือกซ้ำในหน้าสมัคร. การทดสอบก่อนหน้า 360/430px, dialog/Esc/focus, FAQ, carousel, ปิด JavaScript และ reduced motion ยังใช้ผลเดิม; ภาพ lazy-load ที่ยังไม่อยู่ใน viewport ไม่ถือเป็นภาพเสีย.
- Lighthouse mobile ในเครื่องหลังเปลี่ยน Showcase เป็น 7 คลิป: Performance 97, Accessibility 100, SEO 100; LCP 2.6s, CLS 0. ค่าเหล่านี้เป็น lab data จาก local server ไม่ใช่ field data บน GitHub Pages.
- Launch blockers: URL สมัครเดิม `https://www.hamsterhub.co/portcamp` ตอบ HTTP 404 ในวันที่ตรวจ; ตามคำสั่งผู้ใช้ไม่ได้แก้หน้าสมัครหรือ LINE. ยังต้องยืนยันราคา 190 บาท, privacy URL, ช่วงชั้น, ขั้นตอนสมัคร, ตารางบางช่วง, เงื่อนไขเปิดพอร์ต, ข้อมูลวิทยากรและสิทธิ์ภาพผลงาน/รุ่นพี่. ราคากับ privacy link ถูกซ่อน; ไม่ใช้ `?track=`; พอร์ตจริง, โปรไฟล์รุ่นพี่ และภาพ ARAYA ถูกซ่อน; รูปพี่ก๊อกมาจากผู้ใช้.
- Review แบบนักเรียนใหม่: Hero บอกได้ว่าคือค่ายเตรียมพอร์ต/สร้างเกม 3 วัน, เหมาะกับคนมีหรือไม่มีผลงาน, ผลลัพธ์แยกตาม Track และเห็นเหตุผลผ่านผลงานจริง/รุ่นพี่/วิทยากร; วิธีสมัครยังไม่สมบูรณ์เพราะปลายทาง 404.
- ก่อนเปิดเว็บจริง: ให้ทีมยืนยันข้อมูลและสิทธิ์, ส่ง URL สมัครที่ใช้งานได้, ทดสอบกับนักเรียน 2 กลุ่ม, แล้วทดสอบ URL GitHub Pages หลัง deploy. ยังไม่มีการทดสอบกับผู้สมัครจริงหรือ analytics consumer; `dataLayer` ที่ push อยู่ยังไม่ยืนยันว่ามีระบบรับข้อมูล.

## 9. References

- Marketing & Communication — Reality Thinking Toolkit (installed skill; audience, action, claims, mobile copy, measurement)
- Superpowers Writing Plans — https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md (อ่าน source skill ออนไลน์; ประยุกต์ file mapping, task checklist, testable acceptance; ไม่ได้ติดตั้ง plugin)
- Website source — https://github.com/PepesX231/PortfolioCamp/blob/main/index.html
- ARAYA official Steam — https://store.steampowered.com/app/466740/ARAYA/
- Mango Zero, 30 พ.ย. 2559 — https://www.mangozero.com/behind-the-araya-thai-horror-game/
- SSRU — https://fms.ssru.ac.th/news/view/rainny384
- Unsplash license — https://unsplash.com/license
- Asset source pages — §5

### อัปเดตหลังรีวิวภาพและตาราง (27 พฤศจิกายน 2569)

- [x] เพิ่มภาพประกอบการอัดคลิปและห้องเรียนมหาวิทยาลัยจาก Unsplash พร้อมป้ายกำกับและบันทึกที่มาใน `assets-sources.md`
- [x] เพิ่มคลิป COMMAND SELECT ใน Showcase แบบกดเล่นเองในรอบก่อน; รอบล่าสุดแทน Showcase ด้วย 7 คลิปตามชีตที่ผู้ใช้ให้มา
- [x] ย้าย Seniors ก่อน Showcase; ทำการ์ด 3 วันให้กระชับบนมือถือ
- [x] ย้ายพี่ก๊อก/ARAYA เข้าแถวเด่นในตารางวันที่ 5 และกดขยายข้อมูลได้
- [x] เพิ่มเวลารวมวัน 1–3 และกิจกรรม 20:00–21:00 ของวันที่ 5–6
- [x] แก้ข้อความ Track ที่สนใจให้บอกตรง ๆ ว่าต้องเลือกซ้ำในหน้าสมัคร
- [x] ใส่รูปพี่ก๊อกจากไฟล์ที่ผู้ใช้ส่งมา
- [ ] ใส่ภาพเกม ARAYA เมื่อได้รับไฟล์/สิทธิ์ใช้จากเจ้าของ
- [ ] ใส่ปกพอร์ตจริงเมื่อทีมส่งไฟล์ที่ปกปิดข้อมูลส่วนบุคคล (ผู้ใช้ให้รอไว้ก่อน)

### อัปเดตผลงานจากชีตและรูปวิทยากร (27 พฤศจิกายน 2569)

- [x] อ่านชีต `Grade Ex.` โดยใช้เฉพาะชื่อและลิงก์สื่อ ไม่เผยแพร่เกรดหรือคำวิจารณ์
- [x] คัด 7 คลิปให้คละจากหลายช่วง; ดาวน์โหลดและเข้ารหัสใหม่โดยคงความยาวเต็ม; ตัด RE//SLASH
- [x] สร้างภาพ poster จากคลิปแต่ละชิ้นและจัด Showcase เป็นแถวเลื่อนเดียวที่ทุกชิ้นเท่ากัน
- [x] ใส่รูปพี่ก๊อกที่ผู้ใช้ส่งมาในแถววิทยากรของตาราง
- [x] ตรวจคลิปทั้ง 7 ใน Chromium และ WebKit, การเลื่อนแถว, การขยายข้อมูลพี่ก๊อก และ responsive 320/390/1440px
- [ ] ยืนยันสิทธิ์เผยแพร่คลิปผลงานนักเรียนก่อนเปิดเว็บจริง
- [ ] ใส่ภาพ ARAYA เมื่อเจ้าของสิทธิ์ส่งไฟล์ที่ใช้ได้

### อัปเดตการเล่นคลิปและ Git (27 พฤศจิกายน 2569)

- [x] คลิป Showcase ทั้ง 7 เล่นอัตโนมัติแบบปิดเสียงและวนลูปเมื่ออยู่ในจอ; หยุดเมื่อพ้นจอหรือซ่อนแท็บ
- [x] เคารพ reduced motion และการกดหยุดของผู้ชม; ยังมี controls สำหรับกดเล่น/หยุดเอง
- [x] ทดสอบ Desktop/Mobile หลังปรับ autoplay: Chromium และ WebKit ที่ 1440×900/390×844 ผ่าน; ตอนเปิดหน้าไม่โหลดคลิป Showcase, เมื่อเข้าจอเล่นจริงแบบ muted/loop, เลื่อนพ้นจอหยุด, reduced motion ไม่เล่นเอง, กดหยุดเองแล้วไม่เริ่มใหม่; Lighthouse mobile 97/100/100, LCP 2.6s, CLS 0
- [ ] Commit และ push branch `codex/portfolio-camp-autoplay` — อัปเดตหลัง push สำเร็จ
