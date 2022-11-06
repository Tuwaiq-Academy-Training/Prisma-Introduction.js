
محتوى الملف :


- ما هو بريزما(prisma)؟
- لماذا نستخدم البريزما (prisma)
- استخدم حالات
- العمارة النظيفة والطبقات (Clean and layered architecture)


##  ما هو بريزما(prisma)

تحل Prisma محل ORMs التقليدية وتبسط مهام سير عمل قاعدة البيانات:

1 - الوصول: الوصول الآمن إلى قاعدة البيانات من خلال عميل Prisma الذي تم إنشاؤه تلقائيًا (في JavaScript ، TypeScript ، Go)

2 - الترحيل: نمذجة البيانات التصريحية وعمليات الترحيل (اختياري)

3 - الإدارة: إدارة البيانات المرئية باستخدام Prisma Admin

#### يتم استخدامه لبناء واجهات برمجة تطبيقات GraphQL و REST و gRPC وغير ذلك الكثير. يدعم Prisma حاليًا MySQL و PostgreSQL و MongoDB.

ال Prisma مفتوحة المصدر ويمكن استخدامه كمكون مستقل للبنية التحتية مستضاف على مزود السحابة المفضل لديك. Prisma Cloud هو تطبيق (يستخدم من خلال واجهة CLI والويب) يوفر أدوات وخدمات حول Prisma. عند استخدام Prisma ، يكون استخدام Prisma Cloud اختياريًا.

 الهدف من Prisma Cloud هو تسهيل سير العمل في مشاريع Prisma. إنه يتميز بمستعرض البيانات وسجل النشر (قريبًا مع التراجع التلقائي) وخيارات تعاون الفريق المختلفة بالإضافة إلى تكامل مزود السحابة لتسهيل إعداد وصيانة خوادم Prisma الخاصة بهم.
 
 
 ## لماذا نستخدم البريزما (prisma)

#### بسبب سير عمل قاعدة البيانات البسيط

الهدف العام لـ Prisma هو إزالة التعقيد من مهام سير عمل قاعدة البيانات المشتركة وتبسيط الوصول إلى البيانات في تطبيقاتك:
- الوصول الآمن إلى قاعدة البيانات بفضل عميل Prisma المخصص والمُنشأ تلقائيًا.
- واجهة برمجة تطبيقات بسيطة وفعالة للعمل مع البيانات والمعاملات العلائقية.
- إدارة البيانات المرئية باستخدام Prisma Admin.
- يعمل Prisma على توحيد الوصول إلى قواعد بيانات متعددة في وقت واحد (قريبًا) وبالتالي يقلل بشكل كبير من التعقيد في مهام سير العمل عبر قواعد البيانات.
- نظام بث وأحداث في الوقت الفعلي لقاعدة بياناتك يضمن حصولك على تحديثات لجميع الأحداث المهمة التي تحدث في قاعدة البيانات الخاصة بك.
- عمليات الترحيل التلقائية لقاعدة البيانات (اختيارية) استنادًا إلى نموذج بيانات تعريفي يتم التعبير عنه باستخدام لغة تعريف مخطط GraphQL (SDL).
- مهام سير عمل قاعدة البيانات الأخرى مثل استيراد البيانات وتصديرها والمزيد.

## استخدم حالات

#### يعد Prisma مفيدًا في أي سياق تعمل فيه مع قواعد البيانات.

- بناء خوادم GraphQL

ال Prisma هي الأداة المثالية لبناء خوادم GraphQL. عميل Prisma متوافق مع نظام Apollo البيئي ، ولديه دعم افتراضي لاشتراكات GraphQL وتقسيم الصفحات بنمط الترحيل ،ويوفر أمانًا شاملًا ويأتي مزودًا بمحمل بيانات مدمج لحل مشكلة N + 1.

- بناء واجهات برمجة تطبيقات REST و gRPC

ال Prisma مناسب جدًا لبناء واجهات برمجة تطبيقات REST و gRPC حيث يمكن استخدامها بدلاً من ORMs التقليدية. يوفر العديد من الفوائد مثل أمان النوع وواجهة برمجة تطبيقات حديثة وطرق مرنة لقراءة البيانات العلائقية وكتابتها.

- ال CLIs والنصوص والوظائف بدون خادم وغير ذلك الكثير

يحتوي ال Prisma على واجهة برمجة تطبيقات مرنة للغاية مما يجعله مناسبًا لمجموعة متنوعة من حالات الاستخدام. كلما احتجت إلى التحدث إلى قاعدة بيانات واحدة أو أكثر ، ستساعدك Prisma كثيرًا من خلال تبسيط مهام سير عمل قاعدة البيانات.

## العمارة النظيفة والطبقات (Clean and layered architecture)

عند تطوير خوادم التطبيقات ، يكمن معظم التعقيد في تنفيذ وصول آمن وجيد التنظيم إلى قاعدة البيانات فيما يتعلق بالمزامنة وتحسين الاستعلام / الأداء والأمان. يصبح هذا الأمر أكثر تعقيدًا عند تضمين قواعد بيانات متعددة.

أحد الحلول الشائعة لهذه المشكلة هو إدخال طبقة وصول مخصصة للبيانات (DAL) تلخص تعقيدات الوصول إلى قاعدة البيانات. يتم استهلاك واجهة برمجة تطبيقات DAL بواسطة خادم التطبيق ، مما يسمح لمطوري واجهة برمجة التطبيقات بالتفكير ببساطة في البيانات التي يحتاجون إليها بدلاً من القلق بشأن كيفية استعادتها بأمان وبأداء فعال من قاعدة البيانات.



![image](https://i.imgur.com/SUH6AqW.png)

يضمن استخدام DAL فصلًا واضحًا للمخاوف ، وبالتالي يحسن قابلية الصيانة وإعادة استخدام التعليمات البرمجية الخاصة بك. إن الحصول على نوع من تجريد قاعدة البيانات (سواء كانت مكتبة ORM بسيطة أو مكونًا مستقلًا للبنية التحتية) هو أفضل ممارسة للتطبيقات الأصغر حجمًا وكذلك للتطبيقات التي تعمل على نطاق واسع. إنه يضمن أن خادم التطبيق يمكنه التحدث إلى قاعدة البيانات (قواعد البيانات) الخاصة بك بطريقة آمنة وفعالة.

ال Prisma عبارة عن DAL يتم إنشاؤه تلقائيًا ويتبع نفس مبادئ DAL الرائدة في الصناعة (مثل Twitter's Strato أو TAO على Facebook) بينما لا يزال يمكن الوصول إليه للتطبيقات الأصغر.

يتيح لك Prisma بدء مشروعك بهيكلية نظيفة من البداية ويوفر عليك من كتابة النموذج المعياري المطلوب بخلاف ذلك للصق قاعدة البيانات وخادم التطبيق معًا.



