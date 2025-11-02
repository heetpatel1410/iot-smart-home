#define BLYNK_TEMPLATE_ID "*********************"                   // Copy here to access your Blynk Account
#define BLYNK_TEMPLATE_NAME "***************** "                    // Copy here to access your Blynk Account
#define BLYNK_AUTH_TOKEN "****************************************" // Copy here to access your Blynk Account

// WiFi credentials
char ssid[] = "**********";  // Add your WiFi credentials
char pass[] = "**********";  // Add your Wifi credentials

#include <WiFi.h>
#include <BlynkSimpleEsp32.h>
#include <DHT.h>

// Define the pins for the sensors and modules
// These pins are already assigned to SST Technologies' ESP32 IoT Developement Board
#define RELAY_PIN 13
#define SMOKE_SENSOR_PIN 39    // connected to esp 32 "SN" pin...
#define DHT_PIN 32
#define DHT_TYPE DHT11          // For DHT11 sensor

DHT dht(DHT_PIN, DHT_TYPE);

BlynkTimer timer;


void sendSensorData() {

  // Reading smoke sensor
  int smokeValue = analogRead(SMOKE_SENSOR_PIN);
  Blynk.virtualWrite(V1,smokeValue);

  // Reading DHT11 sensor
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();
  Blynk.virtualWrite(V2, humidity);
  Blynk.virtualWrite(V3, temperature);

}
// Control relay
BLYNK_WRITE(V4) {
  int relayState = param.asInt();
  digitalWrite(RELAY_PIN, relayState);
}

void setup() {
  // Debug console
  Serial.begin(115200);
  
  // Setup pins
  pinMode(SMOKE_SENSOR_PIN,INPUT);
  pinMode(RELAY_PIN, OUTPUT);
  pinMode(LED_PIN, OUTPUT);
  pinMode(LDR_PIN,INPUT);
  pinMode(SOIL_PIN,INPUT);

  // Initialize the DHT sensor
  dht.begin();
  // Connect to Blynk
  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);

  // Setup a function to be called every second
  timer.setInterval(1000L, sendSensorData);
}

void loop() {
  delay(500);
  Blynk.run();
  timer.run();
}
