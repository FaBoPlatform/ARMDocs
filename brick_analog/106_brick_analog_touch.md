# #106 Touch Brick
<center>![](/img/100_analog/product/106.jpg)
<!--COLORME-->

## Overview
感圧センサーを使用したタッチセンサーBrickです。
I/Oピンより、感圧部分に加えられた力の大きさの変化をアナログ値で取得することができます。

## Connecting

アナログコネクタ(A0〜A5)のいずれかに接続します。

![](/img/100_analog/connect/106_touch_connect.jpg)

## Datasheet
| Document |
|:--|
| [Datasheet](http://interlinkelectronics.com/datasheets/Datasheet_FSR.pdf) |

## Schematic
![](/img/100_analog/schematic/106_touch.png)

## Sample Code

A0コネクタに接続したTouch Brickの感圧によって、D2コネクタに接続したLED Brickを点灯/消灯させています。

```c
//
// FaBo Brick Sample
//
// #106 Touch Brick
//

#define buttonPin A0
#define ledPin 2

int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop(){

  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {
    digitalWrite(ledPin, LOW);
  }
  else {
    digitalWrite(ledPin, HIGH);
  }
}
```

## 構成Parts
- 感圧センサー

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/106_touch
