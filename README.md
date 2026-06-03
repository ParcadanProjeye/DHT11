#include <Wire.h>

#include <FaBoLCD_PCF8574.h>

#include <DHT.h>

#include <DHT_U.h>

#define DHTPIN 2

#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

FaBoLCD_PCF8574 lcd;




void setup() {


lcd.begin(16,2);

dht.begin();



}



void loop() {
  
  int temp = dht.readTemperature();
  
  int hum = dht.readHumidity();

  lcd.setCursor(0,0);
  
  lcd.print("SICAKLIK: ");
  
  lcd.print(temp);
  
  lcd.print(" C");


  lcd.setCursor(0,1);
  
  lcd.print("NEM: %");
  
  lcd.print(hum);


  delay(2000);


}
