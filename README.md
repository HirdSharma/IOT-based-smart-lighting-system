// --- Pin Definitions ---
const int ldrPin = A0;        // LDR connected to analog pin A0
const int pirPin = 2;         // PIR motion sensor on digital pin 2
const int ledPin = 9;         // LED/Streetlight on PWM pin 9

// --- Thresholds ---
int lightThreshold = 300;     // Adjust as per ambient light conditions (0-1023)
int ledHigh = 255;            // Full brightness
int ledLow = 80;              // Dimmed light
int ledOff = 0;               // Light OFF

void setup() {
  pinMode(ldrPin, INPUT);
  pinMode(pirPin, INPUT);
  pinMode(ledPin, OUTPUT);
  
  Serial.begin(9600);
  Serial.println("Smart Street Lighting Initialized");
}

void loop() {
  int lightLevel = analogRead(ldrPin);         // Read ambient light
  bool motion = digitalRead(pirPin);           // Read motion status (HIGH/LOW)

  Serial.print("Light Level: ");
  Serial.print(lightLevel);
  Serial.print(" | Motion: ");
  Serial.println(motion);

  // Control logic
  if (lightLevel < lightThreshold) {           // Night or low light
    if (motion) {
      analogWrite(ledPin, ledHigh);            // Full brightness
    } else {
      analogWrite(ledPin, ledLow);             // Dim
    }
  } else {
    analogWrite(ledPin, ledOff);               // Daytime - lights OFF
  }

  delay(500); // Sampling delay
}



