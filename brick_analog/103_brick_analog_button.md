# #103 Button Brick

<center>![](/img/100_analog/product/103.jpg)
<!--COLORME-->

## Overview
ボタンを使ったBrickです。I/OピンよりボタンのON/OFFの状態を取得することができます。

※ボタンカバー部分の色はランダムで送付するため色のご指定はできません。あらかじめご了承ください。

## Connecting
アナログコネクタ(A0〜A5)、またはデジタルコネクタ(2〜13)のいずれかに接続します。
![](/img/100_analog/connect/103_button_connect.jpg)

## Schematic
![](/img/100_analog/schematic/103_button.png)

## Sample Code

A1コネクタに接続したButton Brickの入力により、A0コネクタに接続したLED Brick の点灯/消灯を制御しています。
101_brick_analog_ledのソースコードを変えます。SM32CubeMXを再設定して、新たにPA1をGPIO_Inputに設定します。
```c
int main(void)
{

  /* USER CODE BEGIN 1 */

  /* USER CODE END 1 */

  /* MCU Configuration----------------------------------------------------------*/

  /* Reset of all peripherals, Initializes the Flash interface and the Systick. */
  HAL_Init();

  /* Configure the system clock */
  SystemClock_Config();

  /* Initialize all configured peripherals */
  MX_GPIO_Init();

  /* USER CODE BEGIN 2 */

  /* USER CODE END 2 */

  /* Infinite loop */
  /* USER CODE BEGIN WHILE */
  while (1)
  {
  /* USER CODE END WHILE */

  /* USER CODE BEGIN 3 */

  if(HAL_GPIO_ReadPin(GPIOA,GPIO_PIN_1)==GPIO_PIN_RESET){
    HAL_GPIO_WritePin(GPIOA,GPIO_PIN_0,GPIO_PIN_SET);
  }else{
    HAL_GPIO_WritePin(GPIOA,GPIO_PIN_0,GPIO_PIN_RESET);
  }
  /* USER CODE END 3 */


```
書き込みに成功しましたら、リセットを押します。

## 構成Parts
- 12mm角タクトスイッチ

## GitHub
- https://github.com/FaBoPlatform/FaBo/tree/master/103_button
