#include <LiquidCrystal.h>         
const int rs = 2, en = 3, d4 = 4, d5 = 5, d6 = 6, d7 = 7;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

float tempC;    // Temperature in Celsius
float tempF;    // Temperature in Fahrenheit

void setup() {
  Serial.begin(9600);
  analogReference(INTERNAL);            // Using internal reference voltage (1.1V)
  lcd.begin(16, 2);                     // Initialize the LCD with 16x2 characters
  lcd.setCursor(0, 0);
  lcd.print("   Made by Mahin ");      
  lcd.setCursor(0, 1);
  lcd.print("  Basic Project    ");
  delay(1000);                          // Show the message for 1 second
  lcd.clear();                          
}

void loop() {
  int sensorValue = analogRead(A1);     // Read the analog input from LM35 sensor

  // Convert the analog input to Celsius
  tempC = sensorValue * 1100.0 / (1024.0 * 10.0);  // Correct calculation for Celsius using internal reference voltage
  
  // Convert Celsius to Fahrenheit
  tempF = tempC * 9.0 / 5.0 + 32.0;

  // Display the Celsius temperature
  lcd.setCursor(0, 0);                   // Set cursor to the first line
  lcd.print("TEMP: ");
  lcd.print(tempC);
  lcd.print((char)223);                   // Degree symbol
  lcd.print("C");

  // Display the Fahrenheit temperature
  lcd.setCursor(0, 1);                   // Set cursor to the second line
  lcd.print("TEMP: ");
  lcd.print(tempF);
  lcd.print((char)223);                   // Degree symbol
  lcd.print("F");

  delay(1000);                           // Delay for readability
  lcd.clear();                           // Clear the display for the next update
}
