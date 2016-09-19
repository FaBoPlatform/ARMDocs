# Nucleoについて

ST Microerectronics製STM32マイコンを搭載したマイコンボードです。コアにARM Cortex-Mシリーズを採用しており、消費電力にすぐれ低価格であり、すぐにプロトタイプが作れます。超ローパワーなL0シリーズから高性能モデルF７シリーズが用意され、F３シリーズ、F４シリーズはCortex-M4を採用しており高速に動作します。F４シリーズはクロック数が１８０MHzまで対応しているモデルもあり、グラフィックス機能Chrom-ART Acceleratorが搭載されているモデルもあります。Necleoには、Aruinoと同じコネクタとmorphoコネクタが搭載されているボードが用意されているモデルもあります。morphoのピンヘッダはSTM32のすべての入出力が利用可能となっています。Necleoには、デバッカ・プログラマが搭載されており別途購入する必要がありません。HALライブラリが用意されておりすぐにアプリケーションが構築することができます。

※Chrom-ART Acceleratorは、一部モデルのみです。(注意：STM32F401には搭載されておりません。)

## STM32 Nucleo

STM32 Nucleoは、Arduino互換のPinヘッダーを搭載したプロトタイピング用開発ボード。mbedにも対応している。

## STM32 Nucleo

Arduino Nano互換のPinヘッダーを搭載するNucleo-32とArduino Uno互換のPinヘッダーを搭載するNucleo-64, Arduino Mega互換のPinヘッダーを搭載するNucleo-144で構成される。


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
* [NUCLEO-F303ZE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f303ze.html)
* [NUCLEO-F446ZE](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f446ze.html)
* [NUCLEO-F207ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f207zg.html)
* [NUCLEO-F412ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f412zg.html)
* [NUCLEO-F746ZG](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f746zg.html)
* [NUCLEO-F429ZI](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f429zi.html)
* [NUCLEO-F767ZI](http://www.st.com/content/st_com/ja/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f767zi.html)
