# Maya PySide
Updated: 2022/06/02 Tatsuya Yamagishi

Created: 2022/06/02 Tatsuya Yamagishi

## Reference from:
RETRIEVE MAIN WINDOW IN PYQT/PYSIDE FOR DCC APPS
- https://russell-vfx.com/blog/2020/8/20/main-window

## MayaのPythonのバージョン
| Maya     | Python |
| -------- | ------ |
| 2019.3.1 | 2.7.11 |
| 2020.4     |   2.7.11     |
| 2022.3   | 3.7.7  |
| 2023     |   3.9.7     |

## MainWindow
**Python3**から`long型` が無くなり `int型` に統合されました。そのため

```Python
# Python2
shiboken2.wrapInstance(long(ptr), QtWidgets.QWidget)
```
としていた `long` の部分を
```Python
#Python3
shiboken2.wrapInstance(int(ptr), QtWidgets.QWidget)
```
と書き換える必要があるようです。

### Example:
```Python
import shiboken2
import maya.OpenMayaUI as apiUI

from PySide2 import QtCore, QtGui, QtWidgets

def get_main_window():
    ptr = apiUI.MQtUtil.mainWindow()
    
    if ptr is not None:
        if sys.version_info.major == 2:
            return shiboken2.wrapInstance(long(ptr), QtWidgets.QWidget)
    
        elif sys.version_info.major == 3:
            return shiboken2.wrapInstance(int(ptr), QtWidgets.QWidget)
            
window = get_main_window()
```

## 関連：
- [VFXワークフローまとめ](https://yamagishi-2bit.blogspot.com/2019/01/vfx_54.html)
- [Python2.7からPython3.7になって変わった点を調べてみた](https://yamagishi-2bit.blogspot.com/2021/10/vfx-python27python37-python.html)
- [Python3.8から3.10で追加された標準モジュール](https://yamagishi-2bit.blogspot.com/2022/05/python38310python-standard-library.html)