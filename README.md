# Stepper-Motor-with-Arduino
Task 2
 
 
 ## المقدمة
 الـ stepper motor هو محرك يتحرك خطوة بخطوة بدلا من الدوران المستمر ويعمل بالتيار المستمر. يوجد داخل المحرك العديد من الملفات الموزعة بنظام في مجموعات تسمى “مراحل”. بتنشيط كل مرحلة على حدا يدور المحرك خطوة واحدة في كل مرة و من خلال البرمجة الحاسوبية يتم التحكم في المحرك لتحديد الموضع بدقة أو التحكم في السرعة. لهذا السبب تعد محركات stepper هي المناسبة للعديد من التطبيقات التي تتطلب التحكم الدقيق في الحركة .



 
 
 ## تم انشاء المشروع باستخدام
 
 
  برنامج Arduino IDE 1.8.19 [للتنزيل](https://www.arduino.cc/en/software)
  
 برنامج PROTEUS [للتنزيل](https://www.labcenter.com/simulation/)
 
 
 
 
 ## الادوات المستخدمة
 
 # 1- محرك خطوي احادي القطب Unipolar مع ULN2003A


1. لوحة Arduino UNO
2.محرك  Unipolar Stepper
3.اسلاك jumper wirs
4.لوحة driver board ULN2003
5. بطارية  5 and 12 volt 
6.لوحة breadboard
 
 
 # 2-محرك خطوي ثنائي القطب Bipolar stepper مع L293D Motor Driver
 
 
 
1. لوحة Arduino UNO
2.محرك Bipolar Stepper
3.اسلاك jumper wirs
4.لوحة Motor Driver  L293D
5. بطارية  5 and 12 volt 
6.لوحة breadboard
 
 
 ## كيفية التوصيل
 
 # 1- محرك Unipolar with ULN2003
  توصيل ULN2003 pin1 الى  pin 8 in Ardunio
 توصيل ULN2003 pin2 الى  pin 9 in Ardunio
 توصيل ULN2003 pin3 الى  pin 10 in Ardunio
 توصيل ULN2003 pin4 الى pin 11 in Ardunio
 توصيل ULN2003 pin16 الى pin1 in stepper
 توصيل ULN2003 pin15 الى pin2 in stepper
توصيل ULN2003 pin14 الى pin3 in stepper
 توصيل ULN2003 pin13 الى pin4 in stepper
 توصيل ULN2003 pin9 and the 2 2VDD pin in stepper motor الى 12v battery 
 توصيل ground الى ground
 
 
 # 2-محرك Bipolar with L293D Motor Driver
 
 توصيل VSS 1 AND VSS2 الى 5V IN Ardunio 
 توصيل من لوحة L293D input(IN1 . IN2 . IN3 . IN4) الى الوردينو Output pins (pin 9 . pin10 . pin11 . pin12)
 توصيل GNR الى GNR في الاوردينو
 
 
 
 ## الرسم البياني والمحاكاة
 
 
 
 ### محرك خطوي احادي القطب مع ULN2003
 
 
 
 
 
 
 ![STEPPER 1 U](https://user-images.githubusercontent.com/109243989/179367912-023368de-28e7-4095-879b-f7cd93d964f6.JPG)

 
 
 
