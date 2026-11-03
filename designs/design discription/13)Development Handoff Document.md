# وثيقة التسليم البرمجي (Development Handoff Document): منصة AuraMen

---

## 1. المعمارية التقنية والبنية التحتية (Architecture & Tech Stack)

* **إطار العمل الأساسي (Frontend Framework):** Next.js (App Router) مع React و TypeScript.
* **إدارة حالات الواجهة (State Management):**
  * **Global State (Zustand):** إدارة حالة السلة الجانبية (`Cart Drawer`)، قائمة المفضلات (`Wishlist`)، وتفضيلات المقاس الذكي.
  * **Server State (TanStack Query / React Query):** كاش البيانات وتحديثها التلقائي لقائمة المنتجات والصفحة الرئيسية.
  * **Form State (React Hook Form + Zod):** إدارة التحقق من صحة مدخلات الدفع والفلترة وشاشة المقاس الذكي.
* **التنسيق واستراتيجية النمط (Styling System):** Tailwind CSS مع إعداد المتغيرات (`CSS Variables`) للعلامة التجارية.
* **دعم الاتجاهات (RTL/LTR Support):** الاعتماد الكلي على خصائص Tailwind المنطقية (`ms-*`, `me-*`, `ps-*`, `pe-*`, `start-*`, `end-*`) لضمان محاذاة لغة RTL الصحيحة.

---

## 2. نظام التنسيق وقيم التصميم (Design Tokens Mapping)

### الألوان (Colors Variables)

```css
:root {
  /* Brand Colors */
  --color-primary: #111111;         /* neutral-900 (Main CTA, Primary Text) */
  --color-primary-hover: #262626;   /* neutral-800 */
  --color-secondary: #F9F8F6;       /* sand-50 (Editorial Cards & Lookbook Background) */
  --color-accent: #C5A059;          /* gold-500 (Highlights, Badges, Savings Indicator) */
  
  /* Neutral Colors */
  --color-bg-main: #FFFFFF;         /* Main Background */
  --color-border: #E5E5E5;          /* neutral-200 (Borders & Dividers) */
  --color-text-muted: #737373;      /* neutral-500 (Subtitles, SKU, Secondary Text) */
  
  /* Feedback States */
  --color-error: #DC2626;           /* red-600 */
  --color-error-bg: #FEF2F2;        /* red-50 */
  --color-success: #16A34A;         /* green-600 */
  --color-success-bg: #F0FDF4;      /* green-50 */
  --color-warning: #D97706;         /* amber-600 (Low Stock Alert) */
}
المسافات وأنصاف الأقطار (Spacing & Radius Tokens)
نظام المسافات (Spacing Grid): الاعتماد على وحدة base بمقدار 4px (p-1 = 4px, p-2 = 8px, p-4 = 16px, p-6 = 24px, p-8 = 32px, p-16 = 64px).

أنصاف الأقطار (Border Radius):

rounded-sm: 4px (Inputs, Buttons, Badges).

rounded-md: 8px (Product Cards, Lookbook Items, Cart Drawer).

rounded-lg: 16px (Modals, Smart Size Dialog).

الخطوط (Typography Mapping)
اللغة العربية: Tajawal (Weights: 400 Regular, 500 Medium, 700 Bold).

الأرقام والرموز والإنجليزية: Inter (Weights: 400 Regular, 500 Medium, 600 Semi-bold, 700 Bold).

3. مواصفات المكونات وحالاتها البرمجية (Component Specs & States)
1. كرت المنتج (Product Card - ProductCard.tsx)
المسارات والبيانات (Props):

id (string), title (string), price (number), originalPrice (number | optional), images (array of strings), sizes (array of strings), isBundleEligible (boolean).

سلوك الحالات التفاعلية:

Default State: عرض الصورة الرئيسية (images[0])، العنوان، السعر بالريال السعودي.

Hover State (Desktop): انزلاق/تبديل تدريجي للصور إلى (images[1]) خلال 200ms ease-in-out مع إظهار شريط اختيار المقاسات السريع أسفل الكرت.

Quick Add Interaction: عند انقر مقاس معين، يتم استدعاء API مباشرة بـ POST /api/cart وتتحول خانة المقاس المحدد لـ Spinner محلي، تم فتح CartDrawer.

2. السلة الجانبية (Cart Drawer - CartDrawer.tsx)
المحفزات والحسابات (Logic & Calculations):

Free Shipping Threshold: حساب القيمة الحالية مقابل الحد الثابت (مثال: 300 ريال).

المعادلة: Math.min(100, (subtotal / 300) * 100).

إذا كان الإجمالي ≥ 300: إظهار وسم "تهانينا! لقد حصلت على شحن مجاني".

Outfit Bundle Discount: إذا احتوت السلة على قطعتين أو أكثر تنتميان لنفس bundleId، يتم تطبيق خصم أوتوماتيكي بنسبة 15% على عناصر الحزمة وتوضيح قيمة الخصم بخط أخضر واضح.

3. أداة دليل المقاسات الذكي (Smart Size Finder - SmartSizeModal.tsx)
المنطق والخوارزمية البرمجية (Calculation Logic):

المدخلات: height (cm), weight (kg), fitPreference ('tight' | 'regular' | 'loose').

المخرجات: حجم مقترح تلقائي مع نسبة التوافق.

قواعد المصفوفة الحسابية (Baseline Mapping):

إذا كان BMI < 20 ➔ S (أو M في حال اختيار loose).

إذا كان BMI بين 20 و 25 ➔ M (أو L في حال اختيار loose).

إذا كان BMI بين 25.1 و 29.9 ➔ L (أو XL في حال اختيار loose).

إذا كان BMI > 30 ➔ XL أو XXL.

الإجراء: عند الضغط على "تطبيق المقاس"، يتم تحديث قيمة المقاس المحدد في PDP Context وإغلاق Modal فوراً.

4. مسارات APIs والتحقق من البيانات (API Endpoints & Contracts)
GET /api/products
Query Parameters: category, size, color, sort ('featured' | 'price-asc' | 'price-desc' | 'newest'), page, limit.

Response:

JSON
{
  "data": [
    {
      "id": "prod-101",
      "title": "قميص كلاسيكي أبيض",
      "price": 249,
      "originalPrice": 299,
      "currency": "SAR",
      "images": ["/img/p1-front.jpg", "/img/p1-back.jpg"],
      "sizes": ["S", "M", "L", "XL"],
      "inStock": true,
      "stockCount": 3,
      "bundleId": "look-01"
    }
  ],
  "pagination": { "currentPage": 1, "totalPages": 4, "totalItems": 48 }
}
POST /api/cart/items
Request Body:

JSON
{
  "productId": "prod-101",
  "size": "L",
  "quantity": 1,
  "bundleId": "look-01"
}
Error Handling (400 / 422):

JSON
{
  "code": "OUT_OF_STOCK",
  "message": "المقاس L من هذا المنتج غير متوفر حالياً."
}
5. الأداء وسلوكيات الشاشة (Performance & Accessibility Handoffs)
تحسين الصور (Image Optimization):

استخدام مكون <Image /> في Next.js حصرياً مع تحديد أبعاد sizes المتجاوبة لمنع تحميل أحجام غير مناسبة للجوال.

الصور الرئيسية في البانر الأول تستخدم خاصية priority={true} لتقليل زمن LCP (Largest Contentful Paint).

تحويل كافة الصور لصيغة WebP أو AVIF.

معايير الوصولية (Accessibility - A11y):

جميع العناصر التفاعلية والأزرار التي تحتوي على أيقونات فقط بدون نص يجب أن تمتلك وسم aria-label (مثال: aria-label="إغلاق السلة الجانبية").

النافذة المنبثقة لمحدد المقاسات تحبس التركيز (Focus Trap) بالداخل حتى يتم إغلاقها بمفتاح ESC أو زر الإغلاق.

معالجة التحميل ومنع القفز البصري (CLS Prevention):

يمنع تحميل أي عنصر يتسبب في إزاحة المحتوى البصري (Cumulative Layout Shift > 0.1).

استخدام Skeleton بأبعاد محددة ثابتة لجميع مكونات البطاقات قبل اكتمال وصول بيانات API.
