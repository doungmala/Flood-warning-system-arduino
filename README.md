#  Flood-warning-system-arduino

อุปกรณ์ที่ต้องใช้

Ultrasonic Sensor (HC-SR04) Arduino

ยิงคลื่นเสียงลงไปวัดระยะผิวน้ำ

คำนวณความสูงน้ำได้แม่น

Water Level Sensor / Water Sensor

เหมาะกับ:

แจ้งเตือนน้ำเริ่มท่วม

Rain Sensor (เซ็นเซอร์ฝน)

ตรวจว่าฝนตกหรือไม่

ใช้ร่วมกับระดับน้ำ → คาดการณ์น้ำขึ้น

ใช้ทำ logic เช่น

ฝนตกหนัก + ระดับน้ำเพิ่มเร็ว = แจ้งเตือนล่วงหน้า

Logic การแจ้งเตือน

ค่าอินพุตที่ระบบใช้

waterLevelCm = ระดับน้ำ (cm) จาก Ultrasonic

raining = ฝนตกไหม (จาก rain sensor)

waterTouch = น้ำโดนเซ็นเซอร์แล้วไหม (จาก water sensor) (ถ้ามี)

riseRate = “ความเร็วระดับน้ำเพิ่ม” (cm/min) เพื่อเตือนล่วงหน้า

ระดับสถานะ (ตัวอย่างปรับได้)

NORMAL (ปกติ)

waterLevelCm < 30

WATCH (เฝ้าระวัง)

30 ≤ waterLevelCm < 60 หรือ raining == true

WARNING (เตือนภัย)

waterLevelCm ≥ 60 หรือ waterTouch == true

EARLY WARNING (เตือนล่วงหน้า)

ถ้า raining == true และ riseRate ≥ 10 cm/min (น้ำขึ้นเร็วผิดปกติ)

Wiring (Arduino UNO/NANO)

HC-SR04

VCC → 5V

GND → GND

TRIG → D9

ECHO → D8 (UNO รับ 5V ได้)

Rain Sensor (ใช้ขา DO ง่ายสุด)

VCC → 5V

GND → GND

DO → D2 (ปรับ pot ที่บอร์ดฝนให้ threshold พอดี)

Water Sensor (ถ้ามี)

AO → A0 (หรือ DO → D3 ก็ได้)

VCC 5V, GND

Buzzer/LED

Buzzer → D6 (ผ่านทรานซิสเตอร์ถ้าเป็นไซเรน/กินกระแสสูง)

LED เขียว D3 / เหลือง D4 / แดง D5 (ใส่ R 220Ω)

จุดที่ต้อง “วัดจริง” ก่อนใช้งาน

REFERENCE_DISTANCE_CM

คือระยะจากหัว Ultrasonic ถึง “พื้น/ก้นคลอง/จุดอ้างอิงตอนน้ำแห้ง”

TH_WATCH, TH_WARN

ตั้งตามระดับที่ต้องการเตือนจริงในพื้นที่

ถ้าใช้ water sensor: WATER_TOUCH_THRESHOLD

ดูค่า analogRead(A0) ตอนแห้ง/เปียกแล้วตั้ง threshold กลางๆ

*****************************************************************************

ช่องทางติดต่อ:

ชื่อ : ภาธสุ ดวงมาลา

ตำแหน่ง : R&D Manager

Tel : 0641900551

E-mail : nextsoftware.pp@gmail.com

Line : https://lin.ee/THH8PAt

Medium : https://dr-pathasu-doung.medium.com

Website : https://nextsoftwarethailand.com, https://autoworks24.com

บริษัท เน็กซ์ ซอฟต์แวร์ จำกัด 

ที่อยู่ หมู่บ้าน inizio เลขที่ 888/257 ถนนมะลิวัลย์ ตำบลบ้านทุ่ม อำเภอเมืองขอนแก่น จังหวัดขอนแก่น 40000 เลขที่ผู้เสียภาษี : 0405558003118

ผลงานและประวัติการทำงาน

สามารถดูผลงานและประวัติการทำงานได้ที่

AI, Image Processing : https://www.dropbox.com/scl/fi/tskimhifw0hlcdea5e8t8/Next-Software-2026.pdf?rlkey=f26k2b7t69doklzwxyx54qsmh&dl=0

IoT : https://www.dropbox.com/scl/fi/a5mj4ucjotjv4xrh6sh9q/NS_IOT2025.pdf?rlkey=t0cwl0l4b81w73do2drhqqjp0&dl=0

SEO, Website : https://www.dropbox.com/scl/fi/4q811q0s88xtd8usf5e25/WEB-DEVELOPER-SEARCH-ENGINE-OPTIMIZATION.pdf?rlkey=nvqvndrxv7v9yrfmlcgtplmtx&dl=0
