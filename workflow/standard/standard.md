Updated: 
2022/06/03
- DIC サイト追加


2022/05/26
・ 一部追加修正

2022/05/25
・ 一部追加修正

※ 専門家による監修を受けていません。色々違ってたらごめんなさい。
※ 記事の内容に一切の責任を持ちません。

# 仕様と学問：
## 背景
「標準化」が生まれた背景は次の動画などで少し触れられている。

 [YouTube:【ざっくり解説】デザインの歴史 -01- 「デザインの誕生」](https://www.youtube.com/watch?v=wYCdiXczXBI)

## 概要
- 「法律書」のようなイメージを持つ人もいるが、体系的にまとめられた手法や学問の共有による生産性向上などが目的。
- 理解するために **専門分野の一定レベルの学問や技術（テクノロジー）が必要** となる事がある。
- テクノロジーの発展に「標準化」はとても大切。国内のVFXでもそのような動きが出てくることが期待される。（僕が知らないだけでそういった動きはあるのかも）

# 仕様書、ガイドライン：
- 仕様書作成の際、引用は標準規格からされる事が多い。
- 仕様を理解するためには、関連する標準規格の理解が必要となる。
- 標準規格の入手は標準化団体などのサイトからPDFなどを購入する。
    - 値段に関しては、大体数千円くらいの印象だが、数万円するものまで値段は様々な印象がある。
- 仕様はシステムを構築するために必須。システムあっての仕様とも言えるかもしれない。

引用：Netflix カラーグレーディングガイドライン

![](https://d1i9y8i5xa5nlc.cloudfront.net/uploads/user_image/image/32588/resize_img_aa748a7d-5744-4926-be62-af6bbb3ba64c.png)

# 映像に関する標準ヒエラルキーと標準化の流れ：
違ってるかも。あまり自信はない。

![](https://d1i9y8i5xa5nlc.cloudfront.net/uploads/user_image/image/32587/resize_img_958b370d-f230-44d7-855e-ee446f319290.png)


# 映像作品の仕様書が決定する順番の例
※ **各仕様は撮影開始（クランクイン）までに各部署間で共有されている必要がある。** とされている。

1. 作品仕様（納品仕様）
2. 撮影仕様
3. ポスプロ仕様（含カラーマネジメント仕様）

---- ＜以下、外部と共有されることはあまりない＞ ----

4. VFX仕様
5. 2D仕様
6. 3D仕様

### 作品仕様
作品仕様によって作品の品質が定義される

### 撮影仕様
納品の品質に耐えうる撮影仕様を定義する

### ポスプロ仕様
撮影の品質を損なわない、各部門間とのデータのやり取りなどを定義

### VFX仕様
納品の品質を損なわず、撮影素材を編集しても出来るだけ劣化させない仕様を定義する


# 世界標準：
## ISO ： International Organization for Standardization
* 国際標準化機構。: https://www.iso.org/home.html

規格界のトップ。グローバルスタンダード

**ISO 11664-1:2007(E)/CIE S 014-1/E:2006. Colorimetry – part 1: CIE standard colorimetric observers.**

- CIE-XYZ 1931 標準観測者

**ISO 11664-2:2007(E)/CIE S 014-2/E:2006. .Colorimetry – part 2: CIE standard illuminants.**
- CIE-XYZ 1931 標準イルミナント

**ISO 11664-3:2012(E)/CIE S 014-3/E:2011. Colorimetry – Part 3: CIE Tristimulus Values.**
- CIE-XYZ 1931 等色関数


## IEC : International Electrotechnical Commission
国際電気標準会議 : https://www.iec.ch/homepage


### 主な標準規格
* IEC 61966-2-1：sRGB
* ISO/IEC 14496-10 Advanced Video Coding : H.264（ITU-T Rec. H.264の標準規格）
* IEC 60461 : SMPTEのタイムコード


## CIE フランス語：Commission internationale de l'éclairage
国際照明委員会 : https://cie.co.at/

現代の色彩工学の基盤と言っても過言でない。ISOとずぶずぶ。


<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
光の照明の分野での科学、技術及び工芸に関するあらゆる事項について国際的討議を行い、標準と測定の手法を開発し、国際規格及び各国の工業規格の作成に指針を与え、規格・報告書などを出版すると共に他の国際団体との連携・交流をはかることを目的とした国際的な非営利の団体である。 引用:JIS Z 8113 照明用語
</div>

### 主な標準規格
* ISO 11664-1:2007(E)/CIE S 014-1/E:2006. Colorimetry：CIE-XYZ 1931


### Tips
- 色をRGBの３つの値の定量で扱えるのはCIE-XYZ表色系によるもの。CIE-XYZ表色系は2031年で誕生100年になる。
- `D65` などの「CIE標準イルミナント」「CIE標準光源」などもCIEの標準化によるもの

## IEEE：The Institute of Electrical and Electronics Engineers, Inc.  
アメリカ合衆国に本部がある、電気・電子技術者の学会。パソコン周辺機器の規格とかで名前を聞くような？

### 主な標準規格
- IEEE 754 浮動小数点算術に関する標準規格
- IEEE 802


## ITU-R : ITU Radiocommunication Sector
ITU : https://www.soumu.go.jp/g-ict/international_organization/itu/pdf_contents.html（日本語解説サイト） 

国際電気通信連合 無線通信部門。国際電気通信連合 (ITU) の3つの部門のうちの一つであり、無線通信に関する事項を担当する

### 主な標準規格
* ITU-T Recommendation. H.264
* ITU-R Recommendation BT.709（SD TV）
* ITU-R Recommendation BT.1886（HD TV）
* ITU-R Recommendation BT.2020（UHD TV）
* ITU-R Recommendation BT.2100（HDR TV）

### Tips:
- etc. のように略すと IUT-R Rec. BT.709 となる。
- 日本語では ITU-R 勧告 BT.709 と呼ばれたりしている。
- 一般的には **通称** が使われることが多いため、引用を明記しなければならない **技術資料以外** では、名称に関しては「正解」「間違っている」などはあまり気にしなくていいのでは？というのが個人的な見解。Rec.709 、BT.709、ITU-R BT.709 などは **全て同じもの** を指していると思われる。

# 米国：
## SMPTE : Society of Motion Picture and Television Engineers
米国映画テレビ技術者協会：https://www.smpte.org/

* ST 2065-1:2012 - SMPTE Standard - Academy Color Encoding Specification (ACES)
* ST 2084（HDRのPQ: Perceptual Quantizer方式)

## ASC : The American Society of Cinematographers
全米撮影監督協会 : https://theasc.com/

* ASC - CDL
  * VFXではスタンダードだが、国内ではほとんど見かけたことが無い。
  * ACESワークフローに採用されている。


## DCI : Digital Cinema Initiatives  
アメリカの映画制作業界団体：https://www.dcimovies.com/

* DCI-P3 https://www.dcimovies.com/
* DCI Archives https://www.dcimovies.com/archives/

## AMPAS : Academy of Motion Picture Arts and Sciences  
映画芸術科学アカデミー：https://www.oscars.org/

ACES
"Specification S-2008-001", Academy of Motion Picture Arts and Sciences (A.M.P.A.S.), 2008.



## VES : Visual Effects Society  
視覚効果協会：https://www.visualeffectssociety.com/

### VFX Reference Platform（こちらはどちらかというとガイドライン）
- [VFX Reference Platform](https://vfxplatform.com/)
- [Blender : VFX Reference Platform](https://code.blender.org/2022/02/vfx-reference-platform/)  
    - VFX Reference Platformに対するBlenderの考え

### VES Transfer Specifications
https://vestransferspec.org/

VFX用素材に関する仕様のガイドライン

### 関連
[ETC - VFX Image Sequence Naming](https://www.etcentric.org/)

## SIGGRAPH
- 標準化の団体ではないが、ここにCGに関する論文が沢山提出されている。その中のいくつかはツールの機能として実装され一般化する事もある。

    - [Cinematic Color Motion-Picture Color Management Siggraph 2012 Course](https://cinematiccolor.org/)

# 日本：
## JIS：Japanese Industrial Standards
日本産業規格 : https://www.jsa.or.jp/whats_jis/whats_jis_index/

ISOの日本ローカライズ。ISOに対応したJIS規格が大体あると思われる。コンドームからカラーマネジメントまで幅広い分野を扱っている。

### 代表的な規格：
- JIS Q 21500：2018(ISO 21500：2012) プロジェクトマネジメントの手引

### 引用 JIS Z 8105 色に関する用語：「輝度、明度、明るさ」
![image](https://i.gyazo.com/692f55619e48482801e6f7834bc6e0c5.png)

## JLMA：Japan Lighting Manufacturers Association
日本照明工業外 : https://www.jlma.or.jp/index.htm

JIS/CIE、JIS/IECなどの活動もしている。


## ARIB : 一般社団法人　電波産業会

https://www.arib.or.jp/

- ARIB STD-B10
- ARIB STD-B67 (HDR のHLG: Hybrid Log Gamma方式) ※NHKとBCCの共同開発らしい。

## 日本色彩学会：
https://color-science.jp/

定期的に色に関する学会誌を発行している。また、色に関する標準化の活動を行っているらしい。

https://color-science.jp/gakkaishi/backnumber/

# 国際単位系 = SI単位系：
天気予報で使われていた「ミリバール」が「ヘクトパスカル」なったり、様々な単位に影響を与えている。

* SI基本単位
    * 長さはm。重さはkgなど
    * 明るさの基本単位、光度：Cd（カンデラ）は唯一心理物量
      * 他の単位が「物理量」を扱っているのに対し「明るさ」は人の感じる心理的なもの。測光量とも言われる。

* SI組立単位
    * ディスプレイの明るさ（輝度）cd/m2（カンデラ平方メートル＝ニット、ニッツ）など

### 参考：国際単位系(Wikipedia)
https://ja.wikipedia.org/wiki/%E5%9B%BD%E9%9A%9B%E5%8D%98%E4%BD%8D%E7%B3%BB


# VFXに関する主な標準規格：
## 映像
- ITU-R Recommendation BT.709（SD TV）
- ITU-R Recommendation BT.1886（HD TV）
- ITU-R Recommendation BT.2020（UHD TV）
- ITU-R Recommendation BT.2100（HDR TV）

## 映像（映画）制作ワークフロー
- ST 2065-1:2012 - SMPTE Standard - Academy Color Encoding Specification (ACES)

## ディスプレイ
- IEC 61966-2-1：sRGB
- DCI-P3

## カラーマネジメント
- JIS Z 8105 色に関する用語
- JIS Z 8113 照明用語
- JIS Z 8120 光学用語
- JIS Z 8701 XYZ表色系及びX10Y10Z10表色系による色の表示方法
- JIS Z 8719 物体色の条件等色度の評価方法
- JIS Z 8720 測色用の標準の光及び標準光源
- JIS Z 8721 色の表示方法−三属性による表示
- JIS Z 8722 物体色の測定方法
- JIS Z 8723 表面色の視感比較方法
- JIS Z 8724 色の測定方法 − 光源色
- JIS Z 8741 鏡面光沢度測定方法