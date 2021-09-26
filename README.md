const int LOWLEVEL = A0;    // Green LED Lower
const int MIDLEVEL = A1;    // Blue LED Mider
const int HILEVEL = A2;     // Red LED Higher

const int LOWLEVELLED = 0 ;
const int MIDLEVELLED = 1 ;
const int HILEVELLED = 2 ;

int LowSts = 0 ;
int MidSts = 0 ;
int HiSts  = 0 ;

void setup() {

  pinMode(LOWLEVEL, INPUT_PULLUP);    // Sensors
  pinMode(MIDLEVEL, INPUT_PULLUP);
  pinMode(HILEVEL, INPUT_PULLUP);

  pinMode(LOWLEVELLED, OUTPUT);       // LEDs
  pinMode(MIDLEVELLED, OUTPUT);
  pinMode(HILEVELLED, OUTPUT);

    pinMode(LED_BUILTIN, OUTPUT);

    digitalWrite(LED_BUILTIN, LOW);

    digitalWrite(LOWLEVELLED, LOW);
    digitalWrite(MIDLEVELLED, LOW);
    digitalWrite(HILEVELLED, LOW);
}

void loop() {

  LowSts = digitalRead(LOWLEVEL);

  if (LowSts == LOW ) {
    digitalWrite(LOWLEVELLED, HIGH);
  } else {
    digitalWrite(LOWLEVELLED, LOW);
    
  }

  MidSts = digitalRead(MIDLEVEL);

  if (MidSts == LOW) {
    digitalWrite(MIDLEVELLED, HIGH);
  } else {
    digitalWrite(MIDLEVELLED, LOW);
  }

 HiSts = digitalRead(HILEVEL);

  if (HiSts == LOW) {
    digitalWrite(HILEVELLED, HIGH);
        digitalWrite(LED_BUILTIN, HIGH);

  } else {
    digitalWrite(HILEVELLED, LOW);
        digitalWrite(LED_BUILTIN, LOW);
  }
}
