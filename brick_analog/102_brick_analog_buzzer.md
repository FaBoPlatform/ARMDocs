# #102 Buzzer Brick

<center>![](/img/100_analog/product/102.jpg)
<!--COLORME-->

## Overview
圧電ブザーを使ったBrickです。I/Oピンより、鳴らす音や音の長さを制御することができます。

## Connecting
アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。今回はD13にBuzzer Brickを、A0には、Angle Brickをつないでください。

![](/img/100_analog/connect/102_buzzer_connect.jpg)

## Schematic
![](/img/100_analog/schematic/102_buzzer.png)

## Sample Code
###PWMによる出力
D12コネクタにBuzzer Brickを接続し、ビープ音を鳴らしています。#104 Angle Brickを使うことにより周波数をかえることができます。
音の波形は矩形波でPWM出力します。マイコンが高速にスイッチングすることにより、特別なコンバータを使わずに周波数や波長が変えやすくモーター制御などによく使われます。highとlowの割合をディーティー比といいます。

PWM出力するためにはTIM(タイマー)を使用します。PWMの周波数は、タイマーつまり、マイコンのクロック周波数に依存します。この周波数をPPL回路やプリスケーラなどで加工してタイマーの周波数に使用します。

STM32CubeMXを起動します。Pinout設定で、USART2,ADC1,TIM3を設定します。
クロックの設定画面です。ここでは今回は変更はしません。
ADC設定画面です。チェックインします。
TIM3の設定画面で分周する値を決めます。highとLowが等しいディーティー比５０％の128と数値を入力します。

Generatecordeを選択します。すると自動的に初期のコードが生成されます。

maic.cのソースコード抜粋
```c
/* Includes ------------------------------------------------------------------*/
#include "stm32f4xx_hal.h"

/* USER CODE BEGIN Includes */


#include <stdio.h>
#include <string.h>

/* USER CODE END Includes */

/* Private variables ---------------------------------------------------------*/
ADC_HandleTypeDef hadc1;

TIM_HandleTypeDef htim3;

UART_HandleTypeDef huart2;

/* USER CODE BEGIN PV */
/* Private variables ---------------------------------------------------------*/

int a_Value,adc_fin=0;
```

```c
```


<br>
数値が大きくなるほど音が高くなります。

| | ド | ド♯ | レ | レ♯ | ミ | ファ | ファ♯ | ソ | ソ♯ | ラ | ラ♯ | シ |
|  -- | -- |-- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
|  1 | 131 | 139 | 147 | 156 | 165 | 175 | 185 | 196 | 208 | 220 | 233 | 247 |
| 2 | 262 | 277 | 294 | 311 | 330 | 349 | 370 | 392 | 415 | 440 | 466 | 494 |
 | 3 | 523 | 554 | 587 | 622 | 659 | 698 | 740 | 784 | 831 | 880 | 932 | 988 |

その他の音階については下記をご参照下さい。

https://www.arduino.cc/en/Tutorial/ToneMelody?from=Tutorial.Tone

## 構成Parts
- 圧電ブザー

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/102_buzzer
