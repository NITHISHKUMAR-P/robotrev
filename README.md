# robotrev
### Exp 1
<a href="https://www.tinkercad.com/things/1ItpOndYOJ5-epic-hango/editel?sharecode=-EYccamFH8894J2QIR8qzGyvCgMixTpWxe7FUvluMYU">Exp 1 sensor</a>
```
#define trigpin 2
#define echopin 3
long  distance;
int duration;
void setup()
{ 
    pinMode(trigpin,OUTPUT);
    pinMode(12,OUTPUT);
    pinMode(8,OUTPUT);
    pinMode(echopin,INPUT);
    Serial.begin(9600);
}
void loop()
{
    
    digitalWrite(trigpin,LOW);
    digitalWrite(trigpin,HIGH);
    digitalWrite(trigpin,LOW);
    duration = pulseIn(echopin,HIGH);
    distance = duration*0.034/2;
    Serial.print("distance = ");
    Serial.println(distance);
    Serial.print("cm");
    if(distance>100)
    {
        
        digitalWrite(12,HIGH);
        digitalWrite(8,LOW);
        
    }
    else{
        digitalWrite(12,LOW);
        digitalWrite(8,HIGH);
    }
  ```
  ### Exp 2
  <a href="https://www.tinkercad.com/things/fP8A0bKbm08-ingenious-gogo/editel?sharecode=JDqpQJ2VUs9jJDzofZlEXaw0K1-9u52DLM7TVZ2ogBM">Potentiometer</a>
  ```
  //exp 2
int sensorvalue = A0;
int ledpin = 9   ;
void setup()
{
    
    sensorvalue = 0;
    Serial.begin(9600);
    pinMode(ledpin,OUTPUT);
    
    
}
void loop()
{
    
    sensorvalue = analogRead(A0);
    Serial.println(sensorvalue);
    delay(300);
    digitalWrite(ledpin,sensorvalue);
}
```
### Exp 3
<a href="https://www.tinkercad.com/things/1ddNeFtMTGZ-grand-bruticus-elzing/editel?sharecode=WF5LYhw0yi6OojKQ_WHw8XvrvXKKg0K4pJhH1xdxrp4">DC motor</a>
```
// C++ code
//l293D
const int motorPin1 = 5;//pin 14 of L293
const int motorPin2 = 6;//pin 10 of L293
// this will run only one time
void setup(){
  //set pins as output
  pinMode(motorPin1,OUTPUT);
  pinMode(motorPin2, OUTPUT);
}
void loop(){
  digitalWrite(motorPin1,LOW);
  delay(2000);
  digitalWrite(motorPin2,HIGH);
  delay(2000);
}
```
### Exp 4
<a href="https://www.tinkercad.com/things/h5HzCl37Af6-smooth-allis/editel?sharecode=q2nFYne8a0B-_zjx08oSbTnr_TBrCIZRpkowAQIsSNs">Servo</a>
```
#include <Servo.h> 
int pos = 0;
Servo q;
void setup()
{
q.attach(10,500,2500);
Serial.begin(9600);
}
void loop()
{
for (pos = 0;pos<=180;pos+=1)
{
q.write(pos);
delay(5);
Serial.print("angle of servo= ");
Serial.println(pos);
}
for (pos = 180;pos>=0;pos-=1)
{
q.write(pos);
delay(10);
Serial.print("angle of servo= ");
Serial.println(pos);
}
delay(100);
Serial.print("angle of servo= ");
Serial.println(pos);
}
```
### Exp 5
<a href="https://www.tinkercad.com/things/8TCCM4YfItW-powerful-wolt/editel?sharecode=rZmtr0y-VBj2z62CvnaFctMSFw_4k3DsoEuALiTBlXQ">Led lights</a>
```
// C++ code
//
void setup()
  
{
  pinMode(12,OUTPUT);
  pinMode(8,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(2,OUTPUT);
}

void loop()
{
  digitalWrite(12,HIGH);
  delay(500);
  digitalWrite(12,LOW);
  delay(500);
  
  digitalWrite(8,HIGH);
  delay(500);
  digitalWrite(8,LOW);
  delay(500);
  
  digitalWrite(4,HIGH);
  delay(500);
  digitalWrite(4,LOW);
  delay(500);
  
  digitalWrite(2,HIGH);
  delay(500);
  digitalWrite(2,LOW);
  delay(500);
  
  
}
```
### Exp 6
<a href="https://www.tinkercad.com/things/ds5u6TmxbY8-fabulous-fyyran-kasi/editel?sharecode=ovl-v5K0PiKcd6_O-a-VtyZ_ytz7dUigtwaLDZaKDaY">FSR force</a>
```
int sensorvalue=A0;
int led=9;
int force;
void setup()
{
 sensorvalue=0;
 Serial.begin(9600);

 
}

void loop()
{
 sensorvalue=analogRead(A0);
 force=map(sensorvalue,0,466,0,10);
 Serial.print("\nraw value= ");
 Serial.println(sensorvalue);
 Serial.print("force= ");
 Serial.print(force);
 delay(100);

}
```
### Exp 7
<a href="https://www.tinkercad.com/things/8FoTFeiqdzT-brilliant-waasa/editel?sharecode=hR1WXfLNE1cyKZiTACEi3KHJh84D9Mcfh3terhwaLzI">Push btn</a>
```

int ledpin=4;
int pushbtn=2;
int val=0;
void setup()
{
  pinMode(ledpin, OUTPUT);
  pinMode(pushbtn,INPUT);
}

void loop()
{
  int val=digitalRead(pushbtn);
  if(val==0)
  {
    digitalWrite(ledpin,HIGH);
    
  }
  else
  {
    digitalWrite(ledpin,LOW);
    delay(100);
  }
}
```
### Exp 8
<a href="https://www.tinkercad.com/things/lxBfQBCfe3R-spectacular-maimu-bombul/editel?sharecode=HDbP0qJ--wFBmqw4nNjQMBnSmAwBgDnAli94cKueUB4">Series push</a>
```
// C++ code
//
void setup()
{
  pinMode(8,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(2,OUTPUT); 
}

void loop()
{
  digitalWrite(8, HIGH);
  delay(100); // Wait for 1000 millisecond(s)
  digitalWrite(8, LOW);
  delay(200); // Wait for 1000 millisecond(s)
  digitalWrite(7, HIGH);
  delay(200); // Wait for 1000 millisecond(s)
  digitalWrite(7, LOW);
  delay(500);
  digitalWrite(4, HIGH);
  delay(100); // Wait for 1000 millisecond(s)
  digitalWrite(4, LOW);
  delay(500);
  digitalWrite(2, HIGH);
  delay(500); // Wait for 1000 millisecond(s)
  digitalWrite(2, LOW);
  delay(300);
}
```
