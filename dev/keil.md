ＡＲＭマイコンを仕様した開発が盛んになり開発環境もmbed,Keil,IAR,GCC利用のEclipseなどいくつかの選択肢がありますが、今回はkeilで開発環境を構築します。mbedと異なりハードウェアに直接プログラミングでき、コードサイズがコンパクトになるベアメタルとなります。
流れとしては、ドライバをインストール→Keilのインストール→ターゲットとなるボードの設定→必要なコンポーネントをインストール→書き込みの設定となります。
NUCLEO-F401RE導入の場合
  主なスペック
    Nucleo type:Nucleo64(High-performance)
    MCU:STM32F401RET6(ARM 32bit Cortex-M4)
    MCU pin:64
    Flash:512KB
    RAM:96KB
    Interface:SPI,I2S,I2C,USART,USB-OTG,SDIO
    GPIO:50
    Connectors(Arduino UNO Rev3,ST morpho)

開発者登録する。
http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f401re.html

![Top](../img/F401Top.png)



ST-LINK/V2ドライバダウンロード

http://www.st.com/content/st_com/ja/products/embedded-software/development-tool-software/stsw-link009.html

![SoftwareGet](../img/SoftwareGet009.png)

ST-LINK/V2ドライバインストール

ST-LINK/V2のファームウェアをダウンロードする。
https://my.st.com/content/my_st_com/en/products/embedded-software/development-tool-software/stsw-link007.html


![SoftwareGet007](../img/GETSoftware.png)


ST-LINK/V2のファームウェアをアップデートする。
![update](../img/update.png)

NecleoをUSBポートに接続する。

keil μVersion5のダウンロード
https://www.keil.com/download/product/

MDK-ARMを選択する。
![MDK-ARM](../img/MDK-ARM.png)

keil5を起動。ターゲットとなるデバイスを選択する。
下記のボタン（PackInstaller）を押します。
![InstallButton](../img/BoradPackInstall.jpg)

メニューバーのProjectを選択。次にSTmicroelectronics→STM32F401→STM32F401RB→STM32F401RBを選択します。
必要となるコンポーネントを選択する。
![Ｋｅｉｌ設定画面](../img/Keil_Soc_Select.jpg)

参考 ARM KEIL Board Support
file:///C:/Keil_v5/ARM/PACK/Keil/MDK-Middleware/7.0.0/Doc/Board/html/index.html
参考　CMSIS-CORE
file:///C:/Keil_v5/ARM/PACK/ARM/CMSIS/5.0.0-Beta4/CMSIS/Documentation/Core/html/index.html


ユーザー登録する。 住所、名前などを登録してダウンロードする。
![UserReg](../img/userTmp.png)

![InstallButton](../img/ManegerInstallButton.png)

上のBoardsタブを押して、その下のNUCLEO-F401RE（Rev.C）の下DevicesのSTM32F401RBを選択、左にある任意のInstallボタンします。
![DownloadButton](../img/BoardDownload.jpg)

下記の示すOptionForTargetボタンを押します。
![OptionForTargetButton](../img/OptionForTarget.png)


Targetタブをクリックし下記の通りに振動数、アドレス設定します。
![TargetConf](../img/TargetPhoto.png)


Debugタブを押して、ST-Link Debuggerを選択。
![DebugerPhoto](../img/DebugerPhoto.png)


下記の設定になっているか確認してください。相違があれば変更してください。
![Trace](../img/Trace.png)


Flashタブを押して、下記の設定にしてください。ProgramingAlgorithmが下記と相違する場合は、必要に応じてAdd,Removeボタンで変更してください。
![FlashDownload](../img/FlashDownload.png)


上記でAdd,Removeボタンを押すと、下記の画面が出ます。下の画面のように選択してAddボタンを押してください。
![ProgramingAlgorithm](../img/ProgramingAlgorithm.png)
