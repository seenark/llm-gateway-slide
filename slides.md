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

# การวิจัยตลาด LLM Gateway

## โอกาสทางธุรกิจและแนวโน้มปี 2026

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn" title="GitHub">
    <carbon:logo-github />
  </a>
</div>

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer hover:bg-white hover:bg-opacity-10">
    กด Space เพื่อเริ่ม <carbon:arrow-right class="inline"/>
  </span>
</div>

<!--
สไลด์เปิด - แนะนำหัวข้อการวิจัย
-->

---

# Part 1: Industry Overview

_ปูพื้นฐาน: เรากำลังดูอะไรอยู่ และทำไมมันถึงสำคัญ?_

---

# LLM Gateway คืออะไร?

<div grid="~ cols-2 gap-8" mt-4">
<div>

## Definition

**Industry Name:** AI Infrastructure / LLM Gateway

**Status:** กำลังเข้าสู่ยุคที่ 2 (Gen 2: Smart Orchestration)

- **คำนิยาม:** "คนกลาง" (Proxy) อัจฉริยะที่คั่นอยู่ระหว่าง Application กับผู้ให้บริการโมเดล

- **ความสามารถหลัก (Payload-aware):**
    - "อ่านและเข้าใจ" Prompt และ Token
    - ปรับเปลี่ยนเส้นทางได้ทันที

- **ขอบเขต:**
    - ✅ ใช่: Routing, Caching, Governance
    - ❌ ไม่ใช่: Agent Framework หรือ Model Marketplace

</div>

<div>

## 💡 Concept Explained

**API Gateway ปกติ**

> เหมือน "ไปรษณีย์" ที่ส่งจดหมายตามจ่าหน้าซอง โดยไม่สนใจข้างใน

**LLM Gateway**

> เหมือน "เลขาฯ ส่วนตัว" ที่เปิดอ่านจดหมาย
>
> - เรื่องด่วน → ส่งเจ้านาย A
> - เรื่องตลก → ส่งเจ้านาย B
> - ช่วยตรวจคำผิดก่อนส่ง

</div>
</div>

<!--
อธิบายความหมายของ LLM Gateway พร้อมเปรียบเทียบกับ API Gateway ทั่วไป
-->

---

# ภูมิทัศน์ของตลาด

## Market Taxonomy: 4 ประเภทผู้เล่นในตลาด

<div grid="~ cols-2 gap-6" mt-6>

<div>

### 1️⃣ The Aggregators (SaaS)

<v-click>

เน้นรวมทุกค่ายไว้ที่เดียว (One Key fits all)

_ตัวอย่าง:_ OpenRouter, Naga.ai

</v-click>

### 2️⃣ The Polyglot Adapters (OSS)

<v-click>

เน้นแปลงภาษาให้คุยกันรู้เรื่อง (Compatibility)

_ตัวอย่าง:_ LiteLLM (Python), Bifrost (Go)

</v-click>

</div>

<div>

### 3️⃣ The Control Planes (Enterprise)

<v-click>

เน้นการคุมกฎและหน้าบ้านสวยงาม (Governance & UI)

_ตัวอย่าง:_ Portkey, Cloudflare AI Gateway

</v-click>

### 4️⃣ <span v-mark.red.circle>The Inference Orchestrators (Gen 2)</span>

<v-click>

เน้นการประมวลผล Logic ที่ซับซ้อน (Smart Pipes)

**สมรภูมิใหม่!** ← นี่คือจุดน่าสนใจ

_ตัวอย่าง:_ TensorZero (Rust), Plano

</v-click>

</div>

</div>

<!--
แบ่งประเภทผู้เล่นในตลาด โดยเน้นว่า Gen 2 คือสมรภูมิใหม่
-->

---

# ปัญหาและผู้ใช้งาน

## Pain Points & Stakeholders

<div grid="~ cols-2 gap-8" mt-4>

<div>

## Key Stakeholders

<v-clicks>

### 👨‍💻 Developers

- ต้องการความเร็ว (Low Latency)
- ความง่ายในการสลับโมเดล

### 👔 CTO/Finance

- คุม Cost ไม่ให้บานปลาย
- ป้องกัน Vendor Lock-in

### 🛡️ Security

- กรองข้อมูลรั่วไหล (PII)
- ป้องกันก่อนส่งออกไปข้างนอก

</v-clicks>

</div>

<div>

## Major Pain Points

<v-clicks>

### ⚠️ Reliability

โมเดลล่มบ่อย → ต้องมี <span v-mark.underline>ระบบ Fallback อัตโนมัติ</span>

### 🌀 Chaos

ต่างทีมต่างใช้ API Key มั่วซั่ว → ไม่มีศูนย์กลาง

### 🐌 Performance

Gateway เดิมๆ (Python) → เริ่มช้าเมื่อเจอ Traffic มหาศาล

</v-clicks>

</div>

</div>

<!--
สรุปปัญหาหลักและผู้มีส่วนได้ส่วนเสีย
-->

---

# Part 2: Key Findings

_เจาะลึก: สิ่งที่ค้นพบจากการวิจัย และช่องว่างในตลาด_

---

# Use Cases ยอดนิยม

## Top 3 AI Use Cases

<div grid="~ cols-3 gap-4" mt-6>

<div v-click="1" class="p-4 border rounded-lg">

### 💰 1. Cost Optimization via Routing

ฉลาดเลือกโมเดล:

- คำถามง่าย → GPT-4o mini (ถูก)
- คำถามยาก → GPT-4o (แพง)

<span class="text-sm opacity-75">User ไม่รู้ตัว!</span>

</div>

<div v-click="2" class="p-4 border rounded-lg">

### 🛡️ 2. Guardrails & Security

- การป้องกันข้อมูลรั่วไหล (Data Masking)
- การป้องกัน Prompt Injection
- กรอง PII ก่อนส่งออก

</div>

<div v-click="3" class="p-4 border rounded-lg">

### ⚡ 3. Semantic Caching

ถ้ามีคนถามคำถามที่มี "ความหมาย" เหมือนเดิม

→ ตอบจาก Cache ทันที

<span class="text-sm opacity-75">ประหยัดเงินและเร็วมาก!</span>

</div>

</div>

<v-click="4">

<div class="mt-8 p-4 bg-blue-50 rounded-lg border-l-4 border-blue-500">

### 💡 Concept Explained: Semantic Cache

ไม่ใช่แค่การเทียบตัวอักษรเป๊ะๆ (Exact Match)

แต่คือ<span v-mark.underline>การเข้าใจบริบท</span>

เช่น:

- "หวัดดี" ≈ "สวัสดีครับ" → เรื่องเดียวกัน!
- ระบบดึงคำตอบเดิมมาตอบได้เลย

</div>

</v-click>

<!--
อธิบาย Use Case ยอดนิยม 3 อัน พร้อมเจาะลึก Semantic Cache
-->

---

# โอกาสทางธุรกิจ

## The Opportunity (2026)

<div class="text-center text-2xl font-bold mb-6" v-click="1">
<span v-mark.red.underline>The Rust-based, Local-First Gateway</span>
</div>

<div grid="~ cols-2 gap-8" mt-4>

<div>

## 😰 ปัญหาของคู่แข่ง

<v-clicks>

**LiteLLM (Python)**

- ช้าเกินไปสำหรับงาน Scale ใหญ่
- ไม่มี UI ในตัว

**TensorZero (Rust)**

- ซับซ้อนเกินไป
- ต้องรื้อระบบใหม่ (High Friction)

**Portkey**

- ดีแต่ต้องพึ่งพา SaaS Cloud
- ไม่ Private 100%

</v-clicks>

</div>

<div>

## 🎯 โอกาสของเรา

<v-clicks>

### Winning Wedge

สร้าง **"The Caddy of AI Gateways"**

### จุดขาย

- ✅ เป็นไฟล์เดียว (Single Binary)
- ✅ เขียนด้วย Rust (เร็ว)
- ✅ มี UI ในตัว (ไม่ต้องต่อเน็ต)
- ✅ ใช้ง่ายเหมือน Caddy Web Server

</v-clicks>

</div>

</div>

<!--
เจาะจงโอกาสทางธุรกิจ - Rust-based Local-First Gateway
-->

---

# ข้อมูลเชิงลึกที่น่าตกใจ

## Surprising Insights

<div grid="~ cols-3 gap-4" mt-6>

<div v-click="1" class="p-4 border-2 border-red-300 rounded-lg bg-red-50">

### 🔥 Schema คือ WAF ตัวใหม่

ความปลอดภัยที่สำคัญที่สุด:

<span v-mark.underline.red>ไม่ใช่แค่กันคนแฮก</span>

แต่คือการกัน AI "หลอน" จนส่ง JSON พังๆ กลับมา

→ **Structured Output Validation**

</div>

<div v-click="2" class="p-4 border-2 border-orange-300 rounded-lg bg-orange-50">

### 🦀 Rust กำลังกินตลาด

Gateway ยุคใหม่เปลี่ยนจาก Python/Node → Rust/Go เกือบหมด

เพื่อรองรับ Token Streaming ที่ระดับ <span v-mark.circle.orange>Millisecond</span>

</div>

<div v-click="3" class="p-4 border-2 border-yellow-300 rounded-lg bg-yellow-50">

### 🔄 Proxy ธรรมดาไม่พอแล้ว

ตลาดต้องการ **"Inference Graph"**

ใส่ Logic เข้าไปในการเรียก:

- ลองเรียก A ก่อน
- ถ้าไม่มั่นใจ → เรียก B
- เอาผลมาสรุปด้วย C

</div>

</div>

<!--
สรุป Insight ที่น่าสนใจ 3 ข้อ
-->

---

# Part 3: Research Workflow

_เบื้องหลัง: กระบวนการทำงานระหว่างคนกับ AI_

---

# Step 1 - Market Mapping

## 🤖 AI Driven

<div grid="~ cols-2 gap-8" mt-4>

<div>

### เป้าหมาย

กวาดตามองหาผู้เล่นในตลาด

### Tools

<div class="p-4 bg-gray-100 rounded">
- Perplexity
- Google Search
- AI Search Engines
</div>

</div>

<div>

### Action Process

<v-clicks>

1. ใช้ AI ค้นหา:
    - "Open source LLM Gateway 2025-2026"
    - "Rust based AI Proxy"

2. **AI Role:**
    - ช่วยลิสต์รายชื่อโปรเจกต์ใหม่ๆ
    - ที่เราอาจไม่รู้จัก
    - เช่น _Plano_ หรือ _Bifrost_

3. **ผลลัพธ์:**
    - ได้รายชื่อดิบ (Raw List)
    - มาจัดหมวดหมู่

</v-clicks>

</div>

</div>

<!--
อธิบายขั้นตอนแรก - Market Mapping ด้วย AI
-->

---

# Step 2 - Deep Dive & Verification

## 👨‍💻 Manual Heavy

<div grid="~ cols-2 gap-8" mt-4">

<div>

### เป้าหมาย

ตรวจสอบความจริงทางเทคนิค

### Tools

<div class="p-4 bg-gray-100 rounded">
- **GitHub** (Manual Reading)
- Source Code Analysis
- Issue Tracker Review
</div>

</div>

<div>

### Action Process

<v-clicks>

1. **อ่าน Code:**
    - `Cargo.toml` → ดู dependencies
    - หนักแค่ไหน?

2. **อ่าน Issues:**
    - คนบ่นเรื่องอะไร?
    - Bug ซ้ำๆ คืออะไร?

3. **ดู Commit History:**
    - โปรเจกต์ตายหรือยัง?
    - Last commit นานแค่ไหน?

</v-clicks>

<v-click="4">

### ⚠️ ทำไมต้องใช้คน?

AI มักจะอ่านแค่ **README** (ซึ่งเป็นการตลาด)

แต่คนต้องเข้าไปดู **"ความจริง"** ใน Code

</v-click>

</div>

</div>

<!--
อธิบายขั้นตอนที่สอง - Deep Dive ด้วยการอ่าน GitHub เอง
-->

---

# Step 3 - Synthesis & Strategy

## 🤝 Hybrid Approach

<div grid="~ cols-2 gap-8" mt-4>

<div>

### เป้าหมาย

วิเคราะห์หาจุดยืน (Positioning)

### Tools

<div class="p-4 bg-gray-100 rounded">
- **ChatGPT** (as sparring partner)
- SWOT Analysis
- Feature Comparison Matrix
</div>

</div>

<div>

### Action Process

<v-clicks>

1. **ป้อนข้อมูลดิบ:**
    - ข้อมูลที่คัดกรองแล้ว
    - ใส่ลงไปใน AI

2. **สั่งให้ AI วิเคราะห์:**
    - SWOT Analysis
    - เปรียบเทียบฟีเจอร์แบบตาราง
    - หาจุดแข็ง/จุดอ่อน

3. **Human Role:**
    - ตัดสินใจเลือก "Winning Wedge"
    - สู้ที่ความง่าย หรือ ความเร็ว?
    - AI ตัดสินใจทิศทางธุรกิจแทนไม่ได้!

</v-clicks>

</div>

</div>

<!--
อธิบายขั้นตอนที่สาม - Synthesis ร่วมกับ AI
-->

---

# Part 4: AI Limitation & Human Judgment

_จุดบอด: ตรงไหนที่ AI พลาดและต้องใช้คน_

---

# ความผิดพลาดของ AI

## Hallucination: Feature Confusion

<div grid="~ cols-2 gap-8" mt-4>

<div class="p-4 bg-red-50 border-l-4 border-red-500">

### ❌ สิ่งที่ AI บอก

> "LiteLLM เขียนด้วย <span v-mark.red.strike>Rust</span> และมีประสิทธิภาพสูง"

</div>

<div v-click="1" class="p-4 bg-green-50 border-l-4 border-green-500">

### ✅ ความจริง

> LiteLLM เขียนด้วย **Python** 100%

</div>

</div>

<v-clicks>

### 🤔 ทำไม AI ถึงพลาด?

- จำสลับกับโปรเจกต์อื่น
- มั่วข้อมูลเพราะเห็นคำว่า "High Performance" ในโฆษณา
- Training data ล้าสมัย

### 💥 ผลกระทบ

ถ้าเชื่อ AI → วางแผนผิดพลาดเรื่อง Tech Stack ทันที!

</v-clicks>

<!--
ตัวอย่าง AI Hallucination - สับสนระหว่างโปรเจกต์
-->

---

# สิ่งที่ต้องตรวจสอบเอง

## Manual Verification: License & Pricing

<div grid="~ cols-2 gap-8" mt-4">

<div>

### ⚠️ สิ่งที่ AI มักพลาด

<v-clicks>

**รายละเอียดของ License:**

- AI บอก "Open Source"
- จริงๆ เป็น "Source Available"
- ห้ามนำไปทำ SaaS แข่ง!

**Pricing Gates:**

- ฟีเจอร์ SSO ต้องจ่ายเงินเพิ่ม
- Enterprise Gate ที่ซ่อนอยู่

</v-clicks>

</div>

<div>

### 🔍 ทำไม AI พลาด?

<v-clicks>

ข้อมูลพวกนี้มักซ่อนอยู่:

- ในไฟล์ License เล็กๆ
- หน้า Pricing ที่ซับซ้อน
- ไม่ใช่หน้าแรกที่ AI อ่าน

### ✅ Solution

คนต้องเข้าไปอ่าน:

- `LICENSE` file
- `PRICING.md`
- Terms of Service

</v-clicks>

</div>

</div>

<!--
อธิบายว่าทำไมต้องตรวจสอบ License เอง
-->

---

# เรื่องของ "ความรู้สึก"

## Nuance & Vibe: Developer Experience (DX)

<div grid="~ cols-2 gap-8" mt-4>

<div>

### 🤖 สิ่งที่ AI ไม่เข้าใจ

**"ความรู้สึกตอนใช้งาน"** (Friction)

<v-click>

ตัวอย่าง:

- AI บอกว่า TensorZero ติดตั้งง่ายเพราะมี Docker
- แต่ความจริง = Config File เขียนยากมาก
- ต้องเข้าใจ Concept Graph theory

</v-click>

</div>

<div>

### 👨‍💻 Human Insight

<v-clicks>

**คนเท่านั้นที่รู้:**

"Easy to install" ≠ "Easy to use"

<v-click>

### 📊 Metrics ที่ AI วัดไม่ได้

- Time to first "Hello World"
- Number of config files
- Cognitive load ตอน setup
- "Gotcha" moments ที่ซ่อนอยู่

</v-click>

</v-clicks>

</div>

</div>

<!--
อธิบายว่าทำไมความรู้สึกตอนใช้งานสำคัญ - สิ่งที่ AIไม่เข้าใจ
-->

---

# Part 5: Research Tips & Prompt

_บทเรียน: เคล็ดลับเพื่อการวิจัยที่ดีกว่าเดิม_

---

# Prompt ที่ทรงพลัง

## Effective Prompt: Context Setting

<div class="p-6 bg-gradient-to-r from-blue-50 to-purple-50 rounded-lg border-2 border-blue-200">

### 🎯 เทคนิค: การกำหนดบริบทเวลาในอนาคต

```markdown
กำหนดให้ **วันที่ปัจจุบันคือ: 22 กุมภาพันธ์ 2026**

ให้วิเคราะห์ในฐานะ Principal Product Strategist
โดยให้ความสำคัญกับข้อมูลย้อนหลังไม่เกิน 6 เดือน...
```

</div>

<v-clicks>

### ✨ Why it works?

1. **ลด Legacy Info**
    - บังคับไม่ให้ดึงข้อมูลเก่ามาตอบ
    - บังคับมองหา Trend ล่าสุด

2. **Role Clarity**
    - กำหนดบทบาทที่ชัดเจน
    - "Principal Product Strategist" vs "Generic AI"

3. **Time Awareness**
    - การหลอกให้ AI คิดว่าอยู่ในอนาคต
    - ช่วยกรองข้อมูลที่ล้าสมัย

</v-clicks>

<!--
สอนเทคนิคการเขียน Prompt ที่ดี
-->

---

# เคล็ดลับการวิจัย

## "GitHub สำคัญกว่า Google"

<div grid="~ cols-2 gap-8" mt-4">

<div>

### ❌ ปัญหาของ Google

<v-clicks>

ในโลก Developer Tools:

- ข้อมูลใน Google = SEO ขยะ
- Tutorial เก่า
- Blog post ที่ไม่อัปเดต

<span class="text-red-500">→ Misleading Information!</span>

</v-clicks>

</div>

<div>

### ✅ GitHub คือแหล่งความจริง

<v-clicks>

| ที่               | บอกอะไร?                             |
| ----------------- | ------------------------------------ |
| **README**        | สิ่งที่ผู้สร้าง _เคลม_               |
| **Releases/Tags** | สิ่งที่ _มีอยู่จริง_ + ความถี่อัปเดต |
| **Issues**        | _จุดตาย_ ที่หน้าเว็บไม่บอก           |
| **Pull Requests** | _อนาคต_ ฟีเจอร์อะไรกำลังจะมา         |

</v-clicks>

</div>

</div>

<v-click="3">

<div class="mt-6 p-4 bg-yellow-50 border-l-4 border-yellow-500">

### 💡 Pro Tip

สังเกต **Issue Response Time**

- ถ้า Issue ทิ้งไว้เดือนๆ → Project ตายแล้ว
- ถ้ามี PR รอ merge เยอะ → Maintainer ไม่ active

</div>

</v-click>

<!--
เคล็ดลับว่าทำไม GitHub สำคัญกว่า Google สำหรับ Dev Tools
-->

---

# สิ่งที่ต้องปรับปรุง

## Next Time Improvement

<div grid="~ cols-2 gap-8" mt-4">

<div>

### 🚨 Problem

<v-clicks>

AI ชอบอนุมานว่า:

- เครื่องมือยอดฮิตในอดีต (เช่น Python proxies)
- ยังคงเป็นมาตรฐาน

→ ทำให้เราอาจหลงไปแข่งกับเทคโนโลยีที่กำลังจะตกรุ่น

</v-clicks>

</div>

<div>

### ✅ Solution

<v-clicks>

**ในการวิจัยครั้งหน้า ต้องสั่งให้ AI:**

1. ระบุเลยว่าข้อมูลชุดไหนเก่ากว่า 6 เดือน
    - ติดป้าย **[Possibly Outdated]**

2. ให้คะแนนน้ำหนัก:
    - โปรเจกต์ที่มี Activity ในรอบ 30 วัน
    - มีน้ำหนัก > โปรเจกต์ตาย

3. Impact:
    - ไม่หลงทางไปแข่งกับคู่แข่งที่กำลังจะตาย
    - ไม่ใช้เทคโนโลยีที่กำลังจะตกรุ่น

</v-clicks>

</div>

</div>

<!--
บทสรุป - สิ่งที่จะปรับปรุงในการวิจัยครั้งหน้า
-->

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

<!--
สไลด์ปิดท้าย
-->
