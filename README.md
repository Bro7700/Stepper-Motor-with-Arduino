# Stepper-Motor-with-Arduino
Task 2
 
 
 ## المقدمة
 الـ stepper motor هو محرك يتحرك خطوة بخطوة بدلا من الدوران المستمر ويعمل بالتيار المستمر. يوجد داخل المحرك العديد من الملفات الموزعة بنظام في مجموعات تسمى “مراحل”. بتنشيط كل مرحلة على حدا يدور المحرك خطوة واحدة في كل مرة و من خلال البرمجة الحاسوبية يتم التحكم في المحرك لتحديد الموضع بدقة أو التحكم في السرعة. لهذا السبب تعد محركات stepper هي المناسبة للعديد من التطبيقات التي تتطلب التحكم الدقيق في الحركة .



 
 
 ## تم انشاء المشروع باستخدام
 
 
  برنامج Arduino IDE 1.8.19 [للتنزيل](https://www.arduino.cc/en/software)
  
 برنامج PROTEUS [للتنزيل](https://www.labcenter.com/simulation/)
 
 
 
 
 ## الادوات المستخدمة
 
 ##### 1- محرك خطوي احادي القطب Unipolar مع ULN2003A


1. لوحة Arduino UNO
2.محرك  Unipolar Stepper
3.اسلاك jumper wirs
4.لوحة driver board ULN2003
5. بطارية  5 and 12 volt 
6.لوحة breadboard
 
 
 ##### 2-محرك خطوي ثنائي القطب Bipolar stepper مع L293D Motor Driver
 
 
 
1. لوحة Arduino UNO
2.محرك Bipolar Stepper
3.اسلاك jumper wirs
4.لوحة Motor Driver  L293D
5. بطارية  5 and 12 volt 
6.لوحة breadboard
 
 
 ## كيفية التوصيل
 
 ##### 1- محرك Unipolar with ULN2003
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
 
 
 ##### 2-محرك Bipolar with L293D Motor Driver
 
 توصيل VSS 1 AND VSS2 الى 5V IN Ardunio 
 توصيل من لوحة L293D input(IN1 . IN2 . IN3 . IN4) الى الوردينو Output pins (pin 9 . pin10 . pin11 . pin12)
 توصيل GNR الى GNR في الاوردينو
 
 
 
 ## الرسم البياني والمحاكاة
 
 
 
 ### محرك خطوي احادي القطب UNIPOLAR مع ULN2003
 
 
 
 
 
 

 
 تحرك المحرك للدرجة 90 بعد خطوة واحدة
 
 
 
 ![STEPPER 2 U](https://user-images.githubusercontent.com/109243989/179368170-932578ae-55de-4a15-af88-d1a866730d3e.JPG)

  تحرك المحرك للدرجة 90 بعد خطوة واحدة
 

 
 
 
 ![STEPPER 3 U](https://user-images.githubusercontent.com/109243989/179368176-a8ab2997-fbfe-4132-9d9b-eed8ba9c12a0.JPG)



 تحرك المحرك للدرجة 180 بعد خطوتين




![STEPPER 4 U](https://user-images.githubusercontent.com/109243989/179368180-ae4aaba9-a00c-4f5a-9843-5d23b12d44fd.JPG)



تحرك المحرك الى الدرجة 270 بعدة 3 خطوات  





![STEPPER 5 U](https://user-images.githubusercontent.com/109243989/179368186-60083b80-1f70-467a-b5f3-9871b27435fd.JPG)



تحرك المحرك الى الدرجة 360 بعد 4 خطوات 




#### The Code

Demonstrates 28BYJ-48 Unipolar Stepper with ULN2003 Driver

Uses Arduino Stepper Library

//Include the Arduino Stepper Library

#include <Stepper.h>

// Define Constants

// Number of steps per internal motor revolution

const float STEPS_PER_REV = 32;

// Amount of Gear Reduction

const float GEAR_RED = 64;

// Number of steps per geared output rotation

const float STEPS_PER_OUT_REV = STEPS_PER_REV * GEAR_RED;

// Define Variables

// Number of Steps Required

int StepsRequired;

// Create Instance of Stepper Class

// Specify Pins used for motor coils

// The pins used are 8,9,10,11

// Connected to ULN2003 Motor Driver In1, In2, In3, In4

// Pins entered in sequence 1-3-2-4 for proper step sequencing

Stepper steppermotor(STEPS_PER_REV, 8, 10, 9, 11);

void setup() {

// Nothing (Stepper Library sets pins as outputs)

}

void loop() {

// Slow - 4-step CW sequence to observe lights on driver board

steppermotor.setSpeed(1);

StepsRequired = 4;

steppermotor.step(StepsRequired);

delay(2000);

// Rotate CW 1/2 turn slowly

StepsRequired = STEPS_PER_OUT_REV / 2;

steppermotor.setSpeed(100);

steppermotor.step(StepsRequired);

delay(1000);

// Rotate CCW 1/2 turn quickly

StepsRequired = - STEPS_PER_OUT_REV / 2;

steppermotor.setSpeed(700);

steppermotor.step(StepsRequired);

delay(2000);

}
 
 --------------------------------------------------------------------------------------------------------------------------------------------------------------------
 
 
 ### محرك خطوي ثنائي القطب BIPOLAR مع L293D
 
 
 
 
 ![STEPPER PI 1](https://user-images.githubusercontent.com/109243989/179368610-039fc6be-2f6e-4bc6-ae4d-81b970826ce0.JPG)

 
 
 دوران مع عقارب الساعة 
 
 
 
 ![STEPPER PI 2](https://user-images.githubusercontent.com/109243989/179368630-2a8cd643-9623-40b3-8c3c-cd1176435485.JPG)

 
 
 
 
 
 
 ![STEPPER PI 3](https://user-images.githubusercontent.com/109243989/179368632-0cd621a2-a434-4c4e-807a-981c952a6166.JPG)

 
 دوران عكس عقارب الساعة 

 
### The code

// Include the Arduino Stepper Library #include <Stepper.h>

// Number of steps per output rotation NEMA 17

const int stepsPerRevolution = 200;

// Create Instance of Stepper library

Stepper myStepper(stepsPerRevolution, 12, 11, 10, 9);

void setup() { // set the speed at 20 rpm:

myStepper.setSpeed(20);

}

void loop() { // step one revolution in one direction:

myStepper.step(stepsPerRevolution);

delay(500);

// step one revolution in the other direction:

myStepper.step(-stepsPerRevolution);

delay(500); }
