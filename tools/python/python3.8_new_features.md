# Python3.8から3.10で追加された標準モジュール：Python Standard Library changes in recent years(和訳)

翻訳：DeepL翻訳 https://www.deepl.com/translator

Created v1 2022/05/28


## 引用:
Python Standard Library changes in recent years
- https://antonz.org/python-stdlib-changes/

あまり注目されない、3.8から3.10で導入された標準モジュールの新機能を紹介するよ。


記事中のすべての新機能と改良点には、例が添えられています。プレイグラウンドで試すこともできますし、ローカルで実行することもできます。ローカルに古い Python がある場合は、Docker を使って実行してください。

```
$ docker run -it --rm python:3.10-alpine
```


# array
[array](https://docs.python.org/3/library/array) モジュールはコンパクトな数値配列の型付けを行います。有名なリストに比べて使用頻度は低いです。

[array.index()](https://docs.python.org/3/library/array#array.array.index) メソッドは、配列内の値を検索し、見つかった要素のインデックスを返します。オプションで start と stop パラメータを指定できるようになり、検索間隔を定義できるようになりました (3.10+):

```Python
from array import array
arr = array("i", [7, 11, 19, 42])

idx = arr.index(11)
# idx == 1

idx = arr.index(11, 2)
# ValueError: array.index(x): x not in array
```

[playground](https://stepik.org/lesson/717024/step/2)

Contributed by: Anders Lorentsen • Zackery Spytz

# base64
[base64](https://docs.python.org/3/library/base64) モジュールは、Base16、Base32、Base64アルゴリズムを使ってバイナリデータをASCII文字列にエンコードするモジュールです。

[b32hexencode()](https://docs.python.org/3/library/base64#base64.b32hexencode) と [b32hexdecode()](https://docs.python.org/3/library/base64#base64.b32hexdecode) は、[RFC 4648](https://datatracker.ietf.org/doc/html/rfc4648.html#section-7) (3.10+) に従って拡張された 32 文字のアルファベットを使う新しい関数です。

```Python
import base64
bytes = b"python is awesome"

base64.b32encode(bytes)
# b'OB4XI2DPNYQGS4ZAMF3WK43PNVSQ===='

base64.b32hexencode(bytes)
# b'E1SN8Q3FDOG6ISP0C5RMASRFDLIG===='
```
[playground](https://stepik.org/lesson/717024/step/3)


# bisect
[bisect](https://docs.python.org/3/library/bisect) モジュールは、バイナリサーチ法を用いてソートされたリストを処理します。主な機能は以下の通りです。

- [bisect()](https://docs.python.org/3/library/bisect#bisect.bisect) リストの中の項目を見つける。
- [insort()](https://docs.python.org/3/library/bisect#bisect.insort) 順序を保持したまま項目を追加します。.

```Python
import bisect

lst = [7, 11, 19, 42]
idx = bisect.bisect(lst, 12)
# idx == 2

bisect.insort(lst, 12)
# [7, 11, 12, 19, 42]
```

バージョン3.10以降、すべてのモジュール関数がオプションのkeyパラメータをサポートしています。これはリストアイテムの値を返す関数です。要素を直接比較できない場合に使用すると便利です。

```Python
import bisect
import operator

p1 = {"id": 11, "name": "Diane"}
p2 = {"id": 12, "name": "Bob"}
p3 = {"id": 13, "name": "Emma"}

key = operator.itemgetter("name")
people = sorted([p1, p2, p3], key=key)
# Bob, Diane, Emma

idx = bisect.bisect(people, "Dan")
# TypeError: '<' not supported between instances of 'str' and 'dict'

idx = bisect.bisect(people, "Dan", key=key)
# idx == 1
```
[playground](https://stepik.org/lesson/717024/step/4)


# builtins
[builtins](https://docs.python.org/3/library/builtins) モジュールには、プログラマが import なしで使用するすべての組み込み関数とクラスが含まれています： int, list, len(), open() など。

```Python
import builtins

list is builtins.list
# True

len is builtins.len
# True
```

**str** が [str.removeprefix()](https://docs.python.org/3/library/stdtypes#str.removeprefix)、 [str.removesuffix()](https://docs.python.org/3/library/stdtypes#str.removesuffix) メソッドを受け、それぞれ文字列の先頭と末尾が切り落とされました（3.+）。

```Python
s = "Python is awesome"

s.removeprefix("Python is ")
# 'awesome'

s.removesuffix(" is awesome")
# 'Python'
```


**intger** は [int.bit_count()](https://docs.python.org/3/library/stdtypes#int.bit_count) メソッドを受け取り、整数のバイナリ表現における 1 の数を返します (3.10+):

```Python
n = 42

bin(n)
# '0b101010'

n.bit_count()
# 3
```

**dictionary** のメソッドである `dict.key()`、`dict.values()`、`dict.items()` は、辞書データを参照するビューオブジェクトを返します。以前は、これらのオブジェクトから辞書への逆リンクを取得することは不可能でしたが、現在はそれが可能です - .mapping 属性を介して (3.10+):

```Python
people = {
    "Diane": 70,
    "Bob": 78,
    "Emma": 84
}

keys = people.keys()
# dict_keys(['Diane', 'Bob', 'Emma'])

keys.mapping["Bob"]
# 78
```

# Collection merging
 [zip()](https://docs.python.org/3/library/functions#zip) 関数に `strict` パラメータが追加されました。これは、配列が同じ長さであることを保証するものです (3.10+)。

```Python
keys = ["Diane", "Bob", "Emma"]
vals = [70, 78, 84, 42]

pairs = zip(keys, vals)
list(pairs)
# [('Diane', 70), ('Bob', 78), ('Emma', 84)]

pairs = zip(keys, vals, strict=True)
list(pairs)
# ValueError: zip() argument 2 is longer than argument 1
```
[playground](https://stepik.org/lesson/717024/step/5)

Contributed by: Dennis Sweeney • Niklas Fiekas • Brandt Bucher

# dataclasses
[dataclasses](https://docs.python.org/3/library/dataclasses) モジュールは、仕様にしたがってクラスを生成します。

Dataclasses can now use slots, which are great for creating compact data objects with a fixed set of properties (3.10+).

Regular dataclass:
```Python
from dataclasses import dataclass

@dataclass
class Person:
    id: int
    name: str

diane = Person(id=11, name="Diane")
diane.__dict__
# {'id': 11, 'name': 'Diane'}
diane.salary = 70
# ok
```
Dataclass with slots:
```Python
from dataclasses import dataclass

@dataclass(slots=True)
class SlotPerson:
    id: int
    name: str

bob = SlotPerson(id=12, name="Bob")
bob.__dict__
# AttributeError: 'SlotPerson' object has no attribute '__dict__'
bob.__slots__
# ('id', 'name')
bob.salary = 78
# AttributeError: 'SlotPerson' object has no attribute 'salary'
```

そのほか、オブジェクトを作成する際に、データクラスがキーワードのみのパラメータを受け付けるように強制できるようになりました (3.10以上)。
```Python
from dataclasses import dataclass

@dataclass(kw_only=True)
class KeywordPerson:
    id: int
    name: str

diane = KeywordPerson(id=11, name="Diane")
# ok
diane = KeywordPerson(11, "Diane")
# TypeError: KeywordPerson.__init__() takes 1 positional argument but 3 were given
```
[playground](https://stepik.org/lesson/717024/step/6)

Contributed by: Yurii Karabas • Eric V. Smith

# datetime
[datetime](https://docs.python.org/3/library/datetime) 日付と時刻を扱います。

新しい [date.fromisocalendar()](https://docs.python.org/3/library/datetime#datetime.date.fromisocalendar) と [datetime.fromisocalendar()](https://docs.python.org/3/library/datetime#datetime.datetime.fromisocalendar) コンストラクタを受け取り、 (year, week, week_day) のトリオから日付を作成します (3.8+):

```Python
import datetime as dt

day = dt.date(2022, 9, 13)
day.isocalendar()
# datetime.IsoCalendarDate(year=2022, week=37, weekday=2)

year, week, day = day.isocalendar()
next_day = dt.date.fromisocalendar(year, week, day+1)
# datetime.date(2022, 9, 14)
```

さらに、`.isocalendar()` メソッドは、通常のタプルではなく、`IsoCalendarDate` という名前のものを返すようになりました (3.9+)。上の例で見ることができます。

[playground](https://stepik.org/lesson/717024/step/7)

# fractions
[fractions](https://docs.python.org/3/library/fractions) モジュールは有理数で動作します。

[Fraction.as_integer_ratio()](https://docs.python.org/3/library/fractions#fractions.Fraction.as_integer_ratio) メソッドを受け取り、分数を (分子、分母) のペアとして返すことで、通常の float (3.8+) の長年の欠点を修正しました。

```Python
(0.25).as_integer_ratio()
# (1, 4)

(0.5).as_integer_ratio()
# (1, 2)

(0.2).as_integer_ratio()
# (3602879701896397, 18014398509481984)
# oopsie
```
```Python
from fractions import Fraction

Fraction("0.2").as_integer_ratio()
# (1, 5)
# so much better
```
`decimal.Decimal` は3.6でこれを習得しています。しかし、それはまだ素晴らしいことです。

[playground](https://stepik.org/lesson/717024/step/8)

Contributed by: Lisa Roach • Raymond Hettinger

# functools
[functools](https://docs.python.org/3/library/functools) モジュールは、高次の補助関数のコレクションです。そのうちのひとつが [lru_cache()](https://docs.python.org/3/library/functools#functools.lru_cache) で、これは高価な計算をキャッシュするものです。

```Python
import functools
import time

@functools.lru_cache(maxsize=256)
def find_user(name):
    # imitating slow search
    time.sleep(1)
    user = {"id": 11, "name": "Diane"}
    return user

find_user("Diane")
# kinda slow

find_user("Diane")
# blazingly fast
```

以前は、明示的にキャッシュサイズを設定する必要がありました。そして今回、 `@lru_cache` を引数なしで指定できるようになり、デフォルトのサイズである `128` を使用できるようになりました (3.8+) 。

さらに、キャッシュのパラメータを取得できるようになりました(3.9+)。

Besides, you can get the cache parameters (3.9+):

```Python
find_user.cache_parameters()
# {'maxsize': 256, 'typed': False}
```

メモリ使用量を気にしないのであれば、`@lru_cache` の代わりに無制限の `@cache` を使うこともできます (3.9 以上)。

新しい [@cached_property](https://docs.python.org/3/library/functools#functools.cached_property) デコレーターは、計算されたオブジェクトプロパティをキャッシュします (3.8+) 。

``` Python
import functools
import statistics

class Dataset:
    def __init__(self, seq):
        self._data = tuple(seq)

    @functools.cached_property
    def stdev(self):
        return statistics.stdev(self._data)

dataset = Dataset(range(1_000_000))

dataset.stdev
# kinda slow

dataset.stdev
# blazingly fast
```

また、[@singledispatchmethod](https://docs.python.org/3/library/functools#functools.singledispatchmethod) はパラメータの型によってメソッドをオーバーロードします(3.8+)。

```Python
import functools

class Divider:
    @functools.singledispatchmethod
    def divide(self, dividend, divisor):
        raise NotImplementedError("Do not know how to divide those")

    @divide.register
    def _(self, dividend: int, divisor: int):
        return dividend // divisor

    @divide.register
    def _(self, dividend: str, divisor: int):
        # this is really stupid, I know
        newlen = len(dividend) // divisor
        return dividend[:newlen]

divider = Divider()
divider.divide(10, 2)
# 5

divider.divide("hello world", 2)
# 'hello'
```

Smells like Java to me.

[playground](https://stepik.org/lesson/717024/step/9)

# glob
[glob](https://docs.python.org/3/library/glob) globモジュールは、テンプレートにマッチするファイルやディレクトリを検索します。

[glob()](https://docs.python.org/3/library/glob#glob.glob) および [iglob()](https://docs.python.org/3/library/glob#glob.iglob) 関数の `root_dir` パラメータにより、検索対象のルートディレクトリを指定できるようになりました (3.10+):

```Python
import glob
import os

os.getcwd()
# '/'

glob.glob("*", root_dir="/usr")
# ['local', 'share', 'bin', 'lib', 'sbin', 'src']
```
It’s a small thing, but it’s nice.

[playground](https://stepik.org/lesson/717024/step/10)

Contributed by: Serhiy Storchaka

# graphlib
[graphlib](https://docs.python.org/3/library/graphlib) モジュールはグラフを扱います。そして、ご存知でしょうか？これは全く新しいモジュールなのです (3.9+)

今のところ、トポロジカルグラフソーティング（任意の `u→v` に対して、頂点 `u` が `v` の前に来るような頂点の順序付け）の機能しか持っていない。

```Python
from graphlib import TopologicalSorter

graph = {"Diane": {"Bob", "Cindy"}, "Cindy": {"Alice"}, "Bob": {"Alice"}}
# Alice → Bob → Diane
#     ↳ Cindy ↗

sorter = TopologicalSorter(graph)
list(sorter.static_order())
# ['Alice', 'Cindy', 'Bob', 'Diane']
```
[playground](https://stepik.org/lesson/717025/step/2)

# itertools
[itertools](https://docs.python.org/3/library/itertools)モジュールは、メモリ効率の良いコレクション処理のための様々なイテレータを提供します。

そのうちの1つは、ローリングアグリゲートを計算する [accumulate()](https://docs.python.org/3/library/itertools#itertools.accumulate) 関数です。初期値(3.8以上)を設定するinitialパラメータが使えるようになりました。

```Python
import itertools

seq = [7, 11, 19, 42]

accumulator = itertools.accumulate(seq)
list(accumulator)
# [7, 18, 37, 79]

accumulator = itertools.accumulate(seq, initial=100)
list(accumulator)
# [100, 107, 118, 137, 179]
```

そして、ピカピカの新しい [pairwise()](https://docs.python.org/3/library/itertools#itertools.pairwise) 関数は、コレクションを横断して、連続した要素のペアを生成します(3.10+)。

```Python
import itertools

seq = [7, 11, 19, 42]
pairer = itertools.pairwise(seq)

list(pairer)
# [(7, 11), (11, 19), (19, 42)]
```
[playground](https://stepik.org/lesson/717025/step/3)

# math
[math](https://docs.python.org/3/library/math)モジュールには、豊富な数学関数が含まれています。

ここには、たくさんのニュースがあります。

- [dist()](https://docs.python.org/3/library/math#math.dist) calculates the Euclidean distance between points (3.8+);
- [perm()](https://docs.python.org/3/library/math#math.perm) and [comb()](https://docs.python.org/3/library/math#math.comb) count the number of permutations and combinations (3.8+);
- [lcm()](https://docs.python.org/3/library/math#math.lcm) computes the least common multiple (3.9+);
- [gcd()](https://docs.python.org/3/library/math#math.gcd) now computes the greatest common divisor for an arbitrary number of arguments (3.9+).

```Python
import math

math.dist((1,1), (4, 5))
# 5.0

math.perm(5, 2)
# 20

math.comb(5, 2)
# 10

math.lcm(9, 27, 60)
# 540

math.gcd(9, 27, 60)
# 3
```

そして、[prod()](https://docs.python.org/3/library/math#math.prod)は配列の要素(3.8+)を掛け合わせる。

```Python
import math

seq = range(3, 9)
math.prod(seq)
# 20160
```
[playground](https://stepik.org/lesson/717025/step/4)


# random
[random](https://docs.python.org/3/library/random) モジュールは乱数を扱います。

新しい[randbytes()](https://docs.python.org/3/library/random#random.randbytes)メソッドはランダムなバイト列を生成します(3.9以上)。

```Python
import random

random.randbytes(4)
# b'\x8b\xd4\x8f\xc9'
```
[playground](https://stepik.org/lesson/717025/step/5)


# shlex
[shlex](https://docs.python.org/3/library/shlex)モジュールは、Unixのコマンドラインの規則に従って文字列をトークンに分割します。

また、[join()](https://docs.python.org/3/library/shlex#shlex.join) 関数のおかげで、トークンを文字列に結合することもできるようになりました(3.8+)。

```Python
import shlex

tokens = ["echo", "-n", "Python is awesome"]
shlex.join(tokens)
# "echo -n 'Python is awesome'"
```
[playground](https://stepik.org/lesson/717025/step/6)


# shutil
[shutil](https://docs.python.org/3/library/shutil) モジュールはファイルとディレクトリを扱います: それらをコピー、移動、削除します。

[copytree()](https://docs.python.org/3/library/shutil#shutil.copytree) 関数 (3.8+) の dirs_exist_ok パラメータのおかげで、ディレクトリのコピーも少し便利になりました。このパラメータがオンの場合、この関数はターゲットディレクトリが存在することを許可します。

```Python
from pathlib import Path
import shutil

tmp = Path("/tmp")

src = tmp.joinpath("src")
src.mkdir()
src.joinpath("src.txt").touch()
# /tmp/src
# /tmp/src/src.txt

dst = tmp.joinpath("dst")
dst.mkdir()
# /tmp/dst

shutil.copytree(src, dst)
# FileExistsError: [Errno 17] File exists: '/tmp/dst'
shutil.copytree(src, dst, dirs_exist_ok=True)
# PosixPath('/tmp/dst')
```

[playground](https://stepik.org/lesson/717025/step/7)


# statistics
[statistics](statistics モジュールは、数学的な統計を扱います。`math` と同様に、最近のリリースで大きく改善されました。まだ `scipy` ではありませんが、Pythonが3.4で持っていた幼稚園のバージョンではありません。

自分の目で確かめてください。

- [fmean()](https://docs.python.org/3/library/statistics#statistics.fmean) は算術平均を計算します(mean()のように、より速く) (3.8+)。
- [geometric_mean()](https://docs.python.org/3/library/statistics#statistics.geometric_mean) は幾何平均を計算します (3.8+)。
- [multimode()](https://docs.python.org/3/library/statistics#statistics.multimode) は，複数の値がある場合でもモード（データセット内で最も頻度の高い値）を返す (mode() とは対照的) (3.8+);
- [quantiles()](https://docs.python.org/3/library/statistics#statistics.quantiles) は、データセットを分位数に分割し、そのカットポイントを返す (3.8+).) モジュールは、数学的な統計を扱います。数学と同様に、最近のリリースで大きく改善されました。まだscipyではありませんが、Pythonが3.4で持っていた幼稚園のバージョンではありません。

自分の目で確かめてください。

fmean() は算術平均を計算します(mean()のように、より速く) (3.8+)。
geometric_mean() は幾何平均を計算します (3.8+)。
multimode() は，複数の値がある場合でもモード（データセット内で最も頻度の高い値）を返す (mode() とは対照的) (3.8+);
quantiles() は、データセットを分位数に分割し、そのカットポイントを返す (3.8+).

```
import statistics

seq = list(range(1, 10))

statistics.fmean(seq)
# 5.0

statistics.geometric_mean(seq)
# 4.147166274396913

statistics.multimode(seq)
# [1, 2, 3, 4, 5, 6, 7, 8, 9]
statistics.multimode("python is awesome")
# ['o', ' ', 's', 'e']

statistics.quantiles(seq)
# [2.5, 5.0, 7.5]
```

[NormalDist](https://docs.python.org/3/library/statistics#statistics.NormalDist) は、確率変数の正規分布を記述します(3.8+)。

```Python
from statistics import NormalDist

birth_weights = NormalDist.from_samples([2.5, 3.1, 2.1, 2.4, 2.7, 3.5])
drug_effects = NormalDist(0.4, 0.15)
combined = birth_weights + drug_effects

round(combined.mean, 1)
# 3.1

round(combined.stdev, 1)
# 0.5
```

Pearson [correlation()](https://docs.python.org/3/library/statistics#statistics.correlation) と[covariance()](https://docs.python.org/3/library/statistics#statistics.covariance) 関数が追加されました。

```Python
import statistics

x = [1, 2, 3, 4, 5, 6, 7, 8, 9]
y = [9, 8, 7, 6, 5, 4, 3, 2, 1]

statistics.correlation(x, x)
# 1.0

statistics.correlation(x, y)
# -1.0

statistics.covariance(x, x)
# 7.5

statistics.covariance(x, y)
# -7.5
```

そして、[linear_regression()](https://docs.python.org/3/library/statistics#statistics.linear_regression) 電卓(3.10+)。

```Python
import statistics

movies_by_year = {
    2000: 371,
    2003: 507,
    2006: 608,
    2009: 520,
    2012: 669,
    2015: 708,
    2018: 873,
    2021: 403,
}

x = movies_by_year.keys()
y = movies_by_year.values()
slope, intercept = statistics.linear_regression(x, y)

year_2022 = round(slope * 2022 + intercept)
# 697
```

ちなみに、`statistics` モジュールは、ドキュメントが充実していることでも有名です。調べてみてください。

[playground](https://stepik.org/lesson/717025/step/8)


# zoneinfo
[zoneinfo](https://docs.python.org/3/library/zoneinfo) モジュールは、世界中のタイムゾーンの情報を提供します。もう一つの新しいモジュール! (3.9+)

`zoneinfo` が登場する前、Python は単一の禁欲的な `timezone.utc` タイムゾーンを備えていました。さて、もうそうではありません。

```Python
import datetime as dt
from zoneinfo import ZoneInfo

utc = dt.datetime(2022, 9, 13, hour=21, tzinfo=dt.timezone.utc)
# 2022-09-13 21:00:00+00:00

paris = utc.astimezone(ZoneInfo("Europe/Paris"))
# 2022-09-13 23:00:00+02:00

tokyo = utc.astimezone(ZoneInfo("Asia/Tokyo"))
# 2022-09-14 06:00:00+09:00

sydney = utc.astimezone(ZoneInfo("Australia/Sydney"))
# 2022-09-14 07:00:00+10:00
```

[playground](https://stepik.org/lesson/717025/step/9)


# Summary
私たちは、27人の開発者から提供された17ものモジュールをレビューしました。これは、asyncioやtyping、その他多くの低レベルのものを考慮に入れていません。見ての通り、標準ライブラリは活発に開発されている。そして、新機能は非常に合理的です。私は、あなたが記述された新機能を有用と感じることを願っています!

また、特に貢献者の方々の素晴らしい仕事ぶりに感謝したいと思います。

> We have reviewed as many as 17 modules contributed by 27 devs — and this is without taking into account asyncio, typing and many other lower-level ones. As you can see, the standard library is actively developing. And the new features are quite reasonable. I hope you will find the described novelties useful!
> 
> I would also like to specifically thank the contributors for their amazing work:

- [Carl Meyer](https://twitter.com/carljm) for the `functools.cached_property()` decorator;
- [Dennis Sweeney](https://github.com/sweeneyde) for the `str.removeprefix()` and `str.removesuffix()` methods;
- [Ethan Smith](https://twitter.com/ethanhs) for the `functools.singledispatchmethod()` decorator;
- [Filipe Laíns](https://twitter.com/missingclara) for the `base64.b32hexencode()` and `base64.b32hexdecode()` functions;
- [Lisa Roach](https://twitter.com/lisroach) for the `Fraction.as_integer_ratio()` method and `itertools.accumulate()` improvements;
- [Niklas Fiekas](https://twitter.com/niklasfiekas) for the `int.bit_count()` method;
- [Pablo Galindo](https://twitter.com/pyblogsal) for the whole graphlib module and `math.prod()` function;
- [Paul Ganssle](https://twitter.com/pganssle) for the whole `zoneinfo` module;
- [Raymond Hettinger](https://twitter.com/raymondh) for lots of functions in the `statistics` module, `itertools.pairwise()` function, `key` parameter in the `bisect` module and his community work;
- [Serhiy Storchaka](https://twitter.com/serhiystorchaka) and [Yash Aggarwal](https://github.com/FR4NKESTI3N) for the combinatorics in the `math` module;
- [Timothy Wolodzko](https://twitter.com/tymwol) for the `covariance()`, `correlation()`, and `linear_regression()` functions in the `statistics` module;
- [Victor Stinner](https://twitter.com/victorstinner) for the `random.randbytes()` method.