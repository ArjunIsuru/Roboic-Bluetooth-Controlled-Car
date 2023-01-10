# Roboic-Bluetooth-Controlled-Car

*Arduino Car Using Bluetooth*

Forward,Reverse and Stop and further more one side tyre forwad is working...That means a rotation in Mechanics...


*_Code:-_*

#include<SoftwareSerial.h>
SoftwareSerial bluetooth(10,11);
char data;
int a=150,b=150;
void setup() {
  Serial.begin(115200);
  bluetooth.begin(9600);
  pinMode(2,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
}
void loop() {
  if(bluetooth.available()){
  data=bluetooth.read();
  Serial.println(data);
}  
  if(data=='F'){forward();}
  if(data=='B'){backward();}
  if(data=='L'){left();}
  if(data=='R'){right();}
  if(data=='S'){stop();}
}
void forward(){
  digitalWrite(2,HIGH);
  digitalWrite(3,LOW);
  analogWrite(4,a);
  
  digitalWrite(5,HIGH);
  digitalWrite(6,LOW);
  analogWrite(7,b);
  }
void backward(){
  digitalWrite(2,LOW);
  digitalWrite(3,HIGH);
  analogWrite(4,a);
  
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  analogWrite(7,b);
  }
void right(){
digitalWrite(2,HIGH);
  digitalWrite(3,LOW);
  analogWrite(4,a);
  
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  analogWrite(7,b);
  }
void left(){
  digitalWrite(2,LOW);
  digitalWrite(3,HIGH);
  analogWrite(4,a);
  
  digitalWrite(5,HIGH);
  digitalWrite(6,LOW);
  analogWrite(7,b);
  }
void stop(){
digitalWrite(2,LOW);
  digitalWrite(3,LOW);
  analogWrite(4,0);
  
  digitalWrite(5,LOW);
  digitalWrite(6,LOW);
  analogWrite(7,0);
  
}

*Quora about Arduino Car*

Most of the People Asked me how could I rotate the Car...

It is simple that,Everyone knows about coupled Forces...

So, First I Rotate the Right wheel to the Forward and the Left wheel to the backward...

Then the Car is rotating  CounterClockwise...

*Arjun ( Isuru ) 🍁✨*



