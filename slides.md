---
theme: bricks
background: https://cover.sli.dev
title: LLM Gateway Research 2026
info: |
    การวิจัยตลาด LLM Gateway และโอกาสทางธุรกิจ
    ประจำเดือนกุมภาพันธ์ 2026
class: text-center
drawings:
    persist: false
transition: slide-left
mdc: true
duration: 45min
---

# LLM Gateway Market 2026

## The New Standard for Business

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10">
    Let's see<carbon:arrow-right class="inline"/>
  </span>
</div>

---

# 🟣 Part 1: ส่องตลาด

# (Industry Overview)

---

# LLM Gateway Market 2026

## The New Standard for Business

<v-clicks>

**Industry Name:** AI Infrastructure (LLM Gateway / Proxy)

**Status:** ปี 2026 หลายองค์กรณ์ต้องการให้พนักงานใช้ AI ช่วยในการทำงาน และอยากควบคุมหลายๆอย่างด้วยตัวเอง
เพราะมันอยากควบคุม ทั้งเรื่องบิล ความปลอดภัย และความเร็ว

**Selected Subvertical:** <span v-mark.yellow.highlight>"Smart Routing", "Prompt-Aware Content Routing", "Performance" & "Security"</span>

**ทำไมต้องกลุ่มนี้?:**

เพราะมันไม่ใช่แค่ส่งข้อมูลผ่านท่อ
แต่มัน <span v-mark.underline.red>"อ่านไส้ใน"</span> ของ Prompt ออก
เพื่อเลือกเส้นทางที่คุ้มและดีที่สุดสำหรับงานนั้นๆ

**User / Buyer**

- **User:** Dev / Platform Engineer
- **Buyer:** CTO / CFO (ที่อยากคุม Cost AI ไม่ให้บานปลาย)

</v-clicks>

---

# วิวัฒนาการของ Proxy

## จาก "ท่อส่ง Data" สู่ "Brain ของ Workflow"

<v-clicks>

### 📅 2023-2024: ยุคเริ่มแรก

เน้นแค่ต่อให้ติด แปล Schema ให้ใช้ด้วยกันได้
_(ยุคทองของ **LiteLLM**)_

### 📅 2025: เริ่มมีสมอง

- ทำ **Semantic Caching** (จำคำตอบที่ความหมายคล้ายกัน)
- ใส่ **Guardrails** มาให้เป็นมาตรฐาน

### 📅 2026 (ปัจจุบัน): ยุค Payload-aware

- Gateway อ่านไส้ใน Prompt ออก
- ขยายความสามารถด้วย **Wasm Plugins**
- และที่สำคัญที่สุดคือ <span v-mark.yellow.highlight>การทำ **Inference Graphs**</span>

### 🔄 การเปลี่ยนแปลง

เราย้ายจากการเป็นแค่ "ทางผ่าน" (Connectivity)
ไปสู่การเป็น "คนคุมกฎและใส่ Logic" (Governance & Logic)

</v-clicks>

---

# เจาะลึก Inference Graphs

## เมื่อ Gateway วางแผนการยิง AI เองได้

<v-click>

**Inference Graphs คืออะไร?:**

แทนที่จะส่งคำถามไปแล้วรอคำตอบแบบทื่อๆ
เราสามารถวาง Logic ต่อกันเป็น Flow ภายใน Gateway ได้เลย
_(Inference as Code)_

</v-click>

<v-clicks>

### ตัวอย่าง Logic ใน Graph

<div class="grid grid-cols-2 gap-4">

<div>

**Node 1: Classifier**

ใช้โมเดลเล็ก (และถูก) เช็คก่อนว่าคำถามคือเรื่องอะไร?

**Node 2: Branching**

- ถ้าเป็นเรื่อง Coding → ส่งไป GPT-5
- ถ้าเป็นเรื่องระบายความร้อน → ส่งไปโมเดลเฉพาะทาง

</div>

<div>

**Node 3: Fallback**

ถ้าโมเดลหลักตอบช้าเกิน 2 วิ
ให้สลับไปยิงโมเดลสำรองทันที

**Node 4: Validator**

เอาผลลัพธ์มาเช็ค JSON Schema
ถ้าพังให้ "วนกลับไปซ่อม" ก่อนส่งถึง App

</div>

</div>

### ✨ Benefit

- ระบบไม่มีล่ม (Resilient)
- ประหยัดเงินมหาศาล
- App ไม่พังเพราะ Format เพี้ยน

</v-clicks>

---

# ปัญหาหลัก (Pain Points) ในปี 2026

## ราคาที่ต้องจ่ายให้กับความซับซ้อน

<v-clicks>

### 🐌 Latency Tax

พวก Proxy ที่เขียนด้วย Python มันสร้าง Overhead สูงเกินไป
ไม่ทันใจสำหรับการทำ Streaming ความเร็วสูงในปี 2026

### 🔧 Config Fatigue

เครื่องมือใหญ่ๆ อย่าง Envoy หรือ Kong
มันหนักและตั้งค่ายุ่งยากเกินไป
_(Complex เกินไปสำหรับทีมที่อยาก Move fast)_

### 🚨 Reliability Gap

ต่อให้โมเดลฉลาดขึ้น แต่มันก็ยังมี
<span v-mark.underline.red>**Schema Validation Fail**</span> (ตอบ JSON ผิด format) อยู่เรื่อยๆ

Gateway เลยต้องมีหน้าที่ <span v-mark.yellow.highlight>"ซ่อม" (Heal)</span> ข้อมูลก่อนส่งถึงแอป

</v-clicks>

---

# 🔵 Part 2: เจาะกลุ่มผู้เล่น

# (Market Taxonomy)

---

# 4 กลุ่มหลักในตลาด LLM Gateway

## ใครทำอะไรในตลาดนี้?

<v-clicks>

<div class="grid grid-cols-2 gap-8">

<div>

<div class="mb-6">

### 1️⃣ Aggregators

**(สายรวมศูนย์)**

ถือ API Key เดียว ยิงได้ทุกโมเดล
เน้นสะดวก จัดการ Billing ง่าย

<div class="text-sm opacity-75 mt-2">

📌 เช่น: OpenRouter

</div>

</div>

<div>

### 2️⃣ Adapters

**(สายหัวแปลง)**

เน้นทำ Standardize
แปลงทุกอย่างให้เป็น OpenAI Format
เพื่อให้ Code ไม่พังเวลาเปลี่ยนค่าย

<div class="text-sm opacity-75 mt-2">

📌 เช่น: LiteLLM

</div>

</div>

</div>

<div>

<div class="mb-6">

### 3️⃣ Control Planes

**(สายหอบังคับการ)**

เน้น Governance, ระบบ Log, Caching
และ UI สวยๆ ให้คนคุมระบบดู

<div class="text-sm opacity-75 mt-2">

📌 เช่น: Portkey, Cloudflare

</div>

</div>

<div>

### 4️⃣ Orchestrators

**(สายสมองกล)**

เน้น Logic หนักๆ
ทำ Inference Graphs และ Smart Routing
เพื่อแก้ปัญหาเรื่องการเอาผลลัพธ์ไปใช้งานต่อ

<div class="text-sm opacity-75 mt-2">

📌 เช่น: TensorZero, Plano

</div>

</div>

</div>

</div>

</v-clicks>

---

# 🟢 Part 3: วิธีการวิจัย

# (Research Workflow)

---

# Research Mode 1: Fast Mode ⚡

<v-clicks>

<div class="space-y-4">

### Step 1: เลือก Industry

เลือก Industry (LLM Gateway)
และส่องดู Github open source

### Step 2: จิ้ม ตัวที่ star เยอะหน่อย

จิ้มมา 1 ตัว (LiteLLM)
แล้วหาคู่แข่งรอบๆ ทันที

### Step 3: หา Painful, Repeated Task

หา <span v-mark.underline.red>**Painful, Repeated Task**</span> ที่ User ต้องทำ
_(เช่น การมานั่งเขียน Code เช็ค JSON ซ้ำๆ)_

### Step 4: เทียบโซลูชัน

เทียบโซลูชันเดิม (Non-AI) กับของใหม่ (AI)
เพื่อหาจุดแข็งจุดอ่อน

</div>

<div class="p-1 bg-gradient-to-r from-yellow-100 to-orange-100 rounded-lg text-center font-bold my-4">

🎯 Goal: เน้นความเร็วในการเรียนรู้ ไม่เน้นเป๊ะ!
_(Speed of learning, not perfection)_

</div>

</v-clicks>

---

# ตัวอย่างเคส เบื้องหลังการทำข้อมูลสไลด์ชุดนี้

<v-clicks>

### 🔍 Manual Research

ผมเข้าไปขุดใน **GitHub Issues** ของ LiteLLM
เพื่อดูว่า Dev บ่นเรื่องอะไรจริงๆ

<div class="p-3 bg-green-50 border-l-4 border-green-500 my-3">

📌 พบว่าคนบ่นเรื่อง <span v-mark.underline>**Latency ของ Python**</span> เยอะมาก

</div>

### 🤖 AI Analysis

ให้ AI ช่วยเปรียบเทียบข้อดีข้อเสียของ Rust vs Go vs Python
เพื่อเลือกว่าจะสร้าง Gateway ด้วยภาษาอะไรดี

### 💡 Insight

พบว่าความเชื่อที่ว่า <span v-mark.red.strike>"Feature เยอะคือดี"</span> มันผิด!

Dev จริงๆ ต้องการ
<span v-mark.yellow.highlight>**"ตัวที่รันง่ายที่สุดไฟล์เดียวจบ"**</span>
_(Single Binary)_

</v-clicks>

---

# 🟡 Part 4: ข้อจำกัดของ AI และการตัดสินใจ

# (Human Judgment)

---

# จุดที่ AI พาหลงทาง (Hallucinations)

## อย่าเชื่อ AI 100%

<v-clicks>

### ❌ ความผิดพลาด

AI บอกว่าตัวนั้นตัวนี้ทำ
<span v-mark.red.strike>**"Native Semantic Caching"**</span> ได้แล้ว

### ✅ ความจริง

พอไปเช็คใน Code จริงๆ
ฟีเจอร์นั้นยังอยู่ใน Roadmap
หรือต้องต่อ External DB วุ่นวาย

### 🔍 ต้องเช็คซ้ำ

ต้องไปไล่ดูหน้า **Pull Requests** ใน GitHub
ถึงจะรู้ว่ามัน "มีจริง" หรือแค่ "โม้ไว้ก่อน"

</v-clicks>

---

# เรื่องของ "ความรู้สึก" และ "DX"

## สิ่งที่ AI คำนวณไม่ได้

<v-clicks>

### 🤖 AI Analysis

AI มักจะจัดอันดับเครื่องมือตาม
_จำนวน_ ฟีเจอร์ที่ระบุไว้

### 👨‍💻 การตัดสินใจโดยมนุษย์

เราตระหนักว่าเครื่องมือที่มีฟีเจอร์ _น้อยกว่า_
แต่ติดตั้งง่ายไฟล์เดียวจบ (Single Binary)

<span v-mark.yellow.highlight>ชนะขาดในแง่ Developer Experience (DX)</span>

<div class="p-4 bg-blue-100 border-l-4 border-blue-500 rounded my-4">

💡 Lesson: Feature ไม่ใช่ทุกอย่าง
**ความง่ายในการใช้งานคือ King**

</div>

</v-clicks>

---

# 🟠 Part 5: เคล็ดลับการวิจัย

# (Tips & Prompts)

---

# Prompt ที่ใช้แล้วเวิร์กจริง

## อยากได้เนื้อๆ

<v-clicks>

### 🎯 Prompt

```markdown
สวมบทเป็น Principal Product Strategist
เปรียบเทียบ [A] กับ [B]
เอาเฉพาะจุดต่าง (Differentiators) กับจุดอ่อนพอ
ฟีเจอร์พื้นฐานไม่ต้องพูดถึง
แล้วขอที่มา (Citations) จาก GitHub หรือ Docs จริงๆ ด้วย
```

### ✨ ผลลัพธ์

ลดเวลาอ่าน ไปได้พอสมควร
ได้แต่เนื้อที่ต้องใช้ตัดสินใจจริงๆ

</v-clicks>

---

# เคล็ดลับ "GitHub over Google"

## แหล่งข้อมูลที่จริงใจที่สุด

<v-clicks>

### ❌ Tip: ค้นหาใน Google

จะเจอแต่หน้า Sale กับ SEO Spam

### ✅ Action: ให้ไปดูหน้า Issues กับ Discussion

ใน GitHub เพื่อดูว่าคนบ่นอะไร
ตรงไหนพัง นั่นแหละคือ <span v-mark.yellow.highlight>**Opportunity**</span>

<div class="grid grid-cols-2 gap-4 mt-4">

<div>

**❌ Google Search**

- SEO ขยะ
- Tutorial เก่า
- Blog post ไม่อัปเดต

<span class="text-red-500">→ Misleading!</span>

</div>

<div>

**✅ GitHub**

| ที่           | บอกอะไร?                  |
| ------------- | ------------------------- |
| README        | สิ่งที่ผู้สร้าง เคลม      |
| Issues        | จุดตาย ที่หน้าเว็บไม่บอก  |
| Discussion    | คนบ่นเรื่องอะไร ตรงไหนพัง |
| Pull Requests | ฟีเจอร์ไหนที่เขาอยากได้   |

</div>

</div>

</v-clicks>

---

# การคุมเข้มเรื่อง "วันที่" (Current Date)

## การปรับจูนข้อมูลสำหรับอนาคตปี 2026

<v-clicks>

### 📚 Lesson

เวลาทำ Research เรื่องที่ขยับเร็วๆ
ต้องย้ำ AI เสมอว่า

<div class="p-4 bg-yellow-100 border-l-4 border-yellow-500 rounded my-4 font-bold text-lg">

**"เอาข้อมูล 6 เดือนล่าสุดเท่านั้น"**

</div>

### ❓ ทำไม?

เพื่อกันไม่ให้มันไปดึงความรู้เก่าที่ล้าสมัยไปแล้วมาตอบเรา

</v-clicks>

---

# Next

## จากข้อมูล สู่การลงมือสร้าง

<v-clicks>

### 🎯 Goal

เราจะสร้าง <span v-mark.yellow.highlight>**"The Caddy of AI Gateways"**</span>

### 🛠️ Strategy

- **ใช้ Rust** - เพื่อความเร็ว
- **Single Binary** - เพื่อ DX
- **Wasm** - เพื่อความยืดหยุ่น

### 🚀 Next Step

เริ่มทำ Prototype ตัวแรก รองรับ Semantic Cache และ Basic Inference Graph

<div class="my-8 p-2 bg-gradient-to-r from-purple-100 to-blue-100 rounded-xl">

<div class="text-4xl mb-2">🙏 Thank You!</div>

การวิจัยนี้เป็นการร่วมมือกันระหว่าง
**Human Expertise** + **AI Assistance**

<br/>

<div class="text-sm opacity-75 mt-4">

Questions? Discussion?
📧 Let's connect!

</div>

</div>

</v-clicks>
