# تقرير عن تأمين كلمات المرور

## مقدمة

تأمين كلمات المرور هو من أهم الخطوات لحماية حسابات وبيانات المستخدمين. مع انتشار محاولات الاختراق أصبح تخزين كلمات المرور بشكل آمن ضرورة أساسية لكل التطبيقات والخدمات اللي تعتمد على تسجيل الدخول. هذا التقرير يقدم شرحاً بسيطاً عن الطرق لتأمين كلمات المرور، مع التركيز على ثلاث نقاط رئيسية:
1. تجنب تخزين كلمات المرور كنصوص عادية واستخدم التجزئة (Hashing)
2. استخدام "الملح" (Salt) لتقوية التجزئة وزيادة الأمان.
3. طريقة التحقق من كلمة المرور عند تسجيل الدخول بشكل آمن.

## 1. لا تخزن كلمة المرور كنص عادي (Plain Text)

من المهم جداً تجنب تخزين كلمات المرور كما هي، بشكل نص عادي وواضح في قاعدة البيانات، لأن في حال حدوث اختراق، يمكن للمخترقين قراءة كلمات المرور بسهولة. الحل هو استخدام تقنية اسمها **التجزئة** (Hashing)، اللي تحول كلمة المرور إلى رمز مشفر غير قابل للاسترجاع إلى النص الأصلي، وبهالطريقة تخزينها يكون أكثر أمان.

**الصورة أدناه توضح عملية تحويل كلمة المرور إلى صيغة غير قابلة للقراءة باستخدام التجزئة(Hashing)**:

![التجزئة](https://i.ibb.co/VjW7DrR/1.png)

## 2. استخدام "Salt" لزيادة الأمان

التجزئة لوحدها قد تكون غير كافية لحماية كلمات المرور، خصوصاً إذا كانت كلمات المرور متشابهة بين المستخدمين. لحل هذي المشكلة، نضيف شيء مهم اسمه **"الملح" (Salt)**، وهو قيمة عشوائية تنضاف لكل كلمة مرور قبل التجزئة. هذي القيمة تضمن أن حتى لو كانت كلمات المرور متطابقة، تطلع التجزئات مختلفة، وهذا يزيد الأمان ويصعب على المخترقين محاولة فك التشفير.

### مثال على استخدام Salt

لو كانت كلمة المرور "secret123" ومع إضافة الملح، راح يطلع لنا رمز تجزئة فريد لكل مستخدم، حتى لو كان مستخدم آخر عنده نفس كلمة المرور.

**الصورة أدناه توضح كيف يتم إضافة الملح لكلمة المرور قبل التجزئة لضمان تجزئة فريدة لكل مستخدم**:

![Salt](https://i.ibb.co/M1pfQRL/2.png)

## 3. كيفية التحقق عند تسجيل الدخول

بدل ما نخزن كلمات المرور كنصوص عادية، النظام يعتمد على التجزئة في التحقق من كلمة المرور عند تسجيل الدخول. لما يدخل المستخدم كلمة المرور، النظام يحسب التجزئة باستخدام نفس الطريقة مع الملح المخزن، ويقارنها بالتجزئة الموجودة في قاعدة البيانات. إذا كانت النتيجتان متطابقتين، يدخل المستخدم للنظام.

**الصورة أدناه توضح عملية التحقق من كلمة المرور عند تسجيل الدخول**:


[التحقق](https://i.ibb.co/z6r6VZj/image.png)


بهذا الشكل، يوفر التقرير نظرة شاملة عن أفضل الطرق لتأمين كلمات المرور، وركزنا على تجنب تخزينها كنص عادي، واستخدام الملح لتعزيز الأمان، واتباع آلية آمنة للتحقق عند تسجيل الدخول.
