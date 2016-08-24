# #101 LED Brick

<center>![](/img/100_analog/product/101.jpg)
<!--COLORME-->

## Overview
LEDのBrickです。発光色は5色（青・緑・赤・白・黄）あります。Lチカのおともにもどうぞ。

※購入時は色の間違いにご注意ください。

## Connecting
アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。

![](/img/100_analog/connect/101_led_connect.jpg)

## Schematic
![](/img/100_analog/schematic/101_led.png)

## Sample Code
D2コネクタにLED Brickを接続し、一定時間(1秒=1000ms)ごとに点灯/消灯（Lチカ）させています。

```c
//
// FaBo Brick Sample
//
// #101 LED Brick
//

#define ledPin 2 // LEDピン

void setup() {
  // LED接続ピンを出力に設定
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // LEDを一定時間で点滅
  digitalWrite(ledPin, HIGH);
  delay(1000);
  digitalWrite(ledPin, LOW);
  delay(1000);
}
```

## 構成パーツParts
- 5mm LED(各色)

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/101_led
