# Yamagishi Live-Ation VFX（実写VFX） Overview

- Web : [Vook : 実写系VFXワークフロー概要](https://vook.vc/n/4447)
- GitHub : https://github.com/YamagishiVFX/VFX_Summary
- Blog : Yamagishi 2-bit blog https://yamagishi-2bit.blogspot.com/
- LinkedIn : https://www.linkedin.com/in/tatsuya-yamagishi/

### 更新：
v1.4.0 2022/06/11
- 一部編集

v1.3.0 2022/06/06
- 一部編集
- 「映像史」を別ページに
- 「学習資料」更新
- 「VFX制作ガイドライン概要」を作成
- 「3DCG制作ガイドライン」v1b1

v1.2.0 2022/06/03
- 一部編集
- `Nukeコンポジット概要` 追加
----
## VFXワークフロー一例：

![image](https://i.gyazo.com/7204b9d464a8a4b805df2ef27d962da7.png)

 
- **実写系VFXワークフロー**をなんとなく体系的に列挙してみた。

# はじめに：
* **様々な考え方がある。**
    * 本質的な思想が大事。
    * **個人でも集団でもワークフローの基本は変わらない。**
    * 絵具で絵を描く人からプログラムしか書かない人まで、範囲が非常に広く様々な仕事が存在する。
    * **FXアーティスト** といった場合、一般的な概念はあるものの、実際の働き方は人や環境によって様々だったりする。
    * 環境、人、プロジェクトなどによりワークフローは異なり**正解は存在しない**。ここでは、**個人の基準による普遍性を意識**してまとめている。   

* 独自解釈かつ各分野の専門家の監修などを受けていないため、色々違ってたらごめんなさい。その分野のプロから見たら **間違っていたりおかしな点がある可能性が高い。**
* **5人～の小中規模環境**を想定したワークフローの紹介。大規模環境については良く分からない。
* 「CG業界」は存在しない。何かしろの業界に依存する形になっていると思う。
    * 映画、CM、ゲーム、アニメ、etc。「何のためのCGか？」によってもワークフローは異なる。
* ワークフローは常に変化している。記事の内容も**適時更新**される可能性。
* CGを始めるために必要な知識ではなく、**必要になったら都度調べたり、俯瞰で見つめ直したりする**　ようなもの。
* あまりヒットしないような情報を優先的に扱っている。調べたら良くヒットするような「絵の描き方」「ツールの使い方」のような情報の優先度を下げている。
    * VFX制作の際の優先順位とは異なっていることに注意。基本的には綺麗なアウトプットが最優先。
* 音に関しての知識が壊滅的にありません。
* **記事の内容に一切の責任を持ちません。**

# 社会：
## 資本主義経済
* 資本主義
* 資本家、労働者
* 賃金労働：労働の対価
* 生産性
    * [日本生産性本部：生産性の定義](https://www.jpc-net.jp/movement/productivity.html)
    * [日本生産性本部：生産性に関する統計・各種データ](https://www.jpc-net.jp/research/rd/)

## 会社
* 法人
    * [freee 経理COMPASS：法人とは｜法人の定義と種類・設立方法](https://advisors-freee.jp/article/category/cat-big-04/6469/)
* 経営理念
    * [Redshift：Crafty Apes が繊細なインビジブル エフェクトで作り出す映像の魔術](https://redshift.autodesk.co.jp/invisible-effects/)
* 会計
    * [日本経済新聞：入社1年目で知っておきたかった会計の基礎 1](https://vdata.nikkei.com/newsgraphics/clear-accounting/p1-fs/)
* 戦略
    * グレイナーの「５段階企業成長モデル」
    * [みずほ産業調査 Vol.69 コンテンツ産業の展望 2022 ～日本企業の勝ち筋～](https://www.mizuhobank.co.jp/corporate/bizinfo/industry/sangyou/m1069.html)
* 信用調査
    * 帝国バンク

## 金融
* [メルカリ、ものとお金の価値を学ぶ小学生向け体験学習プログラムを提供](https://edtechzine.jp/article/detail/4030)
* [金融庁：基礎から学べる金融ガイド](https://www.fsa.go.jp/teach/kou3.pdf)
* [金融庁：高校向け金融経済教育指導教材](https://www.fsa.go.jp/news/r3/sonota/20220317/20220317.html)

## 投資
* 資産運用
    * 株式
    * 積立

### 法律
* 法治国家
* 労働契約法
* 労働基準法
* 36協定
    * みなし残業
* 秘密保持契約(NDA)
* 業務委託契約
* 著作権
    * 一般
    * 会社と会社員
    * 会社と業務委託
    * 引用、参考資料、社内資料など
    * 映画等の製作委員会方式における著作権
        * [宇宙戦艦ヤマト著作権問題](https://www.weblio.jp/wkpja/content/%E5%AE%87%E5%AE%99%E6%88%A6%E8%89%A6%E3%83%A4%E3%83%9E%E3%83%88%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA_%E7%9F%A5%E7%9A%84%E8%B2%A1%E7%94%A3%E6%A8%A9%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E7%89%B9%E8%A8%98)
    * CM制作における著作権
    * プログラムコードの著作権
        * オープンソース（oss）の著作権
    * パブリックドメイン
        * [『くまのプーさん』のホラー映画が制作進行中。原作童話のパブリックドメイン入りにより幅広い利用が可能に](https://www.famitsu.com/news/202205/26262708.html)
    * News:
        * [著作物、二次利用しやすく デジタル需要増、法改正で代理許可](https://www.nikkei.com/article/DGKKZO61392450T00C22A6MM8000/)

* 商標登録
    * 著作権と商標登録
    * [「ギコ事件」「のまネコ騒動」商標登録問題](https://www.youtube.com/watch?v=XG9PrbBt4SM)
    * 「ゆっくり茶番劇」商標権取得問題
* 参考：
    * [文化庁：インターネット上の海賊版による著作権侵害対策情報ポータルサイト](https://www.bunka.go.jp/seisaku/chosakuken/kaizoku/index.html)


## 会社員
* 売上、労働の対価
    * [baigie：仕事と給与と評価の関係](https://speakerdeck.com/sogitani1107/shi-shi-togei-yu-toping-jia-falseguan-xi)
* 役員
* 健康保険制度
* 年金制度
    * [厚生労働省：海外の年金制度](https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/nenkin/nenkin/shogaikoku.html)
* 年末調整
* 福利厚生
* 労災
* 所得税

## 個人事業主
* マイナンバーカード
* 税金各種
    * 所得税
    * 個人事業主税
    * 源泉徴収
    * 復興税
    * 消費税
        * インボイス制度
* [文芸美術国民健康保険組合](http://www.bunbi.com/)
    * 加入資格がある組合
* 会計システム
    * 帳簿＆会計ソフト
    * 銀行口座
    * クレジットカード
    * 電子帳簿保存法
* 確定申告
    * 青色申告
    * 税理士
* 資産運用
    * NISA
    * iDeCo

# VFXアーティスト：
### はじめに
* 今すぐ始めるVFX
* 初めてのVFX
* [VFX制作に便利なツール](https://vook.vc/n/4525) ← 2022/05/25 New
* [Effects Corner：優れたVFXアーティストになるためには？](http://effectscorner.blogspot.com/2011/03/what-makes-good-visual-effects-artist.html#.Xh0mcv77SUk)
    * [こちらのサイトで概要を和訳してくれています](http://elephantplus.blogspot.com/2011/03/vfx-artist.html)
* [アメリカの美大で学んだこと05:「絵がうまい」より大切なこと](https://note.com/kenta_design/n/n54064d88a7de)

### 部署と役職、責任やスキル
- 問題解決能力
- どんな環境でも安定した結果を出せる
- 限界まで自分を追い込めるかどうかが成長のために必須（引用：魔改造はなぜ成功するのか 著・倉野信次）
  - 過去を振り返ると「大きく成長できた」と実感できるのは「仕事の納期」なども含めてギリギリまで追い込んだ、追い込まれたときが多い気がする。（あくまでも `限界` であり、心身共に壊れてしまったら本末転倒）

- 参考
  * [Screen Skills : Visual effects (VFX)](https://www.screenskills.com/job-profiles/browse/visual-effects-vfx/)
  * 海外のVFXプロダクションの求人はこの辺を明示しているので、海外の求人を見てみるのも参考になります。
      * [Ftrack : Pipeline TD](https://www.ftrack.com/en/2021/09/what-is-a-pipeline-td.html)
      * [【ACADEMY】テクニカルアーティストとして仕事を得るには](https://jp.gamesindustry.biz/article/2205/22052601/)

### 学習：学問
* [文部科学省：系・分野・分科・細目表](https://www.mext.go.jp/b_menu/shingi/gijyutu/gijyutu4/toushin/attach/1337808.htm)
* [VFX（CG）学習資料](https://vook.vc/n/4473)
* VFX制作会社：海外、国内
* VFXを教える学校
    * 海外
    * 国内
        * [Anitoon Academia](https://www.anitoon.jp/)
* インターネットの活用
    * [仕事：LinkedIn](https://www.linkedin.com/feed/)
    * [ArtStation](https://www.artstation.com/)
    * Facebook、Twitter、Instagram等
    * YouTube、Vimeo
    * LinkedinやArtStationなどに登録して活動していると海外から声がかかる事も少なくないらしい。

* 英語
    * VFXに関係なく、専門的で上質な資料の殆どは英語。
    * 仕事の選択股が圧倒的に増える。労働者にとって「働く環境」はとても大事。
    * [YouTubeの字幕を翻訳読み上げ！Chromeアドオン（拡張機能）CaptionSpeakerの紹介 | 英語が日本語に聞こえる！](https://zenn.dev/o_y_g/articles/c6cfd6b232315f)

<div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
<b>Note:</b> 英語が出来ない僕が言うのもアレだが、映像技術の殆どは海外で生まれ、様々な試行錯誤がされ、その中で特に有効なものがソフトウェア（もしくはプラグイン等）に実装され一般化される。そのような背景があり、映像の技術資料のほとんど（あくまで個人的な体感で9割くらい）は英語の資料になっている。日本語に翻訳されているものはその中の1割あるかどうか？だったり、翻訳されていても間違っていたり、独自解釈であったりすることが多い（僕の記事も独自解釈）。試行錯誤された知見が国内に入ってくることもほとんどない状況となっている。
<br><br>
アーティストは、VFX制作ツールが同じであれば英語を覚える事で仕事の選択幅も圧倒的に広がる。労働者側が待遇などを改善しようと思った場合、既存の環境を変える努力をするより環境を変えてしまった方が楽な場合も少なくない。近年は全世界共通で労働力が不足している傾向があり、労働者側は仕事を選びやすい世の中になっているのではないか？と思われる。グローバルな人材確保が活発になってきており、リクルーターを雇える企業は求人という受け身ではなく積極的にコンタクトを取ってくる。そのような状況で、日本はどのように国際的な競争力を維持し、高度なスキルを持つ人材の流出に対応していくのか？課題は多いと感じている。日本だから関係ないという段階では既に無くなっているというのが個人の認識。グローバルな視点での判断なども重要になってきていると感じている。
<br><br>
そのような背景があるため、個人的には積極的に英語の勉強を勧めたい。（海外の方が良いという意味ではなく、出来るだけ早い段階に言語の壁を取り除いた方がいいと思う）
</div>

* クリエイティブ概論
* 美術史
* デザイン史
    * [YouTube:【ざっくり解説】デザインの歴史 -01- 「デザインの誕生」](https://www.youtube.com/watch?v=wYCdiXczXBI)
* 映像史
    * 映画史
        * 一般
            * https://ja.wikipedia.org/wiki/%E6%98%A0%E7%94%BB%E5%8F%B2
            * [『ストーリー・オブ・フィルム 111の映画旅行』予告編](https://www.youtube.com/watch?v=fYiJyCbcyWE)
        * CFX
            * スターウォーズ：ILM
            * ゴーストバスターズ：ILM
        * VFX
            * [VFX movies : VFX Shots Race 「代表的な映画のVFXショット数、制作費、世界興行収入」](http://www.upcomingvfxmovies.com/svfx-shots-race/)
                * 国内に感しては「総製作費」は表に出てくるものの、実際の「制作費」が表に出てくることはほとんど無いため実態がほとんど分かっていない。
            * トロン
            * ターミネーター2
            * ジュラシックパーク
            * ベイブ
            * タイタニック: Digital Domain
            * スターウォーズ EP1 : ILM
            * マトリックス
            * ロード・オブ・ザ・リング：Weta　Digital
            * アバター(2009)
            * アベンジャーズシリーズ

        * タイトルバック
            * ソウル・バス
            * カイル・クーパー
        * 映画配給会社
            * 海外
              * Disney
            * 国内
              * 東映
              * 東宝
              * 松竹
              * ワーナー ブラザース ジャパン
    * CM
        <div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;">
        2000 ～ 2010年頃、コンピュータの一般化により様々な技術革新が起きた。映像も新しい映像技術、映像表現が沢山生まれ、お金がかけて新しい映像表現を用いたCMなどが沢山作られた。実験的な表現も盛んで様々な作品が作られた。今見返しても作れないなぁ・・・と思うものが沢山ある。当時のアメリカのスーパーボール中は有名企業をこぞってハイクォリティのCMを投入していた（最近観てないので近年どうなっているかは不明）。<br><br>

        当時、日本国内でも同様の流れはあったものの、バブル崩壊の煽りを受けCM制作費も縮小傾向に。そのため、海外のCMの劣化コピーが沢山作られた。海外の有名なCMを資料として沢山受け取った印象がある。冬の時代。
        
        今はこのころの表現をもっと整理したり、如何にリアルタイムに落とし込めるか？という面が盛んな気がする。
        </div>
        
        * [How David Fincher's Early Commercial Work Paved the Way for His Hollywood Success](https://collider.com/david-fincher-commercials-explained/)
          * この時代を駆け抜けたレジェンドどいえばデビッドフィンチャー。完全にオーパーツ。
          * Digital Domainによる[「2003 - ADIDAS」 ](https://vimeo.com/239309998?embedded=true&source=video_title&owner=48066928)は伝説。
          * [2003 - ADIDAS : VFXブレイクダウン](https://vimeo.com/239310831?embedded=true&source=vimeo_logo&owner=48066928)
    * アニメ
        * 海外
          * Disney ターザン
          * トイストーリー
        * 国内
          * もののけ姫
          * 劇場攻殻機動隊
          * Studio4℃
    * MV
        * マイケルジャクソン
        * ニコ動
        * TikTok
    * Gameムービー（リアルタイムの台頭によりオワコンかも・・・）
        - スクエアエニックス：ビジュアルワークス
        - Blizzard
        - フロムソフトウェア
        - Digic Pictures
        - 白組

    * インターネット
        * YouTube、TikTok
        * ニコ動
* 賞
    * アカデミー賞
    * サンダンス映画祭
    * カンヌ国際映画祭
    * 日本アカデミー賞
    * VFX-JAPANアワード
    * CGWROLD
* 色彩
    * [CG CINEMATOGRAPHY](https://chrisbrejon.com/cg-cinematography/)
      * バイブル。とにかくこれを見ておけば問題ない。
    * 色彩検定
* 絵画
    * デッサン、クロッキー
* 脚本
* 映像演出（構図、カメラワーク、編集等）

* カメラ
    * 参考
        * [FUJIFILM：film 101(英語：フィルムやカメラに関して基礎知識)](https://www.ishootfujifilm.com/film-101/articles)
    * 一眼レフカメラ
        * Canon、Nikon、Panasonic、Sony
    * 一般的なムービーカメラ
        * GoPro、AJA
    * シネマカメラ
        * Canon、Panasonic、Blackmagic、ARRI、SONY
        * [RED](https://www.red.com/red-tech)
    * カメラ情報
        * [VFX Camera Database](https://vfxcamdb.com/)
    * シャッター、絞り、ISO
        * [Photography Mapped - Interactive Camera Diagram](http://photography-mapped.com/interact.html)
    * 口径幅と焦点距離
    * 画角の計算
    * レンズ
        * [ZEISS eXtended Data](https://www.zeiss.co.jp/consumer-products/cinematography/content/extended-data.html?fbclid=IwAR1jw3QV1iYRQPem6V99jrLqazsZp7exvWi5vwkNqh8wl2NrnK51VoBUpec)

    * 被写界深度
        * 被写界深度とセンサーサイズ、F値
        * [DOF Simulator](https://dofsimulator.net/en/)
        * [UE4:Cinematic Depth of Field Method](https://docs.unrealengine.com/4.27/en-US/RenderingAndGraphics/PostProcessEffects/DepthOfField/CinematicDOFMethods/)
        * [Richard Rosenman: DOF PRO](https://richardrosenman.com/shop/dof-pro-ae/)
    * モーションブラー
    * レンズディストーション
    *  [入射瞳：Entrance pupil](https://www.cybernet.co.jp/optical/course/word/n01.html)
    * ローリングシャッター 

* 情報処理（コンピュータ、データ）
    * データサイエンス
* 数学
    * 単位等：Unit
        * ラジアン r（弧度法）：国際単位系
            * CGの回転などで使用
        * ステラジアン sr：国際単位系
            * 照明器具やCGのライティングなど光の強さなどで使用
    * 数学関数
        * ceil、floor、round、modulo
        * min、max
        * pow、sqrt、log、log10
    * 三角関数
        * sin、cos、tan
        * asin、acos、atan
    * 基本的なベクトル計算
        * [VFXアーティストのためのベクトルの計算](https://yamagishi-2bit.blogspot.com/2020/09/blog-post.html?q=%E3%83%99%E3%82%AF%E3%83%88%E3%83%AB)
    * 基本的な行列計算
        * [文部科学省：行列入門](https://www.mext.go.jp/content/20210525-mxt_kyoiku01-000009442_1_1.pdf)
    * 四元数：クォータニオン
        * [YouTube : Unity Japan【Unity道場 博多スペシャル 2017】クォータニオン完全マスター](https://www.youtube.com/watch?v=uKWLPU8gfIY)
    * 資料など
        * [Scientific Visualization: Python + Matplotlib](https://github.com/rougier/scientific-visualization-book)
        * [数学を知ればゲーム制作の幅が広がるUnity社エンジニアが解説するグラフの意味とゲームへの応用](https://logmi.jp/tech/articles/326426)
        * [Nuke Expression 101](http://www.nukepedia.com/written-tutorials/expressions-101)
        * [CAMERON CARSON :  NUKE WAVE EXPRESSIONS](https://www.cameroncarson.com/nuke-wave-expressions?fbclid=IwAR3FTMxQitt-2zL2jY4TBKIcb03K70uZTvNJQxlnrAaR-yACYftCnUacnGQ)
* 物理
    * 単位：
        * 明るさの基本単位 = カンデラ：cd
            <div style="padding: 10px; margin-bottom: 10px; border: 1px solid #333333; border-radius: 10px;"> SI単位なのに学校では習わない。7つのSI基本単位のうちの光の明るさの（心理）物理量。色、光に特に関りが強い僕たちは名前は知っておいた方がいいと思われる。これを基準にした組単位にニット、ルクス、ルーメンなどがある。特にライティングのライトの単位などで出てくることもある。
            </div>
* アルゴリズム

    Houdini、Nuke、Fuison、Blender(Geometry Node) など、一部ツールではワークフローの実装がしやすいツールではアルゴリズムを知っておくと便利な事があるらしい。


  * [50分で学ぶアルゴリズム / Algorithms in 50 minutes](https://speakerdeck.com/e869120/algorithms-in-50-minutes)
  * 代表的なアルゴリズム
    * フラクタル
    * パーリンノイズ
    * ボイズ：Boids
        * [Qiita: Boids アルゴリズムで鳥の群れを作ってみた](https://qiita.com/kure/items/2638de370974a791756a)
  * メガデモ
* 現代における映像のVFX
    * 世界、日本

* VFXに関係ありそうな団体
    * [VFX-JAPAN](https://vfx-japan.jp/)
    * [CG-ARTS](https://www.cgarts.or.jp/)
    * [JFP](https://jfproject.org/about)


# 表現手法：
* モーフ
    * マイケルジャクソンのあれ
* タイムラプス
* クロマキー
* スリットスキャン
    * [MUSIC SAVES TOMORROW (SPACE SHOWER TV STATION ID 2011) 監督：辻川幸一郎](https://vimeo.com/26473392)
* モザイク処理
* バレットタイム
    * ロスト・イン・スペース（1998）
    * マトリックス（1999）
    * ソードフィッシュ（2001）
* ハイスピード（HS）
* 透過光
* コマドリ
  * [imai / Fly feat.79,中村佳穂](https://youtu.be/iQi3aMQXip8)
* ジェネラティブアート
    * [ジェネラティブアートを始めよう](https://note.com/p5aholic/n/n853fd1d137d1)
* 多重露光
* ティルトシフト

etc.

# 標準化：
## VFXに関する主な標準化団体（何となく強い順）
- [関連：VFXに関する標準化](https://vook.vc/n/4491) ← New 2022/05/18

### 国際標準
- ISO
- IEC / ISO
- CIE / ISO
- IEEE
- ITU / ITU-R

### 米国標準
- SMPTE
- DCI
- AMPAS
- ASC
- VES
    * [VFX Reference Platform](https://vfxplatform.com/)（どちらかというとガイドライン）
    * [Blender : VFX Reference Platform](https://code.blender.org/2022/02/vfx-reference-platform/)  VFX Reference Platformに対するBlenderの考え
### 日本標準
- JIS

## 国際単位系：SI単位系
* SI基本単位
* SI組立単位

## 用語
* [VFXの用語](https://vook.vc/n/4486) ← New 2022/05/16
    * 海外と日本の違い等

### 主な標準規格
* JIS Z 8105 色に関する用語
* JIS Z 8113 照明用語
* JIS Z 8120 光学用語

# コンピュータ概論：
### 情報処理
* ビット、バイト
* データと型
* コンピュータの仕組み
    * 中央処理装置：CPU
    * 主記憶装置：メモリ
    * 補助記憶装置：SSD、HDDなど
    * 入力装置：マウス、キーボード、スキャナー、マイク等
    * 出力装置：ディスプレイ、スピーカー、プリンタ等
    * (画像処理用演算プロセッサ：GPU)
* データ処理のモニタリング
    * Windows：タスクマネージャー
    * MAC：アクティビティモニタ
* 論理演算：ブール演算
    * 論理和、論理積

### エンコード、デコード

### シェルコマンド
* Windows：コマンドプロンプト = DOSコマンド
* Unix系ターミナル = シェル、バッシュコマンド
    * Mac、Linux
    * シェルスクリプト

### プログラム
* プログラミング言語
* コンパイル
* インタープリタ
* CLI、GUI
  
### バージョニング
* セマンティックバージョニング


# プロジェクトマネジメント：
* 参考資料：
    * JIS Q 21500：2018(ISO 21500：2012) プロジェクトマネジメントの手引
    * [SQUARE ENIX OPEN CONFERENCE ゲーム開発プロジェクトマネジメント講座](http://www.jp.square-enix.com/tech/openconference/library/2011/dldata/PM/PM.pdf)
    * マネジメントと言えば[ドラッカー](https://ja.wikipedia.org/wiki/%E3%83%94%E3%83%BC%E3%82%BF%E3%83%BC%E3%83%BB%E3%83%89%E3%83%A9%E3%83%83%E3%82%AB%E3%83%BC)。

* 団体
    * [一般社団法人プロジェクトマネジメント学会](https://spm.or.jp/)
    * [PMI日本支部](https://www.pmi-japan.org/)
* プロジェクト理念
* クォリティラインと納期の設定
* 環境と評価
* 文章化と情報共有
    * [ドキュメント作成スキル向上を目指す人向けおすすめ記事まとめ](https://qiita.com/yasuoyasuo/items/1eb7298f91a44dce7abc)
    * Wiki
        * DokuWiki、Crowi
    * Markdown方式
* ツール
    * Google、Office、Slack、Notion、ShotGrid
    * Python

### タスクベース
* [backlog：サル先生のプロジェクト管理入門](https://backlog.com/ja/project-management-guide/)
* チームマネジメント
    * スタッフリング：部署と役職、責任 
    * [関連：将棋の初手から学ぶチームマネジメント](https://yamagishi-2bit.blogspot.com/2020/01/blog-post.html?q=%E5%B0%86%E6%A3%8B)
* タスク
* 見積：ブレイクダウン、ビッド
* 生産性の算出
    * [日本生産性本部：生産性の定義](https://www.jpc-net.jp/movement/productivity.html)
    * [なぜ日本の給与は上がらないのか?〜「低所得」ニッポンを分析〜](https://gendai.ismedia.jp/articles/-/95082?imp=0)
* 優先順位
* ガントチャート
* チケット
* ベロシティ
* タスクベースの制作管理ツール
    * ShotGrid
    * Ftrack
    * Notion
    * [redmine](https://redmine.jp/)

# 制作：
## 製作と制作
## VFXワークフロー
* [ARRI公式HP : The post-production workflo](https://www.arri.com/en/learn-help/learn-help-camera-system/camera-workflow/image-science/aces/post-production)

引用：ARRI

![](https://i.gyazo.com/573440615be069e8a4c91832088156d5.png)

## ガイドライン
* ロケハンガイドライン
    * 記録するものなど
* オンセットガイドライン
    * 撮影立ち合い：服装、持ち物など。記録するもの。
        * 養生テープ
        * メジャー
        * カラーチャート
        * スマホ、iPad、ノートPC等
    * CGリファレンス撮影ガイドライン
        * カラーチャート、ミラーボール、グレーボール
    * HDRI撮影ガイドライン
        * [fxguid：The Definitive Weta Digital Guide to IBL](https://www.fxguide.com/fxfeatured/the-definitive-weta-digital-guide-to-ibl/)
          * あのWeta DigitalによるIBL撮影ガイドライン。神資料。
    * フォトグラメトリ用ドローン撮影ガイドライン
        * [ドローンの登録制度が義務化](https://vook.vc/n/4372)
* [3D制作ガイドライン](https://vook.vc/n/4554)
    * 3Dアセット制作ガイドライン
      * FX用アセット制作ガイドライン
      * CFX用アセット制作ガイドライン
* 2D制作ガイドライン
    * [Nukepedia: Compositing Practices 101](http://www.nukepedia.com/written-tutorials/compositing-practices-101/)
    * Nukeコンポジットガイドライン
        * [Nukepedia: 10 tips to optimising Nuke and creating efficient workflows](http://www.nukepedia.com/written-tutorials/10-tips-to-optimising-nuke-and-creating-efficient-workflows/)
        * Nukeコンポジットガイドライン v6 Tatsuya Yamagishi
        * [コンポジゴク：NUKEのスピードを速くするためのTips集](http://compojigoku.blog.fc2.com/blog-entry-43.html)
* コーディングガイドライン
    * Pythonコーディングガイドライン
        * ZEN、PEP8
        * Googleスタイル、numpyスタイル

## 仕様書
### VFXの代表的な仕様の項目

これらを決めてからプロジェクトを開始する。プロジェクト開始途中で変更すると、**作業がやり直しになる可能性が非常に高い**項目。

  * 解像度：Image format Resolution
  * FPS : Frame per second
  * カラースペース：Colorspace
  * ID, Code：識別子
    * Client Code
    * Vender Code
    * Project(Show) Code
    * Episode Code
    * Sequence Code
    * Shot Code
    * Vesion Number
    * YYYYMMDD

### VFX用素材に関するガイドライン
* [VES Transfer Specifications](https://vestransferspec.org/)
* [ETC - VFX Image Sequence Naming](https://www.etcentric.org/etc-publishes-specification-for-naming-vfx-image-sequences/)

### 主な仕様書
なんとなく、仕様が出来上がってく順。仕様は**撮影開始（クランクイン）までに各部署間で共有**されている事が好ましいとされている。


1. 作品仕様書
    * [Netflix作品納品仕様書の例](https://partnerhelp.netflixstudios.com/hc/ja/articles/214806618-Netflix%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E4%BD%9C%E5%93%81-%E7%B4%8D%E5%93%81%E4%BB%95%E6%A7%98-%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3OC-4-1)
2. 撮影仕様書
3. ポスプロ仕様書
4. VFX仕様書
    * 2D仕様書
    * 3D仕様書
        * アセット仕様書
        * ショット仕様書
    * パイプライン仕様書


## 制作進行
* Excelベースのアセット、ショットリスト
* ShotGrid
* Python
    * numpy、pandas、matplotlib

# VFXワークフロー：
## プリプロ：Pre-production
* ロケハン
* 脚本
* アート
## オンセット：On set
* 演出部
* 制作部
* 撮影部
    * DIT
* 照明部
* 美術部
* オンセットデイリー
* VFX
    * オンセット記録シート
    * ターゲットマーカー
        * 作り方。どのようなマーカーが良いか？ 
    * グリーンスクリーン vs ブルースクリーン
        * [MasterClass : Blue Screen vs. Green Screen: Uses for Blue and Green Screens](https://www.masterclass.com/articles/blue-screen-vs-green-screen#what-is-a-green-screen)
    * 黒バック
    * HDRIやVFXのリファレンス撮影
        * 参考資料
            * [gnomon workshop  HIGH DYNAMIC RANGE IMAGING FOR VFX](https://www.thegnomonworkshop.com/tutorials/high-dynamic-range-imaging-for-vfx)
            * [CGWORLD: コスパ最高！　RICOH THETA Z1を利用した ACES対応HDRI制作フロー](https://cgworld.jp/feature/202006-cgw262t1-tips01.html)
            * [RICOH公式HDRIプラグイン](https://pluginstore.theta360.com/plugins/com.theta360.hdri/)
        * カラーチャート、グレーボール、ミラーボール
        * 撮影時のカメラ設定
    * 現像ワークフロー
        * ARRI RAW Converter
        * REDCINE-X PRO
        * DaVinci Resolve
        * LibRaw、ExifTool、RawToAces
        * Nukeワークフローの実装
    * Metadata

        * [Nukeを用いたMetadataによる自動露出合わせ](https://yamagishi-2bit.blogspot.com/2019/03/nuke-metadata-automatically-matching-ev.html)
    * カラーチェッカー、グレーボール、ミラーボール
    * 計測
        * LiDAR Scanner
    * モーションキャプチャ
    * フォトグラメトリ
    * ドローン
    * インカメラVFX（ICVFX）
    * バーチャルプロダクション

## ポスプロ：Post-Production
### 参考
* [Frame.io post-production video workflow](https://workflow.frame.io/)
* [ARRI公式HP : The post-production workflo](https://www.arri.com/en/learn-help/learn-help-camera-system/camera-workflow/image-science/aces/post-production)

引用：ARRI
![](https://i.gyazo.com/89509be813f8351dce52bde3d86d0b7e.png)

### 編集：Edit
* Avid
* Final Cut Pro
* Premire Pro
* DaVinci Resolve

### VFX：Computer-generated(CG)
* ニュートラルグレード
* アンディストーション、リディストーション 

# カラーグレーディング(DI: Digital Intermediate )
- カラーコレクション、カラーグレーディング

### プライマリ
- CDL

### セカンダリ

# MA

# マスタリング（完パケ）


# CG：

## CG検定
## 画像処理
* 画像
* 画像ファイル
    * 型、ビット
    * フォーマット形式
    * 可逆圧縮、非可逆圧縮
    * カラースペース
* 画像ファイル形式
    * [VFXで使うEXRの設定の一例](https://yamagishi-2bit.blogspot.com/2020/05/vfxexr.html)
* 画像処理基礎
    * [3種類の画像処理](https://yamagishi-2bit.blogspot.com/2019/01/vfx_28.html)
    * [色調整の基礎](https://yamagishi-2bit.blogspot.com/2019/08/vfx-wokflow-scene-linear.html)
    * [色合わせ](https://yamagishi-2bit.blogspot.com/2013/11/vfxcolor-matching.html)
* カラコレ
* フィルタ
* トランスフォーム
* αチャンネル
* [フーリエ変換による画像処理まとめ](https://togetter.com/li/1544227)
    * ハイパスフィルタ
        * [YouTube: Nuke Tutorial - Highpass Filter](https://www.youtube.com/watch?v=LE5e2GF7lOI)
        * DaVinciのシャープフィルタ

## 動画処理
* 動画
* 動画ファイル
    * 型、ビット
    * フレームレート
    * ドロップフレーム、ノンドロップフレーム
    * フォーマット形式
    * 可逆圧縮、非可逆圧縮
    * インターレース、プログレッシブ
    * カラースペース
    * オーディオ
    * アスペクト比
      * イメージアスペクト比、ピクセルアスペクト比

## 3DCG
### モデリング
* [パソコン工房：3Dモデリングをはじめる前に知っておきたい基礎知識](https://www.pc-koubou.jp/magazine/63968)
* サーフェイス（ポリゴン）モデル、ソリッドモデル
* 頂点、エッジ、面
* 法線
* トポロジー
    * [ポリゴン分割するのに便利な画像集めました。](https://www.photoshop777.com/post-5774/)
* [YouTube : Smooth Shading](https://www.youtube.com/watch?v=PMgjVJogIbc)
* OpenSubdivision
    * [YouTube : Subdivision Surfaces: Artifacts](https://www.youtube.com/watch?v=k_S1INdEmdI&list=PLYURcfRkTI5XxXw4NixOb4gG02iHFbJr4&index=2)

### テクニック：
- プロジェクション（カメラマップ）

### Shader
* Shader Language
  * OpenGL
  * GLSL、HLSL
  * WebGL
  * OSL
* Material
  * Lambert、Blin、GGX
  * Micro facet
  * Diffuse、Specular、Refraction(Transmissison)
  * Emission
  * Subsurface Scattaring
  * Round Corner
* Material-X

### レンダリング
* [fxguid : The Art of Rendering](https://www.fxguide.com/fxfeatured/the-art-of-rendering/)
* 仮想フレームバッファ
* ラスタライズ（スキャンライン）
* レイトレース
    * 参考        
        * レイトレースの仕組みについては[「VRay：Antialiasing for Shading Effects」](https://docs.chaos.com/display/CWVRAY3MAYA/Antialiasing+for+Shading+Effects)が詳しい
        * ノイズを除去するためのワークフローは[「Arnold：Removing Noise Workflow」](https://docs.arnoldrenderer.com/display/A5ARP/Removing+Noise+Workflow)が参考になる。各レンダラー毎にレイの呼び方とかは異なるが、現在のパストレーサーはほとんど同じような仕組みだと思う。
    * プログラム
        * レイトレース（パストレース）を理解したい場合、自分でプログラムしてみるのが一番
            * [はじめようレイトレーシング](https://raytracing.xyz/)
            * [関連：はじめようレイトレーシングをPythonで写経](https://yamagishi-2bit.blogspot.com/2021/12/httpsraytracing.html)
    * 物理ベース
        * [Physically Based Lighting at Pixar](https://graphics.pixar.com/library/PhysicallyBasedLighting/paper.pdf)
        * [metasequoia4 : 物理ベースレンダリング(1) 概要とglTF](https://www.metaseq.net/jp/archives/2172/)
    * プライマリレイ：レイキャスト
        * レイトレースの計算の基点となるとても大事なレイ。ほとんどのレイの計算はプライマリレイを飛ばしレイの交点を求める事から計算を始める。
        * 交差点：インターセクト
          * 交点のオフセット：浮動小数点による丸め誤差
    * セカンダリ：ライティング、反射、屈折
    * 拡張レイトレース：エリアシャドウ、グロッシネス
    * パストレース：グローバルイルミネーション
    * フォトンマッピング
* スペクトルレンダリング
    * [Spectral Imaging in Production：Course Notes Siggraph 2021](https://jo.dreggn.org/home/2021_spectral_imaging.pdf)
    * [memoRANDOM ：スペクト羅うレンダリング](https://rayspace.xyz/CG/contents/spectral_rendering/)
    * 分光特性と3DCGのRGBレンダリング
        * 反射、屈折、蛍光、偏光、複屈折、条件等色、レイリー散乱、ミー散乱、アッベ数
## AI
* NVIDIA Canvas
* Deep Fake
  * [ディープフェイク（Deepfake）とは｜基本知識、表出した恐怖とその対策について](https://ledge.ai/deep-fake/)

# VFX：
現在VFXの部門は大きく分けて
- **2D** ・・・ コンポジット
- **3D** ・・・ 3DCG

と２つの部門に分けられる。両方を合わせて **CG** と呼ばれることもある。ワークフローが2D、3Dで異なる事もある。作品によっては3Dの作業が無かったり。

プロジェクションマップなどのエンバイロメントを2.5Dという事もあるようだ。

- 僕は2Dのワークフローに3Dを拡張した形でデザインしている。また、フルCG作品でも同じワークフローで作業を行っている。

## カテゴリー
* ビジュアルデベロップメント
* カラースクリプト
* コンセプトアート
* ビジュアライゼーション
* プリビズ
    引用: [CGWorld: 国を越え、アジア全域でプリビズの振興に取り組む。「PREVIS SOCIETY ASIA」シンポジウム](https://cgworld.jp/feature/201602-psa-sympsm.html)
![](https://i.gyazo.com/3684e366e20f84875ffe9d36b6ce31d2.png)

## アセットワーク
* モデリング
* サーフェイス
* リギング
    * IK、FK
* CFX
  * [Automation of Creature FX in a Small Studio Pipeline | Bacon X | FMX HIVE 2022](https://www.youtube.com/watch?v=FDR8wLbBPYc)
* ルックデブ

## ショットワーク
### トラッキング
### レイアウト
### アニメーション

### エンバイロメント（マットペイント）
ひと昔のマットペイントは2Dの絵画のようなイメージだったが、近年は「エンバイロメント：Environment」等と呼ばれ、3DCGなども駆使した **ほぼジェネラリスト** な作業内容となっている。「背景」などを扱うため、エンバイロメントは **地味** な印象もあるかもしれないが、実写映画では時には主役級のルックを作成する事もあり、花形の仕事だと個人的には思います。貢献度も高い役職の１つです。

- [Mattepainter - Blender上でのフォトバッシュ＆マットペイントワークフローを大幅改善してくれるアドオンが登場！](https://3dnchu.com/archives/mattepainter-b3d/)
- [Part 1. Blockout: Medieval Game Environment in UE4](https://www.youtube.com/watch?v=4CRm3GAgAx4)

### FX
### 群衆
### ライティング
* 基礎
    * 映像作品におけるライティングとは？

### コンポジット
* 歴史
    * クロマキー合成
    * デジタル合成の始まり： "Compositing Digital Images" SIGGRAPH 1984 T. Porter and T. Duff
* ツール
    * Nuke
    * AfterEffects
    * Fusion
    * Natron、AVIUTL
* 基礎
    * RGBA
    * プリマルチプライ、アンプリマルチプライ
    * 合成
    * カラコレ
    * トランスフォーム
    * フィルタ（畳み込み、コンボルブ）
    * 作業用色空間
* 合成
    * 標準
    * 加算
    * 減算
        * [「減算」による要素の抽出](https://yamagishi-2bit.blogspot.com/2019/01/composite.html)
    * 除算
* CGのコンポジット：[PIXAR : The Grand Tour: Compositing ](https://renderman.pixar.com/the-grand-tour-compositing)
    * PixarによるフルCGのコンポジットに関する素晴らしいまとめ。
    * NukeとFusionのプロジェクトファイルもあり
* Keying
    * [fxguid : Art of Keying](https://www.fxguide.com/fxfeatured/art_of_keying/)
    * [Compoiste Mentor : Advanced Keying Breakdown](https://compositingmentor.com/category/advanced-keying-breakdown/)
    * ディスピル
        * [関連：ディスピルのテクニックを使った色の置き換え](https://yamagishi-2bit.blogspot.com/2021/12/nuke-despill-vfx.html?q=%E3%83%87%E3%82%A3%E3%82%B9%E3%83%94%E3%83%AB)
* Roto & Paint
* DOF
    * [YouTube：Simulating Physically Accurate Depth of Field in Nuke](https://www.youtube.com/watch?v=Rv7L6M8f2lk)
* 3D Composite
* CG Composite
    * CGのポストエフェクト
    * [3d total : Nuke 使用、複雑な影の合成（データダウンロード/ ※英語ムービー）](https://3dtotal.jp/tutorials/29166/)
* Deep Composite
    * [fxguide The art of deep compositing](https://www.fxguide.com/fxfeatured/the-art-of-deep-compositing/)
* Stereo Composite：立体視



# カラーパイプライン：
VFXカラーパイプライン一例
![](https://i.gyazo.com/d887462f48d452abf9d3fb0f8182ff28.png)

## 色彩工学：カラーサイエンス
### 色彩工学の資料など
* [KONICA MINOLTA：色色雑学](https://www.konicaminolta.jp/instruments/knowledge/color/index.html)
    * 色彩工学の入門としてKONICA MINOLTAさんが定期的に開催している **測色セミナー** が個人的にお勧めです。色とは？から始まり、物理のマテリアル（材質）にも触れるため、それをモデル化しているCGのマテリアルに対する理解も深まります。
* [ccs 光と色の話](https://www.ccs-inc.co.jp/museum/column/light_color/vol14.html)
* [note:色彩工学/カラーサイエンス YoshiColor](https://note.com/yoshicolor)
* [色再現工学の基礎 玄光社 著：大田登](https://www.coronasha.co.jp/np/isbn/9784339076448/)
* [一般財団法人日本色彩研究所](https://www.jcri.jp/JCRI/)
* [Polyphony Digital：Color Science for Games(JP)](https://www.slideshare.net/nikuque/color-science-for-gamesjp)

### 一級建築士試験対策室

一級建築士の色に関する領域が、CGのライティングなどの基礎知識にそのまま使え非常に参考になりました。一級建築士の守備範囲ヤバい・・・。

- [環境　[3.色彩]　色の三原色　物体色　光源色　色の特性](https://tomatoneko.com/kenchiku/kankyo/sikisai/)
- [採光・照明　光の単位](https://tomatoneko.com/kenchiku/kankyo/hikari/)
- [環境　1.日照・日射：太陽高度　日影曲線　日射量　日射熱取得率](https://tomatoneko.com/kenchiku/kankyo/nissyou-nissya/)

### 歴史
* [色空間の歴史](http://www.color-theory-phenomena.nl/08.00.html)
* [YouTube : SCIENCE CHANNEL（JST）ニュートンとゲーテ～物理学者と文学者が導き出した色の科学～](https://www.youtube.com/watch?v=NGzNRSvKFUE)

### 人の視覚
* Tips
    * [YouTube : 【ゆっくり解説】眼の進化ーなぜこれほど精巧な器官ができたのか？](https://www.youtube.com/watch?v=n_i3VXsvCl0)
    * [YouTube : 【ゆっくり解説】あなたが見ている赤色は本当に赤色なのか？－クオリア－](https://www.youtube.com/watch?v=HIMJojVSagg) 盲視の話がとても面白かった。
    *  [YouTube : 太陽は本当は何色なのか？【ゆっくり解説】](https://www.youtube.com/watch?v=w_HcjbKAe0M)
* 錐体、杆体
* 色順応
* 明所視、暗所視
* 恒常性
    * 人によって違う色に見える **あの服** で有名に
* 条件等色：メタメリズム(metamerism)

### CIE-XYZ表色系：色の定量化
* 色
* グラスマンの法則
* 等色実験
    * 測光量
    * 等色関数
* CIE-XYZ色空間
* xy色度図
    * [関連：VFXツールで色度図をプロットしてみる](https://yamagishi-2bit.blogspot.com/2022/03/color-management-vfx-vfx.html)
* 標準イルミナント
* 物体の色
* 光源の色
* 明るさの数値化
    * 輝度、照度
    * [明るさ計算](https://tomari.org/main/java/hikari.html)
* 測色
    * 測色用標準光源
    * 特殊な材質：蛍光、メタル
    * 演色性
      * [写真・映像のライティングの新常識？！演色評価指数（Color Rendering Index）まとめ](https://vook.vc/n/3132)
* 均等色空間：色差
    * [Nukeで色差を評価してみる](https://yamagishi-2bit.blogspot.com/2022/04/color-management-nuke-vfx.html)

* カラーマッチ
    * 色再現工学の基礎：カラーマッチ
    * https://github.com/colour-science/colour-checker-detection
* 明るさ
    * [採光・照明　光の単位](https://tomatoneko.com/kenchiku/kankyo/hikari/)
    * [note:YoshiColor 輝度・照度・明度・明るさ の違いを説明できますか？](https://note.com/yoshicolor/n/n321b7f13952a)
* 色順応のモデル化
    * [CAM and Image CAM Papers：色順応のモデル化の歴史](https://community.acescentral.com/t/cam-and-image-cam-papers/4072)
    * [ZCAM for Nuke](https://community.acescentral.com/t/zcam-for-nuke/4073)

    こういう所に出てくる

    DaVinci: Color > Chromatic Adaptation : 
    
    ![image](https://i.gyazo.com/17720f89148c3e6ef894a11d4981fe53.png)

    Nuke : ColorSpace ノード

    ![image](https://i.gyazo.com/0392bb56c6d5b38c180a5f953cea26d1.png)

* [Colour Science for Python](https://www.colour-science.org/)

## VFXにおけるカラーマネジメント
### 主な参考資料
* [VFX制作における林家問題](https://togetter.com/li/1060942)
* [fxguide : The art of digital color](https://www.fxguide.com/fxfeatured/the-art-of-digital-color/)
* [Cinematic Color : Motion-Picture Color Management Siggraph 2012 Course](https://cinematiccolor.org/)
    * ハリウッドのハイエンドの映画製作のカラーパイプラインが一般化する際の基点となったカンファレンスと捉えています。
* [CG CINEMATOGRAPY CHAPTER1: Color Management](https://chrisbrejon.com/cg-cinematography/chapter-1-color-management/)
* [Cinematic Color2 : Color for Motion Pictures and Games](https://nick-shaw.github.io/cinematiccolor/cinematic-color.html)
    * A VES Technology Committee White Paper 2019
* [Practical HDR and Wide Color Techniques in Gran Turismo SPORT : SIGGRAPH ASIA 2018 Course](https://www.polyphony.co.jp/publications/sa2018/)
* [Multi-Space Color Correction: The New Paradigm](https://www.mysterybox.us/blog/2017/11/08/multi-space-color-correction)
* [Spectral Imaging in Production：Course Notes Siggraph 2021](https://jo.dreggn.org/home/2021_spectral_imaging.pdf)
    * レンダリング、LEDウォールなどの光（スペクトル）に関する発表。
    * Weta Manuka他
* [劇場版「SHIROBAKO」の「色で勝負」の意味を考察する](https://idomizu.dev/archives/7085)

### 色再現
* カラーエンコード、デコード

* 映像制作のための色空間
    * ガンマ、色域、白色点
    * OETF、EOTF
        * [EIZO：第11回　HDR映像（2） 二つのHDRガンマカーブの違い](https://www.eizo.co.jp/eizolibrary/color_management/colorworkflow/series-11.html)
    * IDT、ODT
    * トーンマッピング
* 作業用色空間
* カラーチャート
* 3種類の画像：Image State
    * [AREA JAPANA 第2回：カラースペースにおける3つのファミリー](https://area.autodesk.jp/column/trend_tech/color_magazine/the_three_families_of_color_spaces3/)
    * scene-referred
    * intermediate-referred
    * output-referred
* 色空間の変換
    * [関連：色空間変換行列色々](https://yamagishi-2bit.blogspot.com/2022/03/colormanagement-colortransform-matrix.html)

* LUT
    * ビューイングLUT、コンバートLUT
    * cdl、.cube、.csp、.3dl

* モニタキャリブレーション


* [OCIO : Open Color IO](https://opencolorio.org/)  
  * General
    * [すあまの備忘録：OCIOとACESの知っている範囲メモ](https://godofsuama.hatenablog.com/entry/2020/09/24/100000)
  * Config
    * [toruのブログ：OpenColorIO の Config ファイル作成](https://trev16.hatenablog.com/entry/2019/04/14/193845)
    
    * Free Config
      * Nuke Default
      * SPI-VFX
      * ACES シリーズ


### ワークフロー
* ビデオカラーワークフロー
* リニアワークフロー
* シーンリニアワークフロー
    * シーンリニア  
    * [トーンマッピング](https://yamagishi-2bit.blogspot.com/2013/10/tonemapping.html)
* ACES Workflow：シーンリニアワークフローの標準化
    * Reference
      * [ACES CENTRAL](https://community.acescentral.com/)
      * [ACES TECHNICAL DOCUMENTATION](https://acescentral.com/aces-documentation-copy/)
    * ACES Workflow
      * ACES Colorspace
      * RICD ACES
      * IDT、ACES、LMT、RRT、ODT
    * CDL
    * 各ツールにおけるACES Workflow
      * [Netflix - YouTube：DaVinci ResolveにおけるACESの設定方法（日本語字幕あり）](https://www.youtube.com/watch?v=u9Rvm5xiuhk)

# VFXパイプライン：
## Introduction
* パイプラインとワークフロー

## 歴史
* [VFX movies : VFX Shots Race 「代表的な映画のVFXショット数、制作費、世界興行収入」](http://www.upcomingvfxmovies.com/svfx-shots-race/)
  * 5年くらいでステージが１段階上がって行っているのが見て取れる。

## 参考
* [株式会社ポリゴン・ピクチュアズ / スタジオフォンズ：映像制作パイプラインとアーティストのテクニック](https://a-film-production-technique-seminar.com/fppat/fppat_materials.html)
* [株式会社ポリゴン・ピクチュアズ / スタジオフォンズ：映像制作パイプラインで使用されるツールやミドルウェア](https://a-film-production-technique-seminar.com/fppat/materials/ppi_phones_pipeline_tools/index.html)

## VFX オープンソース
* [Disney Open Source](https://disney.github.io/)
* [Sony Pictures Imageworks OpenSource](https://opensource.imageworks.com/)
* Linux
    * [ASWF: The Academy software foundation](https://www.vfxvoice.com/the-academy-software-foundation-and-the-advantages-of-open-source-software/)
* VFX Open Source
    * [GitHub : Awesome CG / VFX Pipeline](https://github.com/cgwire/awesome-cg-vfx-pipeline)
    * [Pixar USD](https://graphics.pixar.com/usd/release/index.html)
    * [Pixar OpenTimeIO](https://github.com/PixarAnimationStudios/OpenTimelineIO)
    * [OpenImageIO](https://sites.google.com/site/openimageio/home)
    * OpenSubdiv
      * [Pixar OpenSubdiv(英語)](https://graphics.pixar.com/opensubdiv/docs/intro.html)
      * [ピクサーのOpenSubdivほか、サブディビジョンサーフェス技術の系譜を探る](https://cgworld.jp/feature/201511-tremdsofsubdiv.html)
    * OpenFX

## パスコンテキスト
* 仕様とシステム
* ID、コード（識別子）
* 環境変数とパスコンテキスト
* 各ツールの環境変数
* VFXツールの起動方法
    * CLIから起動
    * GUIから起動
    * 簡易的なNukeのショットワークフローの例 

## データベース
* ID
* フィールド
* SQLite

## フォルダ構造

## シーン管理：パス名とシーングラフ
* 概要
  * パス名とシーンストラクチャ
  * パス名によるシーン管理
* Mayaアウトライナー
* Alembic
* Katanaシーングラフ
* USDワークフロー

引用：[cgwiki Usd AssetGuide](https://www.tokeru.com/cgwiki/index.php?title=UsdAssetGuide)
![image](https://i.gyazo.com/fce75be9ed6a2fde266b65fe67df19a9.png)

## USD
### リファレンス
* [Pixar USD](https://graphics.pixar.com/usd/release/index.html)
* [Universal Scene Description Advent Calendar 2021](https://qiita.com/advent-calendar/2021/usd)
* [Reincarnation+#Tech : Pipeline](https://fereria.github.io/reincarnation_tech/11_Pipeline/)
* [cg wiki : Houdini Lops](https://www.tokeru.com/cgwiki/index.php?title=HoudiniLops)
  * Houdiniのサイトですが実際のツールで説明しているため、ある意味一番概要が理解しやすいかもしれません。

### Python API
* [Pythonで始めるUSDの基本 - Stage/Layer](https://zenn.dev/remiria/articles/usd-stagelayer)


### Scene Structure
- Asset
  - [UsdAssetGuide](https://www.tokeru.com/cgwiki/index.php?title=UsdAssetGuide)

- Shot
  - [UsdShotGuide](https://www.tokeru.com/cgwiki/index.php?title=UsdAssetGuide#Shots)

- Camera

- Material
  - [Material-X](https://www.materialx.org/)
    - データ構造、ノードなども仕様で決められている

- Lighting

- レンダーデリゲート:render delegates


### UsdViwer
- [NVidia](https://developer.nvidia.com/usd)

### 各ツールにおけるUSD
Houdini(Solaris:LOP)以外は、Import/Exportの実装のみにとどまる状況。ワークフローはパイプラインなどを開発し自分たちで実装するという背景があるかもしれない。

* [NVidia Omuniverse](https://developer.nvidia.com/usd)
  * マテリアルはMaterial-Xではなく、MDLという独自の実装
    * [NVIDIA MATERIAL DEFINITION LANGUAGE](https://www.nvidia.com/en-us/design-visualization/technologies/material-definition-language/)
* Maya
  - USD - Plugin
    - [Maya USD Plugin GitHub](https://github.com/Autodesk/maya-usd)
    - MayaにUSDのIOとステージやレイヤーなどのUSD標準機能を実装する。
  - USD - Bifrost : [公式：Reference](https://help.autodesk.com/view/MAYAUL/2023/ENU/?guid=Bifrost_MayaPlugin_bifrost_usd_in_maya_html)
  - [Maya 2023 Bifrost USD Getting Started](https://yamagishi-2bit.blogspot.com/2022/05/maya-biofrost-usd-getting-started-usd.html)
* Houdini(Solaris)
* Max
* Nuke
  * Nukeに関しては「読み込んで編集」という用途を考えていないため、Abcとの違いとかは無いかもしれない。Hydraによりビューの表示は綺麗かも。レンダリングは無関係
* Blender
* Cinema4D

## パイプラインツール
* アセット（ファイル）ブラウザ
* パブリッシュツール
    * チェックツール
    * アセット
    * テクスチャ
        * Tiled、Mipmap、Colorspace、Bake、OIIO
        * [ELEMENTAL RAY : Texture Publishing to mental ray](https://elementalray.wordpress.com/2012/04/17/texture-publishing-to-mental-ray/)
    * ショットカム
* ファイル管理ツール：従属関係の管理
* シーンアッセンブルツール
* レビューツール
    * ShotGrid Client Review
    * ShotGrid Create
    * ShotGrid RV
    * [FTrack：cineSync](https://www.ftrack.com/en/cinesync)
    * Frame.io
    * Blackmagic Cloud(?)
    * Dropbox
* ディスパッチャー
    * Deadline

## ワークフローの構築と共有
- ワークフローの実装、共有がツールの設計思想としてあるツール。
  - Houdini
  - Nuke
  - Fusion

- 一部ワークフローが組みやすいツール
  - Blender(Geometry Node)

- その他ツール

    ツールの仕様的にワークフローの実装が困難であるため、スクリプトやプラグインでワークフローを実装するのが主な手法となる。

  - Maya
  - 3dsMax
  - Cinema4d
  - Adobe製品

    など

### VFXツール
- Maya
    - [Daikin:最新Mayaワークグループ設定について](https://www.comtec.daikin.co.jp/DC/UsersNotes/Ritaro/tutorial/maya_04/)
- Houdini
    - [FX HACK：Houdini Workflowについて](http://fxnomemo.blogspot.com/2021/04/houdini-workflow.html)
- Nuke
    - [関連：Nuke 環境構築まとめ](https://yamagishi-2bit.blogspot.com/2019/02/nuke_6.html)

# テクニカル：
## 参考
* [Disney Research](https://www.disneyresearch.com/)
* Siggraph
* CEDEC
* [DF Talk](https://dftalk.jp/)
    * Degital Frontierさんのテック系の情報発信
## システム
* OS
    * Linux
    * Mac
    * Windows
      * Active Directory

* サーバー

## クラウド
* AWS

## 開発
### 開発環境
* Linuxベース
    * [YouTube : プログラマーを目指す未経験者はWindowsとMacはどちらを使うべきか](https://youtu.be/m1R-lqZs1zs)
### プログラム
* プログラム言語
    * C++
    * Python
        * Jupyter Lab導入
            * クラウド上で動くGoogleのColaboratoryというサービスもある。
        * [python初心者用 基礎演習100本ノック](https://zenn.dev/pell/books/a84eed48e73a6e)
        * [画像処理100本ノック!!](https://github.com/yoyoyo-yo/Gasyori100knock)
        
    * Processing

### Git
* Gitの使い方
  * インストール
* GitHubの使い方
  * リポジトリ作成
  * 初期設定
    * ライセンス
    * 言語
  * README.md
  * .gitignore
  * clone
  * push
  * relase

### Gui
* GUIプログラム
    * Qt
    * MVCフレームワーク
      * [MVC、本当にわかってますか？](https://qiita.com/tshinsay/items/5b1724baf32b8b5113c2)

### Tips
- [試行回数の増やし方 2021 年度版 - Increasing number of attempts ver. 2021](https://speakerdeck.com/butsugiri/increasing-number-of-attempts-ver-2021)


# VFX制作ツール：
## 2D
- Nuke
    - [概要](https://vook.vc/n/4466)
    - [NUKE系リンク集](https://yamagishi-2bit.blogspot.com/2018/10/nuke.html)
- Fusion
- Flame
- AfterEffects
- AVIUTL
- Natron

## 3D
- Maya
  - 開発
    - [PySide2 : MainWindowの取得](https://yamagishi-2bit.blogspot.com/2022/06/maya-python3mainwindow-pyside2.html)
- Houdini
- Blender
- 3dsMax
- Cinema4d

## Player
- RV：OCIOなどにも対応しVFX制作現場ではスタンダードなプレイヤー
- HieroPlayer
- [DJV](https://darbyjohnston.github.io/DJV/index.html)：exrなどの連番にも対応し、LUTなども適用できる。Linux版もある。
- VLC

## Paint & Sculpt
- ZBrush
- 3D Coat
- Sbustance Painter
- Mari
- Adobe
- Affinity
- Clipstudio


## Roto
- Mocha
- SilhouetteFx

## LookDev
- [Gaffer](https://www.gafferhq.org/)
- Katana
- Clarisse iFX
- Solaris(Houdini: Stage - LOP)

## Render
### PathTracer
- [Arnold](https://vook.vc/n/4456)
    - MtoA、HtoA、KtoA
- Redshift
- RenderMan
- Cycle(Blender)
- Octane
- ProRender
- Karma(Houdini)

### Iradiance + PathTracer
- V-Ray(Primaryがパストレース。Secondryにライトキャッシュなど独自のアルゴリズム)

### Scanline
- 3dsMax
- Nuke
    - DeepImageにも対応しており、かなり優秀な印象を受ける。
    - レンダリング結果をそのままコンポジット上でDeepCompositeが出来る。

### Spectral
- [Maxwell](https://maxwellrender.com/)

## Pipeline
- ShotGrid
- Ftrack
- Prism
- Anchorpoint
- Blender Studio

## Edit
- Nuke Studio
- Hiero
- Premier Pro
- DaVinci Resolve
- Blender

## Game Engine
- Unreal Engine
- Unity
    - [Enemies – real-time cinematic teaser | Unity](https://www.youtube.com/watch?v=eXYUNrgqWUU&t=3s)

## Management
- Excel
    - [You Suck at Excel with Joel Spolsky](https://www.youtube.com/watch?v=0nbkaYsR94c)

## Tracking
- PFTrack
- Syntheyes
- Blender

## Photogrametry
- RealityCapture
- Metashape

## HDRI
- PTGui

## Online Meeting
- Google Meet
- Slack
- Zoom
- Discoard
- Gather

## ColorGrading
- DaVinci Resolve
- BaseLight

## Other
* SpeedTree
* [Gigapixel AI：アップコンバーター](https://www.topazlabs.com/gigapixel-ai)
- PureRef

## Program
* C++
    * Qt
* C#
* Rust
* Python
    * [Python3.8から3.10で追加された標準モジュール：Python Standard Library changes in recent years(和訳)](https://yamagishi-2bit.blogspot.com/2022/05/python38310python-standard-library.html)
    * 外部モジュールModules
        * PySide2
        * colour
        * openCV
        * imageio
        * ffmpeg
        * Qt.py

## Code Editor
- Visual Studio Code
    - [VsCodeでマークダウンファイル(.md)を快適に使用するTips](https://maasaablog.com/tools/visual-studio-code/1762/)
      