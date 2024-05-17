# TextField-Validation-In-Flutter

▪︎ مهم جداً

- عايز اتكلم معاكم ف نقطتين بخصوص التحقق (validation) 
اللي بنعمله عشان نلزم الuser يدخل داتا معينه

1• لو انطلب منك تخلي ال user يدخل email ومحتاج تعمل validate علي الtext اللي هو دخله ده انه فعلاً email.

2• لو انطلب منك تخلي المستخدم يدخل text و لكن ب form معينه.

علي سبيل المثال AA-1234-BB

ف عشان تلزم ال user يدخل مثلاً حروفين ثم اربع ارقام ثم حرفين و بين كل من الحروف و الارقام تعمل الشكل ده ( - )

ف ان شاء الله هيكون موضوعونا
● الحل

- الحاله الاولي الخاصه بال validation الخاص بال email: 
- في الحاله دي هنستخدم : inputFormatters parameter الموجود في TextFormField Widget واللي بياخد قيمه عباره عن List<TextInputFormatter>?
- و عشان نلزم ال user يدخل valid email
 هنستخدم ال inputFormatter زي الموجود بالمثال ده

 TextFormField(
 maskFormatter: [
 FilteringTextInputFormatter.allow(
 RegExp(r'[a-zA-Z0-9_@.]'))
 ]
 )
الحاله التانية: هي انك تخلي المستخدم يدخل داتا علي هيئة form

- هنستخدم مكتبة مهمه جداً تسمي : mask_text_input_formatter
- ودا عشان احصل علي قيمة من نوع TextInputFormatter 
واستخدم بعد كدا القيمه دي ف إعطاء لل parameter الموجوده ف ال TextField بتاعي (inputFormatters)
ex : TextInputFormatter x = MaskTextInputFormatter(
mask: 'AA-####-AA',
type: MaskAutoCompletionType.eager
);
- link package : https://lnkd.in/gt5ZH32G

 TextFormField(
 maskFormatter: [
 MaskTextInputFormatter(
 mask: 'AA-####-AA',
 type: MaskAutoCompletionType.eager
 )],)
 <div>
 •  Example
 </div>
 <div>
<img src='https://github.com/Ahmedelsapagh10/TextFormField-in-Flutter-validation-/blob/master/textformfield1.png' width="70%"/>
<img src='https://github.com/Ahmedelsapagh10/TextFormField-in-Flutter-validation-/blob/master/textformfield2.png' width="70%"/>
 </div>

hashtag#flutter
hashtag#flutter_dev

