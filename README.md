12 a.
intrfelling keypad module record strokes


void setup() {
  Serial.begin(9600);
  pinMode(35, INPUT);
}

void loop() {
  int val;
  val = digitalRead(35);
  Serial.println(val);

  if (val == 1) {
    Serial.println("Key pressed");
  } else {
    Serial.println("Key Released");
  }

  delay(2000);
}






12 b.control odboard led by keypad


void setup() {
  Serial.begin(9600);
  pinMode(35, INPUT);
  pinMode(2, OUTPUT);
}

void loop() {
  int val;
  val = digitalRead(35);
  Serial.println(val);
  delay(500);

  if (val == 1) {
    Serial.println("LED is ON");
    digitalWrite(2, HIGH);
  } else {
    Serial.println("LED is OFF");
    digitalWrite(2, LOW);
  }






10 a.

uart pass string





void setup() {

  Serial.begin(9600);

}



void loop() {

  Serial.println("Amc Eng College");

  delay(2000);

}











10 b.

disply int float





void setup() {

  Serial.begin(9600);

}



void loop() {

  int i = 29567;

  Serial.println(1234);

  Serial.println(234.25);

  Serial.println("Amc Eng College");

  Serial.println(i);

  Serial.println('A');

  delay(2000);

}









10 c.display string 5 times





void setup() {

  Serial.begin(9600);

  for (int i = 0; i < 5; i++) {

    Serial.println("AMC");

    delay(2000);

  }

}



void loop() {

}









10 d.control led serial monitor





void setup() {

  Serial.begin(9600);

  pinMode(8, OUTPUT);

}



void loop() {

  char val;

  if (Serial.available() > 0) {

    val = Serial.read();



    if (val == '1') {

      digitalWrite(8, HIGH);

    }



    if (val == '0') {

      digitalWrite(8, LOW);

    }

  }

}





1

// Program 01: Develop a program to blink 5 LEDs back and forth.



void LED_Clear();

int LED[] = {18, 19, 23, 25, 26};

int ledCount = sizeof(LED) / sizeof(LED[0]);



void setup() {

  for (int i = 0; i < ledCount; i++) {

    pinMode(LED[i], OUTPUT);

  }

}



void loop() {

  // Forward direction

  for (int i = 0; i < ledCount; i++) {

    LED_Clear();

    digitalWrite(LED[i], HIGH);

    delay(100);

  }



  // Backward direction

  for (int i = ledCount - 1; i >= 0; i--) {

    LED_Clear();

    digitalWrite(LED[i], HIGH);

    delay(100);

  }

}



void LED_Clear() {

  for (int i = 0; i < ledCount; i++) {

    digitalWrite(LED[i], LOW);

  }

}





3 ultrasonic sound sensor



#include <NewPing.h>



#define TRIGGER_PIN 18

#define ECHO_PIN 19

#define MAX_DISTANCE 200

#define BUZZER_PIN 14



NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);



void setup() {

  Serial.begin(9600);

  pinMode(BUZZER_PIN, OUTPUT);

}



void loop() {

  delay(1000);

  unsigned int distance = sonar.ping_cm();



  Serial.print("Distance: ");

  Serial.print(distance);

  Serial.println(" cm");



  if (distance > 0 && distance < 6) {

    digitalWrite(BUZZER_PIN, HIGH);

  } else {

    digitalWrite(BUZZER_PIN, LOW);

  }

}





5a read light using ldr 



void setup() {

  Serial.begin(9600);

  pinMode(36, INPUT);

}



void loop() {

  int val;

  val = analogRead(36);

  Serial.println(val);

}



5b smart street light





void setup() {

  Serial.begin(9600);

  pinMode(36, INPUT);

  pinMode(2, OUTPUT);

}



void loop() {

  int val;

  val = analogRead(36);

  Serial.println(val);



  if (val < 500) {

    digitalWrite(2, HIGH);

  } else {

    digitalWrite(2, LOW);

  }

}

