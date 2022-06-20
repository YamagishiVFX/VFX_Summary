Created v1 2022/06/15 CG Sup. Tatsuya Yamagishi

# Reference 
- [Substance Painter Environment variables](https://substance3d.adobe.com/documentation/spdoc/environment-variables-172823292.html)
- [BORN DIGITALサポート：Substance Painter用環境変数](https://support.borndigital.co.jp/hc/ja/articles/360000236382-Substance-Painter%E7%94%A8%E7%92%B0%E5%A2%83%E5%A4%89%E6%95%B0)

# Substance Painter Environment Variables
### `SUBSTANCE_PAINTER_LICENSE`

値 : ライセンスファイル自体へのパス。

ライセンスファイルのデフォルトの場所を上書きすることを許可します。 例：ライセンスファイルが

`H：/allegorithmic/licenses/substance_painter.key`

にある場合、変数データは 

`"H：/allegorithmic/licenses/substance_painter.key"`

になります。


<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
2017.1.0より前のバージョンの場合は、代わりにSUBSTANCE_PAINTER_2_LICENSEを使用してください。
</div>


### `ALLEGO_LICENSE_IDLE_DELAY`
Value: 7200

マルチユーザー構成の場合にライセンスシートを解放するまでの秒数を指定します。 デフォルトは2時間（7200秒）です。

### `ALG_PAINTER_SKIP_CHECK_FOR_UPDATES`
値：0または1（1 =アップデートチェックを無効にする）

アプリケーションの起動時にアップデートチェックをスキップすることを許可します。

<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Substance Painter 2018.2.2以降でサポートされています。
</div>


### `SUBSTANCE_PAINTER_SVT_HARDWARE_ACCELERATION`
Value: 0 or 1 (1 = Enabled)

GPUの機能を使用。 GPUまたはオペレーティングシステムでサポートされていない場合、設定は無視されます。
互換性のあるハードウェア構成については、ドキュメントを参照してください。[スパース仮想テクスチャ](https://support.borndigital.co.jp/hc/ja/articles/360015409074)

この変数は、設定ウィンドウで利用可能なパラメータを上書きします。

<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Substance Painter 2018.3.0からサポートされています。
</div>


### `SUBSTANCE_PAINTER_TEMP_LOCATION`
Value: Direct path to a folder

Substance Painterがその一時ファイル（SVTキャッシュを含む）を書き込む場所を定義します。

この変数は、Settingsウィンドウで利用可能なパラメータを上書きします。



<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Substance Painter 2018.3.0からサポートされています。
</div>


### `SUBSTANCE_PAINTER_PREVIEWS_MEMORY_BUDGET`
Value: 500

アプリケーションがアセットウィンドウからプレビューをロードし、一時的に保存するために使用できるメモリ（Ram）の量を定義します。バジェットの限界に達すると、古いプレビューはアンロードされます。この値は、アセットウィンドウでのプレビューの表示のみを制御します。

値はメガバイトで定義されます。デフォルト値は500MBです。.


<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Supported since version 7.2.
</div>

### `SUBSTANCE_PAINTER_PLUGINS_PATH`
Location of additional Python plugins.


なおディレクトリ内には
- plugins
- startup
- modules
  
の3つのサブディレクトリを作っておく。

### `PYTHONPATH`
アプリケーションのPython統合でロードする追加のPythonモジュール。詳細については、外部Pythonモジュールのロードを参照してください。

### `OCIO`
Path to a config.ocio file which will be used to drive the Color management settings with OpenColorIO.


<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Supported since version 7.4.

この環境変数は、PAINTER_ACE_CONFIG変数よりも優先されます。
</div>

### `PAINTER_ACE_CONFIG`
Adobe ACEでカラーマネージメント設定を行うためのjsonファイルへのパス。

Supported since version 8.1.

<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
Supported since version 8.1.
</div>