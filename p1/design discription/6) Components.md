# نظام التصميم (Design System) — AuraClinic Platform

---

## 1. الأساسيات (Design Tokens)

### أ. الألوان (Color Palette)

| الفئة | اسم اللون | القيمة (HEX) | Tailwind Class | الاستخدام |
| :--- | :--- | :--- | :--- | :--- |
| **Primary** | Navy Blue | `#1E3A8A` | `bg-blue-900` / `text-blue-900` | الهيدر، العناوين الرئيسية، العناصر المؤسسية |
| **Secondary** | Medical Cyan | `#0EA5E9` | `bg-sky-500` / `text-sky-500` | الأيقونات، العناصر التوضيحية، النقاط البارزة |
| **Accent / CTA** | Action Blue | `#2563EB` | `bg-blue-600` / `hover:bg-blue-700` | أزرار اتخاذ الإجراء الرئيسية والحجز |
| **Success** | Emerald Green| `#059669` | `bg-emerald-600` | أزرار الواتساب، مؤشرات التوفر، النجاح |
| **Neutral Dark**| Slate Gray | `#1E293B` | `text-slate-800` | النصوص الرئيسية |
| **Neutral Muted**| Muted Slate | `#64748B` | `text-slate-500` | النصوص الفرعية، التلميحات |
| **Neutral Light**| Ice White / Light Gray | `#F8FAFC` | `bg-slate-50` | خلفية البطاقات والأقسام الثانوية |
| **Background** | Pure White | `#FFFFFF` | `bg-white` | خلفية الصفحة الرئيسية |

---

### ب. الطبوغرافيا (Typography)

* **الخط الأساسي (Arabic & Latin):** `IBM Plex Sans Arabic`, `sans-serif`

| العنصر | الوزن (Weight) | الحجم (Desktop) | الحجم (Mobile) | Tailwind Class |
| :--- | :--- | :--- | :--- | :--- |
| **H1 (Hero Heading)** | Bold (700) | 48px | 32px | `text-3xl md:text-5xl font-bold` |
| **H2 (Section Title)**| Bold (700) | 36px | 24px | `text-2xl md:text-4xl font-bold` |
| **H3 (Card Title)** | Semi-Bold (600) | 20px | 18px | `text-lg md:text-xl font-semibold` |
| **Body Large** | Regular (400) | 18px | 16px | `text-base md:text-lg` |
| **Body Normal** | Regular (400) | 16px | 14px | `text-sm md:text-base` |
| **Caption / Small** | Light (300) | 14px | 12px | `text-xs md:text-sm` |

---

### ج. المسافات والزوايا (Spacing & Radius)

* **النظام الشبكي للمسافات:** يعتمد على مضاعفات الرقم 4 (`4px`, `8px`, `16px`, `24px`, `32px`, `48px`, `64px`).
* **انحناء الزوايا (Border Radius):**
  * `rounded-md` (`6px`) — للمدخلات (Inputs).
  * `rounded-lg` (`8px`) — للأزرار والبطاقات الصغيرة.
  * `rounded-xl` (`12px`) — للبطاقات الرئيسية والنوافذ المنبثقة.
* **الظلال (Shadows):**
  * `shadow-sm` — للبطاقات العادية عند التوقف.
  * `shadow-md` / `shadow-lg` — للبطاقات عند التفاعل (Hover) والشريط العائم.

---

## 2. عناصر الواجهة الأساسية (UI Components)

### أ. الأزرار (Buttons)

* **الزر الرئيسي (Primary Button):**
  * Structure: خلفية `Action Blue` + نص أبيض + زوايا `rounded-lg` + مساحة داخلية `px-6 py-3`.
  * States: `Hover: bg-blue-700`, `Active: scale-95`, `Disabled: opacity-50 cursor-not-allowed`.
* **الزر الثانوي (Secondary / Outline Button):**
  * Structure: حد خارجي `border border-blue-900` + نص `text-blue-900` + خلفية شفافة.
  * States: `Hover: bg-blue-50`.
* **زر الواتساب / الاتصال المباشر (Floating/Action Button):**
  * Structure: خلفية `Emerald Green` + نص أبيض + أيقونة الواتساب.

---

### ب. بطاقات المحتوى (Cards)

* **بطاقة الخدمة (Service Card):**
  * خلفية بيضاء + حد خفيف `border border-slate-100` + shadow خفيف + مساحة داخلية `p-6` + زوايا `rounded-xl`.
  * تأثير `Hover`: ارتفاع خفيف `hover:-translate-y-1` وزيادة الشفافية للظل `hover:shadow-md`.
* **بطاقة الطبيب (Doctor Card):**
  * جزء علوي مخصص لصحيفة الصورة بحواف منتظمة + محاذاة للنص في المنتصف + شارة (Badge) التخصص.

---

### ج. حقول الإدخال والفيوردات (Form Controls)

* **حقل النص (Input Field):**
  * Structure: خلفية بيضاء + حد `border border-slate-300` + زوايا `rounded-md` + `py-2.5 px-4`.
  * States: `Focus: border-blue-600 ring-2 ring-blue-100 outline-none`.
* **القائمة المنسدلة (Select Box):**
  * نفس تنسيق حقل النص مع سهم توضيحي جانبي لتحديد الخدمات/الأطباء.

---

## 3. قواعد التفاعل والوصولية (Micro-interactions & Accessibility)

* **زمن الانتقال (Transitions):** استخدام `transition-all duration-200 ease-in-out` لجميع حالات الانتقال لتأمين تجربة سلسة.
* **الوصولية (WCAG 2.1):**
  * ضمان التباين بين لون النص الخلفية لا يقل عن `4.5:1`.
  * دعم التنقل بكرت الشاشة والتركيز (Keyboard Focus Indicators) عبر `focus-visible:ring-2`.