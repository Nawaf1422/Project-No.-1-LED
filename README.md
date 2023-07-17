# Project-No.-1-LED
1- We collect the necessary pieces 2- Place the Arduino board and connect the wires 3- Place the LED and resistors 4- Connect the Arduino wire 5- Place the code and application
#define LED_PIN 8
#define BUTTON_PIN 7

byte lastButtonState = LOW;
byte ledState = LOW;

void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT);
}

void loop() {
  byte buttonState = digitalRead(BUTTON_PIN);
  if (buttonState != lastButtonState) {
    lastButtonState = buttonState;
    if (buttonState == LOW) {
      ledState = (ledState == HIGH) ? LOW: HIGH;
      digitalWrite(LED_PIN, ledState);
    }
  }
}
