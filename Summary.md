#include <dht.h>

#define DHTPIN 2
#define DHTTYPE DHT11

dht DHT;

int digit1 = 3;
int digit2 = 4;
int digit3 = 5;
int digit4 = 6;

void setup() {
  pinMode(digit1, OUTPUT);
  pinMode(digit2, OUTPUT);
  pinMode(digit3, OUTPUT);
  pinMode(digit4, OUTPUT);
}

void loop() {
  int chk = DHT.read11(DHTPIN);
  float fahrenheit = (DHT.temperature * 1.8) + 32;

  int digits[4] = {
    (int)fahrenheit / 1000 % 10,
    (int)fahrenheit / 100 % 10,
    (int)fahrenheit / 10 % 10,
    (int)fahrenheit % 10
  };

  digitalWrite(digit1, LOW);
