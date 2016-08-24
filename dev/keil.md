ＡＲＭマイコン開発が盛んになりさまざまなツールがあります。mbed,Keil,IAR,Eclipseなどありますが、ここではKeilを使います。
開発者登録する。
http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f401re.html

![Top](../img/F401Top.png)

ST-LINK/V2ドライバダウンロード
http://www.st.com/content/st_com/ja/products/embedded-software/development-tool-software/stsw-link009.html

![SoftwareGet](../img/SoftwareGet009.png)

ST-LINK/V2ドライバインストール
![SoftwareGet007](../img/GETSoftware.png)

ST-LINK/V2のファームウェアをダウンロードする。
https://my.st.com/content/my_st_com/en/products/embedded-software/development-tool-software/stsw-link007.html

ST-LINK/V2のファームウェアをアップデートする。
![update](../img/update.png)

NecleoをUSBポートに接続する。

Keil５を入手する。
https://www.keil.com/download/product/
MDK-ARMを選択する。
![MDK-ARM](../img/MDK-ARM.png)
ユーザー登録する。
![UserReg](../img/userTmp.png)

firmwareアップグレードkeil μVersion5のダウンロード
  住所、名前などを登録してダウンロードする。
keil5を起動。ターゲットとなるデバイスを選択する。
下記のボタン（PackInstaller）を押します。
![InstallButton](../img/BoradPackInstall.jpg)

メニューバーのProjectを選択。次にSTmicroelectronics→STM32F401→STM32F401RB→STM32F401RBを選択します。
必要となるコンポーネントを選択する。
![Ｋｅｉｌ設定画面](../img/Keil_Soc_Select.jpg)

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
