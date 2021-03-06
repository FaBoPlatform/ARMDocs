#Keil
##豊富な統合開発環境IDE

ARM開発するに必要なソフトウェアは、エディタ、コンパイラ、デバッカ、シュミレータなど複数必要ですが、IDE（統合開発環境）を使えば１つにまとまったソフトウェアとして提供されています。ARMマイコンを使用した開発が盛んになり開発環境もmbed,Keil,IAR,GCC利用のEclipseなどいくつかの選択肢がありますが、今回はARM社が開発したコンパイラが利用できるKeilで開発環境を構築します。オープンソースのeclipseなどは、コンパイラなども別にインストールし組み合わせて使用する必要がありますが、keilだけでコンパイル、書き込み可能で、コンポーネントなどインストールも簡単におこなえます。しかも、実行速度が速いARM社の純正コンパイラとなります。特徴として、mbedと異なりハードウェアに直接プログラミングでき、性能の追及やコードサイズがコンパクトになるベアメタルで開発可能となります。よってＯＳがない状態で実行します。したがって、デバイスドライバ、ライブラリを使い、割り込み処理などはコードを記述しないてはいけません。しかしながら、Keilを使えば、コンポーネントをインストールするのには、とても分かりやすくなっております。

###動作環境
Keilの動作環境は、現在、Windowsが必須となります。keilの無償版は32KBのコード制限があります。しかしながら、機能が単純な場合は十分な容量といえます。


流れとしては、ドライバをインストール→Keilのインストール→ターゲットとなるボードの設定→必要なコンポーネントをインストール→書き込みの設定となります。

###主な開発環境

| 開発元 | パッケージ名 | |
|:--|:--|:--|
| IAR | EWARM |IARシステムズ　評価版は３２Ｋコードサイズ期限なし制限版と３０日期限あり|
| Keil | MDK |ARM社の純正コンパイラ　評価版はIARとほぼ同じ制限|
| Atolic | TrueStudio |Eclipseを基にした製品　評価版は制限なし|
| Rowley | CrossWorks ||
| Embest | CooCox ||
| Segger | emIDE |J-linkを使う場合|
| Code Red | RedSuite ||
| Raisonancec | Ride ||
| Altium | Tasking ||
| Cosmic | Idea | |


他多数


##インストールの準備、デバッカについて
開発者登録する。
http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f401re.html

![Top](../img/F401Top.png)

###デバック方法

STM32には開発にはいくつか豊富があります。JTAG並びにSWDを使った方法、USBを使うのも、UARTを使用するのものです。ここではデバックに優れているSWDを紹介します。

通常、ARM開発には、Keilなどの開発用ソフトウェア以外にも、ターゲットとなるCPUを制御してボードのメモリにファームウェアをダウンロードするJTAGエミュレータが必要になります。ARM開発において、JTAGエミュレータ（デバッガ,プログラミングツール）は約５万円～数十万円J-linkシリーズやUlink（使用するマイコンやIDEによって必要とされるものは変わります）などよく使われますが、Necleoは、ファームウェアを書き込む（ダウンロード）ST-LINKデバッガ（ICE）を搭載済みで完成したら切り離すことが可能になっており、別途購入不要です。また、別売りのプログラマも安価に販売されています。ST-LinkとターゲットとなるマイコンはSWD(SerialWireDebug)インターフェースで接続されている。JTAG５本線の信号線が必要ですが、省スペース化に対応したSWDは、信号線最低限２本(SWCLK,SWDIO)でボードにダウンロード可能です。信号線の他には電源とグランドとなる。JTAGとSWDどちらもプログラムの書き換え、マイコン内の（プログラムの進行状況、変数の状態）を確認することできる。

##JTAG　
４本から５本必要。工場などで基板を検査する規格がデバックにつかわれるようになった。
MCUを検査するバウンダリングスキャンが可能でデイジーチェーンにより複数台同時接続が可能。

| pin |  |
|:--|:--|
| TCK | クロック信号 |
| TMS | モードセレクト |
| NRST | リセット |
| TDI | データ入力 |
| TDO | データ出力 |

##SWD
JTAGをシンプルにしてデバックに特化している。少なくても２本(SWCLK,SWDIO)必要。トレース機能を利用したい場合はSWOを追加します。

| pin |  |
|:--|:--|
| SWCLK | クロック信号 |
| SWDIO | データ |
| NRST | リセット |
| SWO | データ出力（オプション） |

##ST-LINKドライバーインストール
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

##Keilをインストール

keil μVersion5のダウンロード
https://www.keil.com/download/product/

MDK-ARMを選択する。（KeilにはARM以外のマイコンにもいつくか対応している。）
![MDK-ARM](../img/MDK-ARM.png)

ユーザー登録する。 住所、名前などを登録してダウンロードする。
![UserReg](../img/userTmp.png)

keil5を起動。ターゲットとなるデバイスを選択する。
下記のボタン（PackInstaller）を押します。
![InstallButton](../img/BoradPackInstall.jpg)

メニューバーのProjectを選択。次にターゲットを選択しSTmicroelectronics→STM32F401→STM32F401RB→STM32F401RBを選択します。
必要となるPackを選択（Install）する。
![Ｋｅｉｌ設定画面](../img/Keil_Soc_Select.jpg)

参考 ARM KEIL Board Support
file:///C:/Keil_v5/ARM/PACK/Keil/MDK-Middleware/7.0.0/Doc/Board/html/index.html
CMSIS-CORE
ＡＲＭコアはさまざまなメーカーに搭載されていますが、ソフトウェアは各社相違があったのですがARM社が定義した共通規格です。各社ペリフェラルなどは、各社でレジスタを定義していたのですが、CMSISの中のCOREは、ARMコアとつながるペリフェラルにたいしてレジスタを定義しております。
参考　CMSIS-CORE
file:///C:/Keil_v5/ARM/PACK/ARM/CMSIS/5.0.0-Beta4/CMSIS/Documentation/Core/html/index.html
参考　CMSISの説明
http://www.arm.com/ja/products/processors/cortex-m/cortex-microcontroller-software-interface-standard.php
CMSIS-DAP
CMSIS-DAPは、ARM社が提唱するデバッカの定義。
CMSIS-PACKは、CORE,DAP,DSP,SVDなど各ライブラリをまとめたパッケージです。

![InstallButton](../img/ManegerInstallButton.png)

上のBoardsタブを押して、その下のNUCLEO-F401RE（Rev.C）の下DevicesのSTM32F401RBを選択、左にある任意のInstallボタンします。
![DownloadButton](../img/BoardDownload.jpg)

下記の示すOptionForTargetボタンを押します。
同じARMのコアですが、それ以外は異なるのでメーカーによって設定が必要になります。
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
