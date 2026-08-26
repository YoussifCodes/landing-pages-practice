# Design System: AuraMen (Tokens & Foundations)

## 1. Color Tokens (Design Tokens)

### Brand & Primitive Colors

* **Neutral - Dark:** `neutral-900` `#111111` | `neutral-800` `#1F2937`
* **Neutral - Mid:** `neutral-500` `#6B7280` | `neutral-300` `#D1D5DB`
* **Neutral - Light:** `neutral-100` `#F3F4F6` | `neutral-0` `#FFFFFF`
* **Accent - Sand:** `sand-500` `#C5BCAD` | `sand-100` `#E5E0D8` | `sand-50` `#F9F8F6`
* **Status - Success:** `green-600` `#059669` | `green-50` `#ECFDF5`
* **Status - Error:** `red-600` `#DC2626` | `red-50` `#FEF2F2`
* **Status - Warning:** `amber-500` `#F59E0B` | `amber-50` `#FFFBEB`

### Semantic Surface Tokens

* **`color-bg-primary`:** `neutral-0` (`#FFFFFF`) - الخلفية الرئيسية للصفحات والكروت.
* **`color-bg-secondary`:** `sand-50` (`#F9F8F6`) - خلفية كروت الأطقم والـ Lookbook.
* **`color-bg-tertiary`:** `neutral-100` (`#F3F4F6`) - خلفية عناصر الإدخال والـ Badges.
* **`color-bg-inverse`:** `neutral-900` (`#111111`) - خلفية الأزرار الرئيسية والهيدر.

### Semantic Text Tokens

* **`color-text-primary`:** `neutral-900` (`#111111`) - عناوين ونصوص أساسية.
* **`color-text-secondary`:** `neutral-500` (`#6B7280`) - النصوص الفرعية والأوصاف.
* **`color-text-inverse`:** `neutral-0` (`#FFFFFF`) - نصوص الأزرار الداكنة.
* **`color-text-accent`:** `sand-500` (`#C5BCAD`) - نصوص التمييز والوسوم الخاصة.

### Semantic Interactive Tokens

* **`color-border-default`:** `neutral-300` (`#D1D5DB`) - حدود العناصر والحقول.
* **`color-border-subtle`:** `neutral-100` (`#F3F4F6`) - الفواصل الخفيفة.
* **`color-interactive-primary`:** `neutral-900` (`#111111`) - الأزرار الرئيسية.
* **`color-interactive-hover`:** `neutral-800` (`#1F2937`) - حالة التمرير للأزرار.

---

## 2. Typography System

### Font Family

* **Arabic Primary:** `Tajawal`, `sans-serif`
* **English / Monospace:** `Inter`, `sans-serif` (للأرقام والأسعار والـ SKU)

### Type Scale Hierarchy

* **Display / Hero:** Size: `36px` | Line Height: `44px` | Weight: `700 (Bold)` | Usage: البانر الرئيسي.
* **Heading 1 (H1):** Size: `28px` | Line Height: `36px` | Weight: `700 (Bold)` | Usage: عناوين الصفحات الرئيسية.
* **Heading 2 (H2):** Size: `22px` | Line Height: `28px` | Weight: `600 (SemiBold)` | Usage: عناوين الأقسام والكروت.
* **Heading 3 (H3):** Size: `18px` | Line Height: `24px` | Weight: `600 (SemiBold)` | Usage: أسماء المنتجات والعناوين الفرعية.
* **Body Large:** Size: `16px` | Line Height: `24px` | Weight: `400 (Regular) / 500 (Medium)` | Usage: نصوص القوائم والمواصفات.
* **Body Regular:** Size: `14px` | Line Height: `20px` | Weight: `400 (Regular)` | Usage: النصوص العامة والأوصاف.
* **Caption / Small:** Size: `12px` | Line Height: `16px` | Weight: `500 (Medium)` | Usage: الملاحظات، الفلاتر، وتتبع الشحنات.

---

## 3. Spacing System (8pt Grid System)

* **`space-1` (4px):** المسافات الدقيقة جداً (بين الأيقونة والنص).
* **`space-2` (8px):** الحشوات الداخلية للعناصر الصغيرة (Badges, Chips).
* **`space-3` (12px):** المسافات بين العناصر المترابطة داخل الكرت.
* **`space-4` (16px):** الحشوة الداخلية القياسية للأزرار والحقول (Padding).
* **`space-6` (24px):** الهوامش بين الكروت داخل الشبكة (Grid Gap).
* **`space-8` (32px):** المسافات بين الأقسام الفرعية.
* **`space-12` (48px):** المسافات الكبيرة بين أقسام الصفحة الرئيسية.
* **`space-16` (64px):** هوامش أعلى وأسفل الصفحة (Section Padding).

---

## 4. Radius Tokens (Border Radius)

* **`radius-none` (0px):** للتصاميم الحادة جداً والبنرات العريضة.
* **`radius-sm` (4px):** الأزرار الصغيرة، حقول الإدخال، وخانات الفلاتر.
* **`radius-md` (8px):** كروت المنتجات، أزواج الملابس (Lookbook Cards)، والسلة الجانبية.
* **`radius-lg` (16px):** النوافذ المنبثقة (Modals) ودليل المقاسات الذكي.
* **`radius-full` (9999px):** أزرار اختيار الألوان (Color Swatches) ووسوم الحالة (Pills).

---

## 5. Shadow & Elevation Tokens

* **`shadow-none`:** مسطح بدون ظلال (استخدام افتراضي للكروت لتصميم نقي).
* **`shadow-sm`:** `0px 1px 2px rgba(0, 0, 0, 0.05)` - حالة Hover على كروت المنتجات.
* **`shadow-md`:** `0px 4px 6px -1px rgba(0, 0, 0, 0.1)` - للقوائم المنسدلة والسلة الجانبية (Cart Drawer).
* **`shadow-lg`:** `0px 10px 15px -3px rgba(0, 0, 0, 0.1)` - للنوافذ المنبثقة (Modals) أداة قياس المقاس الذكي.

---

## 6. Component Specs & Interaction Tokens

### Buttons (الأزرار)

* **Primary Button:**
  * Background: `color-interactive-primary` | Text: `color-text-inverse` | Radius: `radius-sm` | Height: `48px`
  * Hover: `color-interactive-hover`
* **Secondary / Outline Button:**
  * Background: `transparent` | Border: `1px solid color-border-default` | Text: `color-text-primary` | Height: `48px`
* **Bundle Action Button (One-Click Buy):**
  * Background: `sand-100` | Text: `neutral-900` | Border: `1px solid sand-500`

### Input Fields & Controls

* **Default Input:** Height: `44px` | Border: `color-border-default` | Radius: `radius-sm` | Padding: `space-4`
* **Focus State:** Border: `color-interactive-primary` (2px) | Background: `color-bg-primary`
* **Error State:** Border: `red-600` | Text: `red-600`
