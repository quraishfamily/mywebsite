# ملخص مشروع موقع أحمد قريش — quraishvoice.me

---

## المعلومات الأساسية

| البند | القيمة |
|-------|--------|
| الدومين | https://quraishvoice.me |
| GitHub | https://github.com/quraishfamily/mywebsite |
| Firebase Project | ahmed-quraish |
| Firestore Region | me-central2 (الدمام) |
| Cloudinary | cloud=dhnzsilai / preset=ahmed_site_unsigned |
| EmailJS Service | service_6g3odwb |
| EmailJS Public Key | QnIPBoSRBkpNWiNt4 |
| EmailJS Template (رسائل) | bozx1s3 |
| EmailJS Template (تسجيل دورة) | t2l4rkn |
| WhatsApp | +966565909049 |

---

## Firebase Config

```javascript
var firebaseConfig = {
  apiKey: "AIzaSyBCheHz_5vWYWJdnTpaYstOVKUgvR5tCPQ",
  authDomain: "ahmed-quraish.firebaseapp.com",
  projectId: "ahmed-quraish",
  storageBucket: "ahmed-quraish.firebasestorage.app",
  messagingSenderId: "777596990140",
  appId: "1:777596990140:web:8f336a1f2336a450a416b9"
};
```

---

## الملفات

| الملف | الوصف |
|-------|-------|
| `index.html` | الموقع الرئيسي |
| `admin.html` | لوحة الإدارة |
| `news.html` | صفحة الخبر المستقل |
| `course.html` | صفحة تفاصيل الدورة |
| `consulting.html` | طلب استشارة (صفحة مستقلة) |
| `events-request.html` | طلب تقديم حفل (صفحة مستقلة) |
| `voiceover-request.html` | طلب تسعيرة تعليق صوتي (صفحة مستقلة) |
| `contact.html` | صفحة تواصل مستقلة |
| `events-landing.html` | صفحة هبوط لمقدم الفعاليات (للإرسال للعملاء) |
| `404.html` | صفحة الخطأ |
| `sitemap.xml` | خريطة الموقع |
| `robots.txt` | ملف الروبوتات |
| `og-image.jpg` | صورة المشاركة على السوشيال |

---

## أقسام index.html

| القسم | ID | الوصف |
|-------|-----|-------|
| Hero | home | الصفحة الرئيسية مع الاسم والمسمى والصورة |
| نبذة | about | معلومات شخصية من Firebase settings/main |
| كتبي | books | كتابان مع روابط شراء من settings/books |
| بودكاست صباحو | podcast | RSS من libsyn عبر rss2json API |
| الأخبار | news | آخر 6 أخبار + أرشيف قابل للفتح |
| مقابلات | interviews | من Firestore collection interviews |
| الأعمال | works | slider من Firestore collection works |
| الدورات | courses | من Firestore collection courses + زر التفاصيل |
| شهادات المتدربين | testimonials | مخفي حتى يُضاف محتوى |

**أقسام أُزيلت من index وأصبحت صفحات مستقلة:**
- الاستشارات → consulting.html
- تقديم حفل → events-request.html
- تعليق صوتي → voiceover-request.html
- تواصل → contact.html

---

## Firestore Collections

| Collection | الاستخدام |
|-----------|----------|
| `news` | الأخبار (status: published/draft/scheduled, scheduledAt, img, img2, img3) |
| `courses` | الدورات (title, desc, price, dur, sess, lvl, badge, img, icon, outline, outcomes, reglink) |
| `works` | الأعمال الصوتية والمرئية |
| `interviews` | المقابلات (title, channel, vid) |
| `testimonials` | شهادات المتدربين |
| `registrations` | تسجيلات الدورات |
| `voiceover_requests` | طلبات التعليق الصوتي (quote_price, quote_time, rejected, rejection_time) |
| `event_requests` | طلبات تقديم الحفل (name, phone, email, title, audience, hours, date, location, notes, quote_price, quote_time) |
| `consulting` | طلبات الاستشارة (field, level, goal) |
| `messages` | رسائل التواصل |
| `newsletter` | المشتركين في النشرة البريدية (email, active, time) |
| `newsletter_history` | سجل إرسال النشرة |
| `settings/main` | المعلومات الشخصية |
| `settings/socials` | روابط السوشيال (tw, ig, yt, sn, tiktok, linkedin) |
| `settings/books` | روابط شراء الكتابين |
| `settings/popup` | إعدادات الإعلان المنبثق (active, title, desc, badge, link, img, icon, delay) |

---

## لوحة الأدمن — التبويبات

| التبويب | ID | الوظيفة |
|---------|-----|---------|
| لوحة التحكم | dashboard | إحصائيات عامة |
| الأخبار | news | إضافة/تعديل/حذف + draft/scheduled + رفع صور |
| الدورات | courses | إضافة/تعديل/حذف + المحاور + ما ستتعلمه + رابط تسجيل |
| حلقات صباحو | podcast | إدارة حلقات البودكاست |
| المقابلات | interviews | إضافة/حذف مقابلات يوتيوب |
| الأعمال الصوتية | works | إضافة/حذف الأعمال |
| طلبات التعليق الصوتي | voiceover | عرض + PDF + تسعيرة + رفض + حذف |
| طلبات تقديم الحفل | events | عرض + PDF + تسعيرة + حذف |
| التسجيلات | regs | تسجيلات الدورات |
| طلبات الاستشارة | consulting | عرض + حذف |
| الرسائل | messages | رسائل التواصل |
| التعليقات | comments | تعليقات الأخبار |
| شهادات المتدربين | testimonials | إضافة/حذف |
| النشرة البريدية | newsletter | قائمة المشتركين + إرسال + تصدير CSV |
| الإعلان المنبثق | popup | إدارة popup الموقع |
| الإعدادات | settings | المعلومات الشخصية + السوشيال + الكتب + كلمة المرور |

---

## مميزات الموقع الرئيسي

- شريط أخبار متحرك علوي (fixed) يعرض الأخبار والدورات
- زر واتساب عائم
- زر العودة للأعلى
- Dark/Light mode
- Hamburger menu للجوال
- Loading screen بالشعار
- شاشة 404 مع عداد تنازلي
- نافذة إعلانية منبثقة (popup) تُدار من الأدمن، تظهر مرة واحدة لكل زيارة
- SEO كامل (meta, og, twitter card, schema.org, sitemap)
- شعار SVG للسوشيال (X, Instagram, YouTube, Snapchat)
- صفحة الأخبار: 6 أحدث + أرشيف + زر "أخبار سابقة"
- الأخبار: منشور / مسودة / مجدول
- صفحة تفاصيل الدورة (course.html): محاور + ما ستتعلمه + نموذج تسجيل

---

## مميزات لوحة الأدمن

- Firebase Authentication (بريد + كلمة مرور)
- Badge إشعارات على التبويبات
- رفع صور عبر Cloudinary
- تصدير PDF لطلبات التعليق الصوتي (HTML print window — يدعم العربية)
- تصدير PDF لطلبات تقديم الحفل (HTML print window — يدعم العربية)
- تصدير PDF لكل الطلبات (جدول)
- إرسال تسعيرة للعميل (تعليق صوتي / تقديم حفل)
- تحميل PDF للتسعيرة (HTML print — يدعم العربية)
- رفض طلب التعليق الصوتي مع رسائل جاهزة
- تصدير قائمة المشتركين CSV
- إرسال نشرة بريدية

---

## قواعد تقنية مهمة للتطوير

1. **لا `type="module"`** في script tags
2. **جميع الدوال global** — لا ES modules
3. **نظام proxy في `<head>`** يستخدم `_wcall()` لاستدعاء الدوال قبل تحميل الكود الرئيسي
4. **window exports** — كل دالة تُستخدم في onclick يجب تسجيلها: `window._real_functionName = functionName`
5. **Firebase API: compat style** — `db.collection().doc().set/get/delete`
6. **تجنب multiline strings** داخل single quotes — استخدم `array.join('\n')`
7. **تجنب template literals معقدة** — استخدم DOM API أو string concatenation
8. **تجنب `</html>` أو `</body>`** داخل template literals — استخدم `<\/html>`
9. **الصفحة الرئيسية** تستخدم `var` وليس `const/let` للمتغيرات الأساسية (db, auth, app)
10. **Cloudinary upload** — يستخدم fetch مباشرة بدون SDK

---

## صفحة الهبوط (events-landing.html)

صفحة مستقلة ترسل للعملاء الباحثين عن مقدم فعاليات:
- رابطها: `https://quraishvoice.me/events-landing.html`
- تصميم احترافي داكن مع تأثيرات بصرية
- نموذج حجز يرسل بريد إلكتروني مباشرة
- لا تحتاج Firebase
