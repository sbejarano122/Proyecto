#include <NewPing.h>
#define TRIG_PING A0
#define ECHO_PIN A1
#define MAX_DISTANCE 200
#define MAX_SPEED 190 // sets speed of DC motors 
#define MAX_SPEED_OFFSET 20 NewPing sonar(TRIG_PIN,ECHO_PIN,MAX_DISTANCE);


boolean goesForward=false;
int distance = 100;
int speedSet = 0;


int IN1 = 7;//motor B
int IN2 = 6;//motor B
int IN3 = 5;//motor A
int IN4 = 4;//motor A


void setup() {
  distance = readPing();
  delay(100);
  distance = readPing();
  delay(100);
  distance = readPing();
  delay(100);
  distance = readPing();
  delay(100);


  pinMode (IN1, OUTPUT); //Input1
  conectada al pin 7 motor B 
  pinMode (IN2, OUTPUT); //Input2
  conectada al pin 6 motor B 
  pinMode (IN4, OUTPUT); //Input4
  conectada al pin 4 motor A 
  pinMode (IN3, OUTPUT); //Input3
  conectada al pin 5 motor A
}
void loop if(distance<=20)
{
  moveStop();
  delay(100);
  moveBackward();
  moveStop();
  delay(200);
}
else
{
  moveForwad();
}
distance = readPing();
}
int readPing() {
  delay(70);
  int cm = sonar.ping_cm();
  if(cm==0)
  {
    cm = 250;
  }
  return cm;
}


void moveStop () {
  if(!goesForward)
  {
    goesForward=true;
    digitalWrite (IN3, HIGH);
    digitalWrite (IN1, HIGH);
    delay(5);
  }
}


void moveBackward() {
  goesForward=false;
  digitalWrite (IN4,HIGH);
  digitalWrite (IN2,HIGH);
  delay (5);
}
