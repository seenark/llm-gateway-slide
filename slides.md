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

## ตัวกลางที่ขาดไม่ได้ (The New Standard)

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10">
    กด Space เพื่อเริ่ม <carbon:arrow-right class="inline"/>
  </span>
</div>

---

# Part 1: ส่องตลาด (Industry Overview)

---

# LLM Gateway Market 2026

## ตัวกลางที่ขาดไม่ได้ (The New Standard)

**Industry Name:** AI Infrastructure (LLM Gateway / Proxy)

**Status:** ปี 2026 ไม่มีใครยิง API ตรงไปหา OpenAI/Anthropic แล้ว

<v-click>

**Selected Subvertical:** <span v-mark.yellow.highlight>"Smart Routing or Prompt-Aware Gateways", "Performance" & "Unified API"</span>

</v-click>

<v-clicks>

**Why This Matters?**

- คุมยาก: เรื่องเงิน ความปลอดภัย และความเร็ว
- Gateway ทั่วไปทำได้แค่ส่งข้อมูล แต่เราต้องการตัวที่ "อ่าน Prompt ออก"

**Stakeholders**

- User: Dev / Platform Engineer
- Buyer: CTO / CFO (ที่อยากลดบิลค่า AI)

</v-clicks>

---

# Inference Graphs

## เมื่อ Gateway ไม่ใช่แค่ทางผ่าน 

<v-click>

แทนที่จะยิง A to B จบไป แต่มันคือการวาง Logic ต่อกันเหมือน Flowchart ภายใน Gateway

</v-click>

<v-clicks>

#### Example Flow

1. Node 1: ใช้ Model เล็ก เช็คก่อนว่าคำถามเกี่ยวกับอะไร
2. Node 2: ถ้าเป็นเรื่องยาก ส่งไป GPT-5 ถ้าเรื่องง่าย ส่งไปโมเดลถูกๆ
3. Node 3: เอาคำตอบมาผ่าน Guardrail เช็คความถูกต้อง
4. Fallback: ถ้า Node 2a ตาย ให้ยิงไป Claude sonnet แทนอัตโนมัติ

#### Benefits

- ระบบไม่ล่ม (Resilient) - มี Fallback อัตโนมัติ
- ประหยัดเงินได้มหาศาล - เลือกโมเดลที่เหมาะสมกับงาน
- ความยืดหยุ่น - เปลี่ยน Logic ได้โดยไม่ต้องแก้ Code

</v-clicks>

---

# Pain Points ที่เจอในตลาดตอนนี้

## ปัญหาที่ทำให้คนปวดหัว

<v-clicks>

### 🐌 Latency Tax

พวก Gateway ที่เขียนด้วย Python/Node มัน<span v-mark.underline.red>ช้าเกินไป</span>สำหรับงาน Real-time

### 🔥 The "JSON Break"

โมเดลฉลาดแค่ไหน บางทีก็ส่ง Format เพี้ยน ทำเอา App พัง

### 🔒 Privacy Fear

ไม่อยากให้ Log วิ่งผ่าน Cloud ของคนอื่น อยากรันเองในเครื่อง/On-prem

### 📈 Adoption Stage

ตอนนี้อยู่ในช่วง Growing คนเริ่มรู้แล้วว่าต้องมี แต่ยังหาตัวที่ "ใช้ง่ายและเร็ว" จริงๆ ไม่เจอ

</v-clicks>

---

# Part 2: สิ่งที่ค้นพบ (Insights)

---

# 3 Case หลักที่คนเอาไปใช้จริง

## ไม่ใช่แค่ Proxy แต่คือ AI Controller

<v-clicks>

### 💾 1. Semantic Caching

ถามซ้ำไม่ต้องยิงใหม่ Gateway จำคำตอบที่ "ความหมายเหมือนกัน" ไว้ให้เลย

<span class="text-green-600 font-bold">ลดบิลได้ 30-50%</span>

### 🛡️ 2. Output Guardrailing

เช็คคำตอบก่อนส่งถึงมือ User ถ้า AI ตอบมั่วหรือ Format ผิด Gateway แก้ให้เลย

### ⚡ 3. Local-First / Edge

รัน Gateway ไว้ใกล้ตัวที่สุด (เช่นใน Edge หรือ Laptop) เพื่อลดความหน่วง

### 💡 Surprising Insight

คนเริ่มเบื่อการจ่ายเงินแบบ Aggregator (OpenRouter) และอยากใช้ Key ตัวเอง (<span v-mark.yellow.highlight>BYOK</span>) เพราะการ subscribe มันดูคุ้มกว่าการเติม credit

</v-clicks>

---

# โอกาสของ Rust Gateway

## The "Caddy" of AI

<v-clicks>

### 😰 ปัญหาของคู่แข่ง

**TensorZero/Plano** - เก่งเทพนะ แต่วุ่นวาย Setup ยากเหมือนต้องรื้อบ้านใหม่

**LiteLLM** - ต่อได้ทุกโมเดลจริง แต่ช้าและกิน Resource

### 🎯 โอกาสของเรา

**Winning Wedge** - เราต้องเป็น "Single Binary" ไฟล์เดียวจบ รันปุ๊บได้ปั๊บ (DX เหนือกว่า)

**API First** - มี API ให้ครบสำหรับ admin และ user ทำให้องค์กรณ์สามารถสร้าง Custom UI ของตัวเองแล้วนำมา plug เข้ากับระบบได้ง่าย

**Extendable** - ขยายความสามารถได้ด้วย Wasm Plugins (อยากได้ Logic อะไรเพิ่ม เขียนปลั๊กอินมาเสียบเอา)

</v-clicks>

---

# Part 3: Research Workflow

---

## เป้าหมาย

<v-clicks>

เน้นสปีด! เพื่อให้เห็นภาพรวมของตลาด Gateway ทั้งหมดภายก่อน

### Process

1. **Decide Industry** - เราเริ่มจากมองหา AI/LLM Gateway ที่กำลังมาแรงในปี 2026

2. **Subcategories** - พอดีตรงนี้มี partner หลายๆคนถามถึงเรื่องนี้อยู่ตลอด

3. **Pick a Startup** - เราจิ้มไปที่ LiteLLM (ตัวดัง) แล้วกางแผนที่หาคู่แข่งทันที

4. **Identify Pain** - เจอจุดตายคือ "คนต้องมานั่งเขียน Logic เช็ค JSON เองซ้ำๆ" บางครั้งมี latency เยอะ รับใช้งานพร้อมๆกันแล้วมีปัญหา หรือการ setup ยุ่งยากก็มีส่วน

</v-clicks>

---

# โชว์ Prompt ที่ใช้ปั้น Research นี้ขึ้นมา

## ใช้ AI ยังไงให้ได้ "เนื้อ" ไม่ได้ "น้ำ"

<v-clicks>

### Prompt Template

```markdown
You are an AI Product Strategist...
perform an Industry Spike Analysis...
Identify real-world LLM Gateway opportunities...
```

### วิธีการ

เราใช้ Prompt นี้ยิงใส่ AI เพื่อให้มันช่วย Map Sub-Sector ออกมาเป็น 4 กลุ่ม: Aggregators, Adapters, Control Planes, Orchestrators

### ผลลัพธ์

ทำให้เราเห็น **"Market Gap"** ทันทีว่าคนส่วนใหญ่ยังแก้ปัญหาเรื่อง <span v-mark.underline.red>"Decision translation"</span> (การเอาผลลัพธ์ AI มาใช้งานต่อ) ได้ไม่ดีพอ

</v-clicks>

---

# เมื่อเริ่มจริงจัง

## Hybrid Mode (AI + Manual)

<v-clicks>

### Step 1: Map the Industry

วิเคราะห์ว่าใครเป็นคนจ่าย?
- User: Dev ที่เหนื่อยกับการต่อ API
- Buyer: CFO ที่เห็นบิลค่า Token แล้วอยากจะร้องไห้

### Step 2: Competitive Teardown

ทำ PM Info Pack ชำแหละคู่แข่งรายตัว - TensorZero, Portkey, Cloudflare

### Step 3: Analyze MOAT

ดูว่าใครมี "กำแพง" ตรงไหน?
- Portkey มี UI สวย (Dashboard)
- TensorZero มีความเร็ว (Rust)

</v-clicks>

---

# การหา Gap และจุดตาย

## Gap Analysis

<v-clicks>

### วิธีการ

**Missing Features** - เราลองใช้ AI ช่วยหาว่า "เครื่องมือที่มีอยู่ ขาดอะไร?"

**Poor UX** - AI ชี้เป้าว่าพวก Rust Gateway ตอนนี้ใช้ยากเกินไปสำหรับมือใหม่

### Manual Recheck

ผมไม่ได้เชื่อ AI ทั้งหมด! ผมเข้าไปขุดใน GitHub Issues ของ LiteLLM และ Portkey เพื่อดูว่า User บ่นเรื่องอะไรจริงๆ

### Finding

พบว่า "ความเสถียรของ Output" (Reliability) คือปัญหาที่คนยอมจ่ายเงินแก้ที่สุด

</v-clicks>

---

# สรุปผลลัพธ์

## จาก Raw Data สู่ MVP Strategy

<v-clicks>

<span class="text-2xl font-bold"><span v-mark.red.underline>AI Builder MVP Opportunity</span></span>

### จากกระบวนการทั้งหมด

เราสรุปออกมาได้เป็น **"The Caddy of AI Gateways"**

### Design Concept

เป็น AI Agent ในตัวที่แปลง **[Raw Prompt]** ไปเป็น **[Actionable JSON]** โดยใช้ Rust เพื่อความไว

### Tagline

<div class="p-4 bg-gradient-to-r from-blue-100 to-purple-100 rounded-lg text-center text-xl font-bold my-4">

"From Raw Input to Real-World Outcome"

</div>

### หัวใจสำคัญ

กระบวนการนี้เน้น **Speed of Learning** เราไม่ได้ต้องการความเป๊ะตั้งแต่แรก แต่เราต้องการ "Wedge" ที่จะเข้าไปเจาะตลาดได้จริง!

</v-clicks>

---

# Part 4: ข้อจำกัดของ AI และการตัดสินใจ

---

# จุดที่ AI พาหลงทาง

## Hallucinations

<v-clicks>

### ความผิดพลาด

AI บอกว่าตัวนั้นตัวนี้ทำ <span v-mark.red.strike>"Native Semantic Caching"</span> ได้แล้ว

### ความจริง

พอไปเช็คใน Code จริงๆ ฟีเจอร์นั้นยังอยู่ใน Roadmap หรือต้องต่อ External DB วุ่นวาย

### ต้องเช็คซ้ำ

ต้องไปไล่ดู CHANGELOG.md หรือหน้า Pull Requests ใน GitHub ถึงจะรู้ว่ามัน "มีจริง" หรือแค่ "โม้ไว้ก่อน"

</v-clicks>

---

# เรื่องของ "ความรู้สึก" และ "วัฒนธรรมองค์กร"

## สิ่งที่ AI คำนวณไม่ได้

<v-clicks>

### 🤖 AI Analysis

AI อาจจะบอกว่า "Cloud-based" ดีที่สุดเพราะ:
- สเกลง่าย
- ดูแลรักษาไม่ยาก
- เข้าถึงได้จากทุกที่

### 👨‍💻 Human Judgment

แต่มนุษย์รู้ว่า: องค์กรไทยหรือธนาคารมี "กำแพงความกลัว" เรื่องข้อมูลหลุด

ดังนั้น Gateway แบบ **Local/Self-hosted** ถึงจะขายออก

### 💡 Lesson

เราเลือกเน้น **Privacy-First** เพราะเข้าใจ Stakeholder Incentives มากกว่า AI

</v-clicks>

---

# การก้าวข้ามข้อมูลที่ล้าสมัย

## AI ไม่รู้หรอกว่าวันนี้ Dev เปลี่ยนใจแล้ว

<v-clicks>

### 📚 AI Recommendation

AI มักจะแนะนำ Library เก่าๆ ที่คนใช้เยอะ เช่น: **LiteLLM** (Python-based)

เพราะ Training data มันเห็นว่าคนใช้เยอะในอดีต

### 🚀 การตัดสินใจของเรา

เราเลือกแทงข้าง **Rust (TensorZero/Plano)**

เพราะเห็นแนวโน้มความต้องการเรื่อง <span v-mark.underline>Low-latency</span> ที่พุ่งสูงขึ้นในปี 2026

</v-clicks>

---

# Part 5: เคล็ดลับการวิจัย (Tips & Prompts)

---

# Prompt ที่ใช้แล้วเวิร์กจริง

## Effective Prompt

<v-clicks>

### 🎯 อยากได้เนื้อๆ ไม่เอาต้นไม้

```markdown
สวมบทเป็น Principal Product Strategist
เปรียบเทียบ [A] กับ [B]
เอาเฉพาะจุดต่าง (Differentiators) กับจุดอ่อนพอ
ฟีเจอร์พื้นฐานไม่ต้องพูดถึง
แล้วขอที่มา (Citations) จาก GitHub หรือ Docs จริงๆ ด้วย
```

### ✨ ผลลัพธ์

ลดเวลาอ่าน Marketing BS ไปได้ 80% ได้แต่เนื้อที่ต้องใช้ตัดสินใจจริงๆ

</v-clicks>

---

# เคล็ดลับ "GitHub over Google"

## แหล่งข้อมูลที่จริงใจที่สุด

<v-clicks>

### ❌ Google Search

ในโลก Developer Tools:
- ข้อมูลใน Google = SEO ขยะ
- Tutorial เก่า
- Blog post ที่ไม่อัปเดต

<span class="text-red-500">→ Misleading Information!</span>

### ✅ GitHub คือแหล่งความจริง

| ที่ | บอกอะไร? |
|---|---|
| README | สิ่งที่ผู้สร้าง เคลม |
| Issues | จุดตาย ที่หน้าเว็บไม่บอก |
| Discussion | คนบ่นเรื่องอะไร ตรงไหนพัง |
| Pull Requests | ฟีเจอร์ไหนที่เขาอยากได้ |

### 💡 Action

ให้ไปดูหน้า Issues กับ Discussion ใน GitHub เพื่อดูว่าคนบ่นอะไร ตรงไหนพัง ฟีเจอร์ไหนที่เขาอยากได้แต่เจ้าของยังไม่ทำ นั่นแหละคือ **Opportunity** ของเรา

</v-clicks>

---

# สิ่งที่ต้องแก้ตัวครั้งหน้า

## Improvement

<v-clicks>

### 🚨 Lesson Learned

เวลาทำ Research เรื่องที่ขยับเร็วๆ (อย่าง AI 2026) ต้องย้ำ AI เสมอว่า

**"เอาข้อมูล 6 เดือนล่าสุดเท่านั้น"**

เพื่อกันไม่ให้มันไปขุดเอา "ความรู้คลาสสิก" ที่ตอนนี้เขาไม่ทำกันแล้ว (เช่น การรัน Proxy ด้วย Python ในงาน High-scale) มาตอบเรา

### ✅ Best Practice

**Explicit Time Constraints:**

1. ระบุเลยว่าข้อมูลชุดไหนเก่ากว่า 6 เดือน - ติดป้าย [Possibly Outdated]

2. ให้คะแนนน้ำหนัก:
   - โปรเจกต์ที่มี Activity ในรอบ 30 วัน
   - มีน้ำหนัก > โปรเจกต์ตาย

3. Impact: ไม่หลงทางไปแข่งกับเทคโนโลยีที่กำลังจะตกรุ่น

</v-clicks>

---

layout: end
class: text-center

---

# ขอบคุณครับ

<div class="pt-12">

## 🙏 Thank You!

การวิจัยนี้เป็นการร่วมมือกันระหว่าง
**Human Expertise** + **AI Assistance**

<br/>

<div class="text-sm opacity-75 mt-8">

Questions? Discussion?

<br/>

<span class="text-lg">📧 Let's connect!</span>

</div>

</div>
