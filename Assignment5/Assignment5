#define LILYGO_WATCH_2019_WITH_TOUCH
#include <LilyGoWatch.h>
TTGOClass *ttgo;

#include <SimpleDHT.h>

#include <WiFi.h>
#include <HTTPClient.h>

const char* ssid = "";
const char* password = "";

// Your Domain name with URL path or IP address with path
const char* serverName = "http://192.168.0.195:1234/setValue";

unsigned long lastTime = 0;
unsigned long timerDelay = 5000;  // Time interval in milliseconds

String response;

int pinDHT11 = 21;
SimpleDHT11 dht11;

String httpGETRequest(const char* serverName) {
  HTTPClient http;
  
  http.begin(serverName);
  
  int httpResponseCode = http.GET();
  
  String payload = "{}"; 
  
  if (httpResponseCode > 0) {
    Serial.print("HTTP Response code: ");
    Serial.println(httpResponseCode);
    payload = http.getString();
  }
  else {
    Serial.print("Error code: ");
    Serial.println(httpResponseCode);
  }
  
  http.end();

  return payload;
}

void setup() {
  Serial.begin(115200);
  ttgo = TTGOClass::getWatch();
  ttgo->begin();
  ttgo->openBL();
  
  ttgo->tft->fillScreen(TFT_BLACK);
  ttgo->tft->setTextColor(TFT_WHITE, TFT_BLACK);
  ttgo->tft->setTextFont(4);
  
  WiFi.begin(ssid, password);
  Serial.println("Connecting");
  
  while(WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  
  Serial.println("");
  Serial.print("Connected to WiFi network with IP Address: ");
  Serial.println(WiFi.localIP());
  
  Serial.println("Timer set to 5 seconds (timerDelay variable), it will take 5 seconds before publishing the first reading.");
}

void loop() {
  unsigned long currentTime = millis();
  
  // Check if 5 seconds have passed since the last reading
  if (currentTime - lastTime >= timerDelay) {
    lastTime = currentTime;  // Update the lastTime
    
    Serial.println("=================================");
    Serial.println("Sample DHT11...");
    
    byte temperature = 0;
    byte humidity = 0;
    int err = SimpleDHTErrSuccess;
    
    if ((err = dht11.read(&temperature, &humidity, NULL)) != SimpleDHTErrSuccess) {
      Serial.print("Read DHT11 failed, err=");
      Serial.println(err);
      delay(1000);
      return;
    }
    
    Serial.print("Sample OK: ");
    Serial.print(String((float)temperature) + "* C, ");
    Serial.println(String((float)humidity) + "% H");
    
    ttgo->tft->drawString(String((int)temperature*1.8 + 32) + " *F",  5, 10);
    ttgo->tft->drawString(String(humidity) + " % H",  5, 40);
    
    int t = (int)temperature;
    int h = (int)humidity;
    String url = String(serverName) + "?t=" + t + "&h=" + h;
    Serial.println(url);       
    response = httpGETRequest(url.c_str());
    Serial.println(response);
  }
}

