🛡️ وحدة أمان متكاملة - نظام المصادقة وإدارة كلمات المرور
مشروع أمان متكامل يقدم حلولاً لتوليد كلمات مرور قوية، التحقق من التسريبات، وتفعيل المصادقة الثنائية (2FA) مع واجهة تفاعلية عبر Swagger.

📋 جدول المحتويات
التقنيات المستخدمة

🚀 تشغيل المشروع

📘 Swagger UI

⚙️ الوظائف الرئيسية

توليد كلمة مرور

توليد Passphrase

التحقق من تسريب كلمة المرور

توليد 2FA + QR Code

عرض QR Code مباشرة

📱 نظام المصادقة الثنائية (2FA)

🧪 اختبار النظام عبر Swagger

🏁 خاتمة

التقنيات المستخدمة
تم استخدام الأدوات التالية:

text
Python
FastAPI
Uvicorn
مكتبة pyotp (لـ 2FA)
مكتبة qrcode (لتوليد QR Code)
مكتبة requests (لـ API الخارجي)
re
secrets
string
hashlib
requests
pyotp
qrcode
io
base64
Response
FastAPI
BaseModel
🚀 تشغيل المشروع
لتشغيل المشروع:

bash
uvicorn security_module:app --reload
ثم فتح:

👉 Swagger UI:

text
http://127.0.0.1:8000/docs
https://./images/1.jpg

📘 Swagger UI
يوفر Swagger واجهة تفاعلية لاختبار API بسهولة.

من خلال:
Swagger UI

يمكنك:

تجربة جميع الـ endpoints

إدخال البيانات مباشرة

مشاهدة النتائج فوراً

https://./images/2.jpg

⚙️ الوظائف الرئيسية
🔹 5.2 توليد كلمة مرور
GET /generate-password

📌 مثال:

text
/generate-password?length=12
✔️ يولد كلمة مرور تحتوي على:

حروف كبيرة وصغيرة

أرقام

رموز

https://./images/3.jpg

🔹 5.3 توليد Passphrase
GET /generate-passphrase

📌 يعتمد على ملف: wordlist.txt

✔️ مثال:

text
"click shield voice iron network process safe"
https://./images/4.jpg

🔹 5.4 التحقق من تسريب كلمة المرور
POST /check-breach

✔️ يستخدم API من موقع: Have I Been Pwned

✔️ يتحقق هل كلمة المرور تم تسريبها سابقاً

https://./images/5.jpg

🔹 5.5 توليد 2FA + QR Code
GET /generate-2fa

📤 يعطي:

secret

current_code

QR Code (Base64)

URI

https://./images/6.jpg

🔹 5.6 عرض QR Code مباشرة
GET /qr-image

✔️ يعرض QR Code كصورة مباشرة

https://./images/7.jpg

📱 نظام المصادقة الثنائية (2FA)
تم تطبيق نظام 2FA باستخدام:

Time-based One-Time Password (TOTP)

🔸 طريقة العمل:

يتم إنشاء secret

يتم توليد QR Code

المستخدم يمسح QR باستخدام تطبيق مثل:

Google Authenticator

يظهر كود مكون من 6 أرقام

الكود يتغير كل 30 ثانية

https://./images/6.jpg

🧪 اختبار النظام عبر Swagger
يمكن اختبار جميع الوظائف عبر:

text
http://127.0.0.1:8000/docs
مثال:

اضغط على endpoint

اضغط "Try it out"

أدخل البيانات

اضغط Execute

✔️ تظهر النتيجة مباشرة

https://./images/2.jpg

🏁 خاتمة
يوفر هذا المشروع نظاماً متكاملاً لتحسين أمان كلمات المرور باستخدام أحدث التقنيات، كما يتيح اختبار جميع الوظائف بسهولة عبر Swagger.

https://./images/7.jpg

📁 هيكل المجلدات المقترح
text
مشروعك/
│
├── security_module.py
├── wordlist.txt
├── README.md
│
└── images/
    ├── 1.jpg
    ├── 2.jpg
    ├── 3.jpg
    ├── 4.jpg
    ├── 5.jpg
    ├── 6.jpg
    └── 7.jpg
✅ ملاحظات
جميع الصور بصيغة JPG وتوجد في مجلد images

المسارات تستخدم ./images/ للإشارة إلى المجلد المحلي

تأكد من وجود مجلد images بنفس مستوى ملف README.md

هل تريد تعديل أي شيء آخر؟

This response is AI-generated, for reference only.
