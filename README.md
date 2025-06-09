# Arduino-
const int led_pin1 = 3;
const int led_pin2 = 5;
const int led_pin3 = 6;

void setup() {
  pinMode(led_pin1, OUTPUT);
  pinMode(led_pin2, OUTPUT);
  pinMode(led_pin3, OUTPUT);
}

void loop() {
  int brightness1;
  int brightness2;
  int brightness3;

  // Fade up
  for(int i = 0; i < 255; i++) {
    brightness1 = i;
    brightness2 = i - 70;
    brightness3 = i - 140;
    
    // Constrain brightness values between 0-255
    brightness1 = constrain(brightness1, 0, 255);
    brightness2 = constrain(brightness2, 0, 255);
    brightness3 = constrain(brightness3, 0, 255);
    
    analogWrite(led_pin1, brightness1);
    analogWrite(led_pin2, brightness2);
    analogWrite(led_pin3, brightness3);
    delay(50);
  }

  // Fade down
  for(int i = 255; i >= 0; i--) {
    brightness1 = i;
    brightness2 = i - 70;
    brightness3 = i - 140;
    
    // Constrain brightness values between 0-255
    brightness1 = constrain(brightness1, 0, 255);
    brightness2 = constrain(brightness2, 0, 255);
    brightness3 = constrain(brightness3, 0, 255);
    
    analogWrite(led_pin1, brightness1);
    analogWrite(led_pin2, brightness2);
    analogWrite(led_pin3, brightness3);
    delay(50);
  }
}
