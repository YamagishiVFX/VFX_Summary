# Maya モジュールワークフロー
- スクリプトやプラグインの共有の仕組み

## 参考：
- [Maya 2015 リファレンス](https://help.autodesk.com/view/MAYAUL/2015/JPN/?guid=__files_GUID_CB76E356_753B_4837_8C5B_3296C14872CA_htm)

- [【Maya】モジュールワークフローの使い方【Module workflow】](https://unpyside.com/2020/08/20/module-workflow/)
- [【Maya】プラグイン配布の構成を考える](https://tm8r.hateblo.jp/entry/2016/10/18/222755)

## General
### Module Manager

入れておくと便利。

![](https://i.gyazo.com/eca27812a01819a9ffdd30c8de3e7a59.png)

https://github.com/robertjoosten/maya-module-manager

`module-manager.mel` をMayaにD&Dしてインストール

## 手順：
1. モジュールファイル`.mod`を任意のディレクトリに配置
2. ScriptやPuluginディレクトリを定義
3. 環境変数でモジュールディレクトリを指定して起動

## モジュールの定義
```
+ <VERSION> <PLATFORM> <LOCATION> <MODULE_NAME> <MODULE_NAME> <MODULE PATH>
MAYA_PLUG_IN_PATH +:= \plug-ins
PYTHONPATH +:= \python
XBMLANGPATH +:= icons
```

### OS 条件
- PLATFORM: win64
- PLATFORM: mac
- PLATFORM: linux

### システムロケール
- LOCALE:en_US
- LOCALE:ja_JP

### Maya のバージョン
- MAYAVERSION: 2017
- MAYAVERSION: 2018
- MAYAVERSION: 2019
- MAYAVERSION: 2020

## モジュールパスの確認
```Python
import os
def getpath(env="MAYA_MODULE_PATH"):
    for e in os.environ.get(env).split(";"):
        print(e)
getpath()
```

## userSetup.py
- useSetup.pyはMayaが立ち上がる際に自動で実行されるスクリプトで `python` と `mel` の二種類が有ある。
- **userSetup.py** は通常、最初に実行されたものしか実行されない。
- moduleだとpass分複数読み込ませることができる。mel は最初に読み込んだ一つのみが実行されるそうです。

引用：[スクリプトやプラグインを配布できる環境を作ろう！](http://hesperas.blog134.fc2.com/blog-entry-248.html)

![](https://i.gyazo.com/aef7cecd286bb235cae83b079080d3dd.png)

## 既存の制限事項
次のフォルダ タイプは、リーガル モジュール リソース パスとしてサポートされていません。
モジュール システムでは、名前に次の拡張子が付いたフォルダは無視されます。
- .so , .ml, .bundle, .py, .dll,
- .framework, .plugin, .plist, .app,
- .pkg, .rtfd, .download, .sparsebundle

## Redshift
### Custom Install Locations

https://docs.redshift3d.com/display/RSDOCS/Custom+Install+Locations?product=maya

Windows：
```
+ MAYAVERSION:2017 redshift4maya any %REDSHIFT_COREDATAPATH%
scripts: Plugins/Maya/Common/scripts
icons: Plugins/Maya/Common/icons
plug-ins: Plugins/Maya/2017/nt-x86-64
MAYA_CUSTOM_TEMPLATE_PATH +:= Plugins/Maya/Common/scripts/NETemplates
REDSHIFT_MAYAEXTENSIONSPATH +:= Plugins/Maya/2017/nt-x86-64/extensions
REDSHIFT_PROCEDURALSPATH +:= Procedurals
PATH +:= bin
```
Linux and macOS：
```
+ MAYAVERSION:2017 redshift4maya any $REDSHIFT_COREDATAPATH
scripts: Plugins/Maya/Common/scripts
icons: Plugins/Maya/Common/icons
plug-ins: Plugins/Maya/2017/nt-x86-64
MAYA_CUSTOM_TEMPLATE_PATH +:= Plugins/Maya/Common/scripts/NETemplates
REDSHIFT_MAYAEXTENSIONSPATH +:= Plugins/Maya/2017/nt-x86-64/extensions
REDSHIFT_PROCEDURALSPATH +:= Procedurals
PATH +:= bin
```