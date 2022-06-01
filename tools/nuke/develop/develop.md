# Nuke : 開発

# pip Install
1. Nukeを管理者権限で起動
2. 以下のスクリプトを実行

```Python
import pip
from pip._internal import main as _main

package_names = ['numpy']
_main(['install'] + package_names + ['--upgrade'])
```