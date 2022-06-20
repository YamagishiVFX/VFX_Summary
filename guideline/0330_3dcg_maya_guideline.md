# Maya 3D制作ガイドライン

Created : v1.0.0 a0.0 2022/06/02 Tatsuya YAMAGISHI

## ファイル形式
- **.mb:** バイナリー形式。コンピュータが理解しやすい形式。人が解読することはできない。データが軽い傾向があり、アセットに使われることが多い
- **.ma:** アスキー形式。人が読めるテキストデータ。melで記述されている。編集を行えるため、ショット用ファイルで使われることが多い。

## シーン構造
### 参考
- YouTube：HigaCgチャンネル 【Maya解説】絶対にやってはいけないデータづくり!!Outlinerを瞬時に片付ける方法も公開！
- https://www.youtube.com/watch?v=-msNa5vqKT8&list=PLLfXNZdPD1UPgC3BS9ftBIB7ekuLHVvuR&index=17

### アセット構造一例
- プロジェクトの仕様に則り、管理しやすいシーン構造にする。

![image](https://i.gyazo.com/8b2a30c2857f2a29a0bf6313909d41dd.png)


## シーンクリーンアップ
### 選択して別名で保存も有効


### Namespace Editorを開き、不要なネームスペースが無いか？確認
![image](https://i.gyazo.com/8ff3bf63f4d63349929c5b9c9a191abe.png)

### `Edit > Delete by Type > History`で不必要なヒストリーを削除

![image](https://i.gyazo.com/91bdc6f20d971bd51edb7a2422f17652.png)

### `File > Optimize Scene Size` を実行し不要なデータを削除

![iamge](https://i.gyazo.com/bec38addf62b4e4704b9a2e0566b7e78.png)

### 作業用の一時的なDisplay Layer等を削除

![image](https://i.gyazo.com/bec38addf62b4e4704b9a2e0566b7e78.png)