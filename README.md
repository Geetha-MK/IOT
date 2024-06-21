// Define the pin for the flame sensor
#define FLAME_SENSOR_PIN D2
// Define the pin for the buzzer
#define BUZZER_PIN D1

void setup() {
  // Initialize the flame sensor pin as input
  pinMode(FLAME_SENSOR_PIN, INPUT);
  // Initialize the buzzer pin as output
  pinMode(BUZZER_PIN, OUTPUT);
  // Start serial communication
  Serial.begin(9600);
}

void loop() {
  // Read the value from the flame sensor
  int flameValue = digitalRead(FLAME_SENSOR_PIN);

  // If flame is detected
  if (flameValue == HIGH) {
    Serial.println("Fire detected!");
    digitalWrite(BUZZER_PIN, HIGH); // Sound the alarm
    delay(1000); // Sound for 1 second
    digitalWrite(BUZZER_PIN, LOW); // Turn off the alarm
  } else {
    Serial.println("Fire not detected");
    digitalWrite(BUZZER_PIN, LOW); // Turn off the alarm
  }

  // Delay before next reading
  delay(500);
}
