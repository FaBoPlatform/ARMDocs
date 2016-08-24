# #113 IR Receiver Brick

<center>![](/img/100_analog/product/113.jpg)
<!--COLORME-->

## Overview
フォトトランジスタを使った赤外線受信Brickです。

I/Oピンから赤外線受信のON/OFFを取得することができます。

## Connecting

アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。
![](/img/100_analog/connect/113_ir_receiver_connect.jpg)

## Parts Specification
| Document |
|:--|
| [L-51ROPT1D1](http://akizukidenshi.com/catalog/g/gI-04211/) |
| [2SC1815L-Y](http://akizukidenshi.com/catalog/g/gI-06475/) |

## Schematic
![](/img/100_analog/schematic/113_ir_receive.png)

## Sample Code

A0コネクタに赤外線受信Brick、A1コネクタにLED Brickを接続し、赤外線を受信したらLEDを発光させます。

```c
//
// FaBo Brick Sample
//
// #113 IR Receiver Brick
//

#define ir_receivePin A0
#define ledPin A1

int irState = 0;

void setup() {
  pinMode(ir_receivePin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  irState = digitalRead(ir_receivePin);

  if (irState == HIGH) {
    digitalWrite(ledPin, HIGH);
  }
  else {
    digitalWrite(ledPin, LOW);
  }

}
```

## 構成Parts
- 赤外線フォトトランジスタ

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/113_ir_receive
