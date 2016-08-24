# #116 Distance Brick

<center>![](/img/100_analog/product/116.jpg)
<!--COLORME-->

## Overview
距離センサーモジュールを使用したBrickです。

I/Oピンより距離センサーの正面についているレンズから物体までの距離をアナログ値(0〜1023)で取得することができます。

測定可能な距離は10〜80cmとなっています。

## Connecting

アナログコネクタ(A0〜A5)のいずれかに接続します。
![](/img/100_analog/connect/116_distance_connect.jpg)


## GP2Y0A21YK Datasheet
| Document |
| -- |
| [GP2Y0A21YK Datasheet](http://www.sharpsma.com/webfm_send/1208) |

## Sample Code

A0コネクタに接続して、距離を計測します。

```c
//
// FaBo Brick Sample
//
// #116 Distance Brick
//

#define distancePin A0 // 距離センサーピン

int distanceValue = 0;

void setup() {
  // 距離センサーピンを入力用に設定
  pinMode(distancePin, INPUT);
  // シリアル開始 転送レート：9600bps
  Serial.begin(9600);
}

void loop() {
  // センサーより値を取得(0〜1023)
  distanceValue = analogRead(distancePin);

  // 取得した値を電圧に変換 (0〜5000mV)
  distanceValue = map(distanceValue, 0, 1023, 0, 5000);

  // 変換した電圧を3200(3.2v)〜500(0.5v)の値に変換後、距離に変換 (10〜80cm)
  distanceValue = map(distanceValue, 3200, 500, 5, 80);

  // 算出した距離を出力
  Serial.println(distanceValue);

  delay(100);
}
```

## 構成Parts
- 距離センサーモジュール GP2Y0A21YK

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/116_distance
