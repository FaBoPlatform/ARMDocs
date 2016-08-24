# #112 IR LED Brick

<center>![](/img/100_analog/product/112.jpg)
<!--COLORME-->

## Overview
赤外線LEDを使ったBrickです。

I/Oピンから赤外線LEDをON/OFFを制御することができます。

## Connecting
アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。

![](/img/100_analog/connect/112_ir_connect.jpg)

### IchigoJam
OUTコネクタのいずれかに接続します。


## Parts Specification
| Document |
|:--|
| [OSI5LA5113A](http://akizukidenshi.com/catalog/g/gI-04311/) |

## Schematic
![](/img/100_analog/schematic/112_ir_led.png)

## Sample Code
### for Arduino
A0コネクタに赤外線LED Brick、A1コネクタにボタンBrickを接続し、ボタンが押されたら赤外線LEDを発光させます。
```c
//
// FaBo Brick Sample
//
// #112 IR LED Brick
//

#define ir_ledPin A0
#define buttonPin A1

int buttonState = 0;

void setup() {
  pinMode(ir_ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {
    digitalWrite(ir_ledPin, HIGH);
  }
  else {
    digitalWrite(ir_ledPin, LOW);
  }

}
```

## 構成Parts
- 5mm 赤外線LED OSI5LA5113A

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/112_ir_led
