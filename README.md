# مشروع توقع ممشى السيارة المستعلمة في المملكة العربية السعودية 

## المقدمة والأهداف 🎯
في مشروعنا، نهدف إلى توقع ممشى السيارة المستخدمة في المملكة العربية السعودية. سنقوم بتحليل مجموعة البيانات التي تحتوي على معلومات عن السيارات المستعملة، واستكشاف العلاقات بين مختلف السمات وتأثيرها على الممشى. من خلال بناء نماذج تعلم الآلة، نعتزم إنشاء نماذج تنبؤية يمكنها تقدير ممشى السيارة استنادًا إلى خصائصها.

# أعضاء الفريق 👥
1. ريان العوفي: عمل على تعلم الآلة وملف التعليمات
2. حسام الزهراني: عمل على الرسوم البيانية
3. محمد سعود: عمل على اختيار الفكرة وتنظيف البيانات وتعلم الآلة

## نظرة عامة على مجموعة البيانات ومصدرها 📈
في هذا المشروع، نستخدم مجموعة بيانات من Kaggle تحتوي على معلومات حول السيارات المستعملة في المملكة العربية السعودية. توفر مجموعة البيانات ميزات متنوعة مثل الصانع، والموديل، والسنة، والممشى، والسعر، ونوع الوقود، والمزيد. يمكن العثور على مجموعة البيانات [Saudi Arabia Used Cars](https://www.kaggle.com/datasets/turkibintalib/saudi-arabia-used-cars-dataset)

## تجهيز البيانات وتنظيفها 🧹
بعد رفع مجموعة البيانات باستخدام مكتبة Pandas، تم تجهيز البيانات وتنظيفها عن طريق استخدام Alteryx
اتخذنا عدة خطوات لتجهيز وتنظيف البيانات قبل استخدامها في التحليل والتصور:

- لاحظنا وجود عمود يحتوي على رابط الإعلان و و آخر يحتوي على حالة السيارة وبما أنهما لايخدمان غرض التحليل تم استبعادهما.
- هناك بيانات مفقودة في إعمدة مواصفات السيارة، نوع ناقل الحركة، حجم المحرك، المسافة المقطوعة و السعر فتعاملنا معها على النحو التالي:
- حساب المتوسط للسعر و المسافة المقطوعة حسب سنة الصنع و الطراز  ثم تبديلها في العمود الفارغ، لاحظنا وجود قيم مفقودة فتم تعبئتها بالصف الذي يسبقها.
- حساب القيمة المتكررة للإعمدة الباقية حسب سنة الصنع والطراز و تبديلها بالقيمة الفارغة، لاحظنا وجود قيم مفقودة فتم تعبئتها بالصف الذي يسبقها.
- كانت غالبية البيانات حسب المنطقة الإدارية، لكن كانت هناك بيانات لبعض المحافظات فأدرجناها لمناطقها الإدارية.
- في بيانات الوقود، كانت هناك بيانات للسيارات الهجينة و سيارات الديزل، أقصيناها لكي لا تؤثر على البيانات حيث كانت لا تمثل إلا ٢٪؜ من البيانات.

## الرسوم البيانية والأفكار 📊
يتضمن في الرسوم البيانية والافكار تصور العلاقات واكتشاف جذور المشكلة بين البيانات المختلفة مع بيانات ممشى السيارة

### 1. (ممشى السيارة والأسعار) 📈
   
![newplot](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/281fb1c4-85b0-4576-a17c-c7cdcff8ca06)


### بعض الأفكار والتصورات:
- كل ما زاد ممشى السيارة قل سعرها.
- مجموع الاسعار للسيارات التي عدد اميالها قليل اعلى من التي عدد اميالها كثير.

---


### 2. (توزيع ممشى السيارة في كل منطقة بالسعودية) 📈
   
![newplot](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/2e695afa-416f-44f1-90f0-cb2ccd9d5fd4)


### بعض الأفكار والتصورات:
- اعلى منطقة من ناحية زيادة عدد اميال السيارة هي منطقة الرياض.
- نلاحظ ان المناطق الرئيسية بالمملكة هي التي تزيد فيها عدد اميال السيارات.

---


### 3. (اكبر 5 شركات كمتوسط عدد اميال) 📈
   
![newplot](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/a97bd27d-9c92-40ca-9d38-609d006d46d1)


### بعض الأفكار والتصورات:
- اكبر 5 شركات هي تويوتا، مازدا، شفرولية، جيب، ميركوري.

---


### 4. (الاسعار حسب لون السيارة في كل منطقة بالسعودية) 📈
   
![newplot](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/61780e08-02c6-4ccc-b798-d7566446065a)


### بعض الأفكار والتصورات:
- اللون الابيض والاسود والسلفر والرمادي هي التي متواجده في كل المناطق.
- اسعار السيارات التي باللون الابيض في جميع المناطق هي الاعلى

---


### 5. (مجموع الاسعار حسب حجم المكينة) 📈
   
![newplot](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/cc7a59ce-f7fd-4007-972c-0a05f7bc95c9)


### بعض الأفكار والتصورات:
- مجموع اسعار احجام المكينة الكبيرة هي الاقل
- مجموع اسعار احجام المكينة الصغيرة هي الاعلى
- نلاحظ ان هناك ارقام مكائن معينة هي التي تنتشر بين السيارات في السعودية.



## جدول نتائج نماذج تعلم الآلة 📋
في هذا القسم، ستجد جدول يلخص نتائج النماذج المختلفة التي تم بناؤها باستخدام خوارزميات مختلفة من تعلم الآلة. يقدم الجدول مقارنة موجزة لأداء هذه النماذج في توقع ممشى السيارة استنادًا إلى مجموعة متنوعة من البيانات.

![image](https://github.com/RynHb/Bootcamp-Project-4-ML/assets/62115163/9faf640e-58b1-4312-87dc-bb10d7c7694b)

#### استنتاج نهائي حول نتائج النماذج
##### في نموذج Linear Regression و Decision Tree و SVM تم التوصل إلى النتائج التالية:
- بما أن مقياس MSE و MAE و RMSE مرتفع جدًا، سيؤدي ذلك إلى تقديم توقعات سيئة من النماذج.
- بما أن قيمة R^2 سالبة، فإن النماذج ليس نموذجًا جيدًا للبيانات.
##### من ناحية أخرى، تم التوصل إلى الاستنتاجات التالية في نموذج Random Forest:
- في هذا النموذج، تقل قيمة MSE و MAE عن النماذج الأخرى، وسيقدم توقعات أفضل. R^2 غير سالب، مما يُعتبر إشارة جيدة.

---


**للحصول على معلومات برمجية مفصلة واكثر، يرجى الرجوع إلى ملف الكود Python الموجود في هذا المستودع.**
