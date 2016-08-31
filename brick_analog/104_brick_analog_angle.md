# #104 Angle Brick

<center>![](../img/Angle104/104.jpg)
<!--COLORME-->

## Overview
ボリューム抵抗を使ったBrickです。

I/Oピンからアナログ値を取得することができます。

LED Brickの明るさを調節する際などに使用します。

## Connecting

アナログコネクタ(A0〜A5)のいずれかに接続します。

![](/img/100_analog/connect/104_angle_connect.jpg)

## Schematic
![](/img/100_analog/schematic/104_angle.png)

## Sample Code

A1コネクタにAngleを接続して、A1コネクタに接続したLED Brickをつなぎ、LEDの点灯間隔の時間をボリュームをかえることによって変化させます。

STM32CubeMXを起動し、ADC,USART2,GPIOを設定します。また、パソコンのターミナルから変化量が見れます。
![](../img/Angle104/PinOutConf.png)

コンフィグレーションボタンを押して、次の画面が出てきたら、ADCを選びます。
![](../img/Angle104/ADCSELECT.png)
![](../img/Angle104/ADCConf.png)

NVICボタンを押します。
![](../img/Angle104/ADC_NVIC.png)

GPIOボタンを押します。
![](../img/Angle104/PinOutCof.png)

CodeGrenarateします。

Keilを立ち上げ、main.cファイルに以下のコードを追記します。

コードの一部（抜粋）

```c
/* Includes ------------------------------------------------------------------*/
#include "stm32f4xx_hal.h"

/* USER CODE BEGIN Includes */
#include <stdio.h>
#include <string.h>
/* USER CODE END Includes */
```

```c
/* Private variables ---------------------------------------------------------*/

int value=0;

/* USER CODE END PV */
```

```c
/* USER CODE BEGIN PFP */
/* Private function prototypes -----------------------------------------------*/

char adcFlag=0;
void HAL_ADC_ConvCpltCallback(ADC_HandleTypeDef* hadc)
{
	value=HAL_ADC_GetValue(hadc);
	adcFlag =1;
}

```

```c
int main(void)
{

  /* USER CODE BEGIN 1 */

		char buffer[16];

  /* USER CODE END 1 */

  /* MCU Configuration----------------------------------------------------------*/

  /* Reset of all peripherals, Initializes the Flash interface and the Systick. */
  HAL_Init();

  /* Configure the system clock */
  SystemClock_Config();

  /* Initialize all configured peripherals */
  MX_GPIO_Init();
  MX_ADC1_Init();
  MX_USART2_UART_Init();

  /* USER CODE BEGIN 2 */

	adcFlag=0;
  HAL_ADC_Start_IT(&hadc1);

  /* USER CODE END 2 */

  /* Infinite loop */
  /* USER CODE BEGIN WHILE */
  while (1)
  {
		while(adcFlag != 0);
		sprintf(buffer,"%dms\n\r",value);
		HAL_UART_Transmit(&huart2,(uint8_t*)buffer,strlen(buffer),0x1111);
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_0,GPIO_PIN_SET);
		HAL_Delay(100);
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_0,GPIO_PIN_RESET);
		HAL_Delay(value);
		adcFlag=0;
		HAL_ADC_Start_IT(&hadc1);	  
  /* USER CODE END WHILE */

  /* USER CODE BEGIN 3 */

  }
  /* USER CODE END 3 */

}


```


## 構成Parts
- ボリューム抵抗器A 10k

## GitHub
