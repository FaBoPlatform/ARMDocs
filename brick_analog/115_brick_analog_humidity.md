# #115 Humidity Brick

<center>![](/img/100_analog/product/115.jpg)
<!--COLORME-->

## Overview
湿度センサーモジュールを使用したBrickです。

温度、湿度の情報を取得することができます。

## Connecting

アナログコネクタ(A0〜A5)のいずれかに接続します。

![](/img/100_analog/connect/115_humidity_connect.jpg)


## Parts Specification
| Document |
|:--|
| [DHT11](http://akizukidenshi.com/catalog/g/gM-07003/) |

## Schematic
![](/img/100_analog/schematic/115_humidity.png)

## Sample Code
A0コネクタに接続して、湿度を計測するサンプルになります。

このサンプルコードでは外部ライブラリを使用します。

- [GitHub Library](https://github.com/adafruit/DHT-sensor-library)

![](/img/100_analog/docs/115_humidity_docs_001.png)

![](/img/100_analog/docs/115_humidity_docs_002.png)

  ライブラリ名：「DHT sensor library」

```c
//
// FaBo Brick Sample
//
// #115 Humidity Brick
//
// DHT Library Downloads
// https://github.com/adafruit/DHT-sensor-library

#include "DHT.h"
DHT dht(A0, DHT11);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {

  delay(1000);

  float h = dht.readHumidity();
  float t = dht.readTemperature();

  Serial.print("Hum: ");
  Serial.print(h);
  Serial.print(" %");
  Serial.print("  Temp: ");
  Serial.print(t);
  Serial.println(" *C");
}
```


## 構成Parts
- 湿温度センサモジュールDHT11

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/115_humidity
