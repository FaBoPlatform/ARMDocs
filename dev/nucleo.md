# Nucleoについて

スイスのジュネーブに本社があるST Microerectronics製STM32マイコンを搭載したARMコアであり、省電力、コストにすぐれたCortex-Mシリーズを採用したマイコンボードです。世界には３２ビットのＡＲＭコアを採用したＭＣＵは多数ありますが、その中の一つのです。はじめから３２ビットで設計されており、設計が古いマイコンとくらべ、アドレス空間が広く大きなメモリも扱いやすくメモリ増設も比較的簡単にでき、チップも小さく作れ、低コストで製造できます。STM32シリーズは、品質、入手性にもすぐれ、ボードも非常に安く購入できます。これまでは、STM32を採用したDiscoveryシリーズがありましたが、あくまでもマイコンの評価として存在していましたが、メーカーズ向けにプロトタイプを作る目的として、目的に合わせた豊富なモデル構成、mbedができる安価なボードとして、Necleoとして発売されました。コアにARM Cortex-Mシリーズを採用しており、消費電力にすぐれ低価格であり、すぐにプロトタイプが作れます。超ローパワーなL0シリーズから高性能モデルF７シリーズが用意され、F３シリーズ、F４シリーズはCortex-M4を採用しており高速に動き、マイコンとしては大容量SRAM、浮動小数計算FPU（一部モデル）も搭載しております。F４シリーズはクロック数が１８０MHzまで対応しているモデルもあり、年々、高速化しております。高速化にともないプログラムメモリ（フラッシュメモリから読み出し）にも高速化が求められます。そこで考え出されたのはＡＲＴアクセラレーターという１２８ビットのバッファメモリをフラッシュメモリとコアの間に設けています。したがって、内蔵Flashメモリからのゼロ・ウエイトを実現しています。そのほかにも、グラフィックス機能Chrom-ART Acceleratorが搭載されているモデルもあります。Necleoには、Aruinoと同じコネクタとmorphoコネクタが搭載されているボードが用意されているモデルもあります。morphoのピンヘッダはSTM32のすべての入出力が利用可能となっています。Necleoには、デバッカ・プログラマが搭載されており別途購入する必要がありません。なんといっても、Ｃ言語での開発はもちろんのこと、HALライブラリが用意されておりすぐにアプリケーションが構築することができます。

※Chrom-ART Acceleratorは、一部モデルのみです。(注意：本サイトで扱うSTM32F401,STM32F446には搭載されておりません。)

## STM32 Nucleoの特徴

STM32 Nucleoは、Arduino互換のPinヘッダーを搭載したプロトタイピング用開発ボード。mbedにも対応している。

## STM32 Nucleoの種類

Arduino Nano互換のPinヘッダーを搭載するNucleo-32とArduino Uno互換のPinヘッダーを搭載するNucleo-64, Arduino Mega互換のPinヘッダーを搭載するNucleo-144で構成される。

##Necleoのラインナップ
様々な要求を考慮し、Necleoには、動作速度はもちろんのこと、大きさ、パッケージ（LQFP,BGA,WLCSPなど）、価格、性能（メモリ、演算の能力、ピンの数、インターフェースの種類（UBS host,i2C,Ethernet,CAN,カメラインターフェース）有無）、消費電力、機能（暗号化処理、３相モータ用タイマ）有無,動作電圧などさまざまな要素により、いろいろなタイプが用意されております。

ＳＴＭ３２Ｌ０シリーズ　低消費電力重視
ＳＴＭ３２Ｆ０         ローコスト(動作周波数48MHz)
ＳＴＭ３２Ｆ１         汎用マイコン（動作周波数24MHz~72MHz,RAM4KB~96KB)
ＳＴＭ３２Ｆ２         汎用マイコン(動作周波数120MHz　STM32F1の上位機種)
ＳＴＭ３２Ｆ３         高機能マイコン(高解像度16bitのデルタΣA-Dコンバータ搭載モデルあり)
ＳＴＭ３２Ｆ４         ハイエンドマイコン(動作周波数 80MHZ~180MHz RAM:32KB~384KB)
ＳＴＭ３２Ｆ７         ハイエンドマイコン（プロセッサー並みの性能：最高動作周波数216MHz RAM512KB,320KB,画像処理回路モデルあり）

例：ＳＴＭ３２Ｆ４４６ＲＥ６を意味する型番（命名規則）

はじめの
ＳＴＭ３２は、ARMコア採用Cortex-M4採用という意味しております。
次のＦは、汎用マイコン。

そのあとに続く数字は４４６であり、ハイエンドということを意味しております。
０＊＊　エントリー（CortexM0など）
１＊＊、３＊＊　ミッド(CortexM3,M4など)
２＊＊、４＊＊、７＊＊　ハイエンド(CortexM4,M7など)

次の英数文字Ｒは、６４Pinのピンが出ております。
次のＥは、プログラムメモリサイズ（フラッシュメモリ）５１２ＫＢです。
最後の数字６は、動作温度範囲を表しております。
－４０℃から８５℃

最適なモデルを選びましょう。

###スペックを確認
今回使用するボードの主なスペックです。ここでは、コストパフォーマンスにすぐれたNUCLEO-F401RE,NUCLEO-F446REを取り上げています。

###NUCLEO-F401RE

Nucleo type:Nucleo64(High-performance)

MCU:STM32F401RET6(ARM 32bit Cortex-M4)

MCU pin:64

Flash:512KB

RAM:96KB

Interface:SPI(3),I2S,I2C,USART(3),USB-OTG,SDIO(Secure Digital I/O)

WDT(2),ADC(12bit/10ch),RTC(Real Time Clock),TIM

GPIO:50

Connectors(Arduino UNO Rev3,ST morpho)

参考サイト

NUCLEOラインナップ

http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo.html?querycriteria=productId=LN1847

NUCLEO-F401REのドキュメント

http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f401re.html

NUCLEO-F446REのドキュメント

http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f446re.html

ARMマイコンのテクニカルドキュメント

http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.ddi0363fj/I43478.html



### Nucleo-32
* [NUCLEO-L011K4](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l011k4.html)
* [NUCLEO-F042K6](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f042k6.html)
* [NUCLEO-F031K6](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f031k6.html)
* [NUCLEO-L031K6](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l031k6.html)
* [NUCLEO-F303K8](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f303k8.html)
* [NUCLEO-L432KC](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l432kc.html)

## Nucleo-64
* [NUCLEO-F030R](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f030r8.html)
* [NUCLEO-F302R8](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f302r8.html)
* [NUCLEO-F334R8](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f334r8.html)
* [NUCLEO-L053R8](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l053r8.html)
* [NUCLEO-F070RB](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f070rb.html)
* [NUCLEO-F072RB](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f072rb.html)
* [NUCLEO-F103RB](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f103rb.html)
* [NUCLEO-F410RB](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f410rb.html)
* [NUCLEO-L073RZ](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l073rz.html)
* [NUCLEO-F091RC](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f091rc.html)
* [NUCLEO-F303RE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f303re.html)
* [NUCLEO-L152RE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l152re.html)
* [NUCLEO-F401RE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f401re.html)
* [NUCLEO-F411RE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f411re.html)
* [NUCLEO-F446RE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f446re.html)
* [NUCLEO-L476RG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-l476rg.html)

## Nucleo-144
*
STM32F7***の一部のモデルはＪＰＥＧの映像処理を行うデコーダー、エンコーダーを行う専用回路が搭載されてモデルもあります。
 [NUCLEO-F303ZE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f303ze.html)
* [NUCLEO-F446ZE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f446ze.html)
* [NUCLEO-F207ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f207zg.html)
* [NUCLEO-F412ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f412zg.html)
* [NUCLEO-F746ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f746zg.html)
* [NUCLEO-F429ZI](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f429zi.html)
* [NUCLEO-F767ZI](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f767zi.html)
