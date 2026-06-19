#define trigPin 9
#define echoPin 10
#define buzzer 6
#define led 7
#define motor 5

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(led, OUTPUT);
  pinMode(motor, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  long duration;
  int distance;

  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Read echo
  duration = pulseIn(echoPin, HIGH);

  // Convert to distance (cm)
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.println(distance);

  // Alert logic
  if (distance > 0 && distance <= 50) {
    digitalWrite(buzzer, HIGH);
    digitalWrite(led, HIGH);
    digitalWrite(motor, HIGH);
  } 
  else {
    digitalWrite(buzzer, LOW);
    digitalWrite(led, LOW);
    digitalWrite(motor, LOW);
  }

  delay(200);
}
