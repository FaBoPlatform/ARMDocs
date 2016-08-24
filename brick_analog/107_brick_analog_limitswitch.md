# #107 LimitSwitch Brick

<center>![](/img/100_analog/product/107.jpg)
<!--COLORME-->

## Overview
リミットスイッチを使ったBrickです。

I/OピンよりスイッチのON/OFFの状態を取得することができます。

機械の自動停止や位置検出の際に使用します。

## Connecting

### Arduino
アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。

![](/img/100_analog/connect/107_limitswitch_connect.jpg)

###Raspberry PI
GPIOコネクタのいずれかに接続します。

### IchigoJam
OUTコネクタのいずれかに接続します。


## Support
|Arduino|RaspberryPI|IchigoJam|
|:--:|:--:|:--:|
|◯|◯|◯|

## Schematic
![](/img/100_analog/schematic/107_limitswitch.png)

## Sample Code
A0コネクタにLimitSwitch Brickを接続し、D2コネクタに接続したLED Brickの点灯/消灯を制御しています。

```c
//
// FaBo Brick Sample
//
// #107 LimitSwitch Brick
//

#define buttonPin A0 // リミットスイッチピン
#define ledPin 2     // LEDピン

// リミットスイッチの状況取得用
int buttonState = 0;

void setup() {
  // リミットスイッチピンを入力用に設定
  pinMode(buttonPin, INPUT);
  // LEDピンを出力用に設定
  pinMode(ledPin, OUTPUT);
}

void loop(){
  // リミットスイッチの押下状況を取得
  buttonState = digitalRead(buttonPin);

  // リミットスイッチ判定
  if (buttonState == LOW) {
    // LED点灯
    digitalWrite(ledPin, HIGH);
  }
  else {
    // LED消灯
    digitalWrite(ledPin, LOW);
  }
}
```

## 構成Parts
- リミットスイッチ

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/107_limitswitch
