#ARMについて
私たちのみのまわりには、近年、いつのまにかＡＲＭだらけになっています。イギリスに本拠地を置くARMは工場を持たず半導体を製造していません。世界の半導体メーカーに半導体の設計や仕様（アーキテクチャー）を売っている会社です。その設計図を基に各半導体メーカー（STmicroelectronics、NXP,サムスン、Allwinner,ルネサス,富士通など）はライセンスを受け、独自のペリフェラル(メモリ、インターフェースなど)を実装し製造販売をしています。コスト性が重視される組み込みでは汎用マイコンといえば８ビットや１６ビットであり、かつては主流でしたが、USBやイーサーネットなどの普及により大容量のデータを扱う要求が増え、ARMの需要が高まりました。古くから、ＡＲＭ社は将来を見据え、初めから３２ビットRISC構造を採用し、8ビットや１６ビットマイコンと比べすっきりした構造となっております。64ビット版も登場しております。現在では、ありとあらゆる家電、スマートフォン、電子デバイスに採用されています。

ＡＲＭアーキテクチャのバージョン
ＡＲＭｖ４　ＡＲＭ７で使用
ＡＲＭｖ５　ＡＲＭ９で使用
http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.ddi0100i/index.html
ＡＲＭｖ６　ＡＲＭ１１で使用
http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.dui0348bj/CJAGACAD.html
ＡＲＭｖ７　ＣｏｒｔｅｘーＡ、ＣｏｒｔｅｘーＲで使用
https://www.arm.com/ja/products/processors/classic/arm7/index.php
ＡＲＭｖ８　Ｃｏｒｔｅｘ－Ａで使用
https://www.arm.com/ja/products/processors/instruction-set-architectures/armv8-architecture.php

以下をファミリー名として用途によって分類されます。
クラシックプロセッサ
ARM7
https://www.arm.com/ja/products/processors/classic/arm7/index.php
ARM9
https://www.arm.com/ja/products/processors/classic/arm9/index.php
ARM11
https://www.arm.com/ja/products/processors/classic/arm11/index.php
ＡＲＭ７，ＡＲＭ９、ＡＲＭ１１シリーズは、以下のCortexシリーズに再編されました。
Cortexシリーズ（ワンチップマイコン）であり、コア、メモリ（SRAM,フラッシュメモリ）、周辺回路は、基本的には１つのチップ内にすべて格納されております。
Cortex-Mシリーズ　マイクロコントローラ　安い、省電力、基本的にはＯＳなしでの環境を想定（無線モジュールなど）
https://www.arm.com/products/processors/cortex-m
Cortex-Rシリーズ　リアルタイム重視マイコン（自動車、産業機械など）
https://www.arm.com/products/processors/cortex-r
Cortex-Aシリーズ　アプリケーション用高性能マイコン　マルチタスクを実現（スマートフォン、タブレットＰＣ、ゲーム機、ラズベリーパイ２、３などに採用）
https://www.arm.com/products/processors/cortex-a

#CortexM4について
CortexM4は、従来の製品にＤＳＰ機能追加。さらに、CortexM4Ｆは浮動小数点演算回路と追加しております。
Ｃｏｒｔｅｘシリーズ　テクニカルリファレンスマニュアル
http://infocenter.arm.com/help/topic/com.arm.doc.ddi0439cj/DDI0439CJ_cortex_m4_r0p1_trm_ja-JP.pdf#search=%27CortexM+%E5%91%BD%E4%BB%A4%E3%82%BB%E3%83%83%E3%83%88+map%27
Cortex-Mの命令セットは、Thumb-2命令セット（１６ビットまたは、３２ビット）です。Thumb－２コアは、Thumb命令１６ビットに３２ビットを追加したものです。Cortex-Mシリーズ以外のマイコンには、ARMにはARM命令とThumb命令があり、ＡＲＭ命令は３２ビットで１命令を行いメモリを大量に消費していましたが、機能を削減し、Thumb命令は、１６ビットで１命令を行うようになり改善されましたが、値の制約があります。また、互換性を保つため、ARM内部では16ビットから32ビットに変換されます。

# STM32F446のアーキテクチャ
STM32F446の[blockdiagram](http://www.st.com/content/ccc/resource/technical/document/datasheet/65/cb/75/50/53/d6/48/24/DM00141306.pdf/files/DM00141306.pdf/jcr:content/translations/en.DM00141306.pdf)１６ページを見てみましょう。
ここで扱うSTM32F4はハーバードアーキテクチャを採用しております。他のマイコン同様、データと命令はバスがそれぞれ独立しております。コアとなるARM CotexM4に3つのバスが接続されています。Iバス、Dバス、Ｓバスです。

Ｉバス（命令バス）
Ｄバス（データバス）
Ｓバス（システムバス）

上記の３つのバスは、ＡＨＢバスマトリックス７Ｓ８Ｍ(７スレーブ（ｓ０～ｓ６）、８マスター（ｍ０～ｍ７）)につながっております。
このＡＨＢバスはマスター（ＡＲＭ，ＤＭＡ１，ＤＭＡ２，ＵＳＢＯＴＧ）、スレーブ（ＡＣＣＥＬ，ＳＲＡＭ１（１１２ＫＢ）、ＳＲＡＭ２（１６ＫＢ）、ＡＨＢ２（ペリフェラル、ＡＨＢ１ペリフェラル）、ＱｕａＳＰＩなど）で構成されております。
このバスマトリックスによりSRAM1,SRAM2等に同時にアクセス可能となり並列処理が可能であり、画像、音声データなど大きなデータ処理の運用もこのチップ内で完結できます。

#ＡＨＢとＡＰＢ
ＳＴＭ３２は、ＡＭＢＡのバス規格を採用し、その中の2つのバス高速なバスＡＨＢと低速なバスＡＰＢを採用している。なぜならば、効率よく通信できるように、高速なバスと低速なバスが設けられそれらはバスブリッジにより接続されています。高速バスにはセレクターがあり、並列に処理できるようになっています。ＡＨＢバスマトリックスはマスターとスレーブペリフェラルでAHBバスで接続されアビータによって接続を選択できる。AHB1（1180MHz）は、メインのバス GPIO PORTA~H、AHB/APBと接続、USB OTG HS,AHB2(2180MHz)は、USB OTGFS CAMERAインターフェースとつながっています。また、AHB1とAPB1及びAPB2はブリッジでつながっています。APB1は高速なバスで最大90Mhz、APB2は低速な45MHzであり、適切な動作周波数により消費電力を抑えることができる。

ＡＭＢＡのバスの規格には、ACE,AXK,AHB,APBが含まれている。
https://www.arm.com/ja/products/amba-open-specifications.php

# STM32F446のペリフェラル
STM32F446はFMC,QuadSPI搭載、USBホスト（ハイスピードモード対応）、カメラインターフェース（CAMERA IFT）がついてます。

※FMC　フレキシブルメモリコントーラ
※QuadSPI デュアルクアッドＳＰＩ　外部に高速なフラッシュメモリを実装ができます。

# STM32F446のパッケージ
ＷＬＣＳＰ８１パッケージ(３．７２８×３．８５ｍｍ)
ＬＱＦＰ１４４パッケージ（２０×２０ｍｍ）
フラッシュメモリには、２５６ＫＢまたは５１２ＫＢ
SRAMは１２８ＫＢ内蔵

#値のサイズ
ＡＲＭではデータのサイズを１ワードは３２ビットとします。
バイト(byte) ８ビット
ハーフワード(Harf Word)　１６ビット
ワード(Word)　３２ビット
ダブルワード(Dword)　６４ビット

#変数の宣言について
ＫｅｉｌのコンパイラはISO C99形式になっており、Ｃ９９に沿った変数の宣言とi/oタイプ識別子を使用しましょう。
unsigned char -> uint8_t
unsigned short -> uint16_t
uisigned long -> uint32_t
volatile char -> __O uint8_t
volatile short -> __O uint16_t
volatile long -> __O uint32_t
