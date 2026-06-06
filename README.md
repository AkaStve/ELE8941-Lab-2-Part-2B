// ELE8941 Robotics Lab 2 May 29, 2026
void setup()
{
pinMode(2, OUTPUT);   // PWM pin
pinMode(30, OUTPUT);  // DIR pin
Serial.begin(9600);
delay(500);
Serial.println("Motor Tests    Name: Steve Liu    Date: May 29, 2026");
}
void loop()
{
    Serial.println("75% CCW    ");
    digitalWrite(30, HIGH); // direction CCW
    analogWrite(2, 191); // 75% PWM
    delay(5000);               // run for 5 seconds
    
    analogWrite(2, 0);
    delay(1000);

    Serial.println("75% CW    ");
    digitalWrite(30, LOW);    // direction CW
    analogWrite(2, 191);      // 75% PWM
    delay(5000);

    Serial.println("50% CW    ");
    analogWrite(2, 128);      // 50% PWM
    delay(5000);

    Serial.println("40% CW    ");
    analogWrite(2, 102);      // 40% PWM
    delay(5000);

    analogWrite(2, 0);        // wait with motors off

    while(1);                 // wait for an Arduino H/W Reset
}
