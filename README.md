//ESP-on-Simulator
#include <WiFi.h>
void setup() {
  // put your setup code here, to run once:
  Serial.begin(115200);
  Serial.println("Hello, ESP32!");
  WiFi.mode(WIFI_STA);
}
void loop() {
  Serial.println("Pencarian WiFi...!");
  int networks = WiFi.scanNetworks();
  if(networks==0){Serial.println("WiFi tidak terdeteksi");}
  else
  {Serial.print(networks);
  Serial.println(" Jaringan di temukan !");
  for(int i=0; i < networks; i++)
  {
    Serial.print("Jaringan ke- ");
    Serial.print(i+1);
    Serial.print(WiFi.SSID(i));
    Serial.print(WiFi.RSSI(i));
     delay(10);
  }
  }
}
