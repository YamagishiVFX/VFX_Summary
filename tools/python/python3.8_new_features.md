# Python Standard Library changes in recent years

## 引用:
Python Standard Library changes in recent years
- https://antonz.org/python-stdlib-changes/

あまり注目されない、3.8から3.10で導入された標準モジュールの新機能を紹介するよ。


記事中のすべての新機能と改良点には、例が添えられています。プレイグラウンドで試すこともできますし、ローカルで実行することもできます。ローカルに古い Python がある場合は、Docker を使って実行してください。

```
$ docker run -it --rm python:3.10-alpine
```
# array
[array](https://docs.python.org/3/library/array) module provides compact typed numeric arrays. It is used much less frequently than the famous list counterpart.

array.index() methods finds the value in the array and returns the index of the found element. Now it supports optional start and stop parameters, which define the search interval (3.10+):

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

It received a couple of new functions: [b32hexencode()](https://docs.python.org/3/library/base64#base64.b32hexencode) and [b32hexdecode()](https://docs.python.org/3/library/base64#base64.b32hexdecode), which use an extended 32-character alphabet according to [RFC 4648](https://datatracker.ietf.org/doc/html/rfc4648.html#section-7) (3.10+):

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

functools
functools module is a collection of higher-order auxiliary functions. One of them is lru_cache(), which caches expensive calculations:

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
Previously, it required to explicitly set the cache size. And now you can specify @lru_cache without arguments, using the default size of 128 (3.8+).

Besides, you can get the cache parameters (3.9+):

find_user.cache_parameters()
# {'maxsize': 256, 'typed': False}
If you don’t mind the memory usage, you can use the unlimited @cache instead of @lru_cache (3.9+).

New @cached_property decorator caches the calculated object property (3.8+):

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
And @singledispatchmethod overloads the method depending on the parameter type (3.8+):

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
Smells like Java to me.

playground

Contributed by: Raymond Hettinger • Carl Meyer • Ethan Smith

glob
glob module searches for files and directories that match the template.

Now thanks to the root_dir parameter in glob() and iglob() functions you can specify the root directory of the search (3.10+):

import glob
import os

os.getcwd()
# '/'

glob.glob("*", root_dir="/usr")
# ['local', 'share', 'bin', 'lib', 'sbin', 'src']
It’s a small thing, but it’s nice.

playground

Contributed by: Serhiy Storchaka

graphlib
graphlib module works with graphs. And you know what? This is a brand-new module! (3.9+)

So far, it has only one feature — topological graph sorting (an ordering of vertices such that for any u → v, the vertex u comes before v):

from graphlib import TopologicalSorter

graph = {"Diane": {"Bob", "Cindy"}, "Cindy": {"Alice"}, "Bob": {"Alice"}}
# Alice → Bob → Diane
#     ↳ Cindy ↗

sorter = TopologicalSorter(graph)
list(sorter.static_order())
# ['Alice', 'Cindy', 'Bob', 'Diane']
playground

Contributed by: Pablo Galindo • Tim Peters • Larry Hastings

itertools
itertools module provides a variety of iterators for memory-efficient collection processing.

One of them is the accumulate() function, which calculates the rolling aggregate. Now it allows the initial parameter, which sets the initial value (3.8+):

import itertools

seq = [7, 11, 19, 42]

accumulator = itertools.accumulate(seq)
list(accumulator)
# [7, 18, 37, 79]

accumulator = itertools.accumulate(seq, initial=100)
list(accumulator)
# [100, 107, 118, 137, 179]
And the shiny new pairwise() function traverses the collection and yields pairs of consecutive elements (3.10+):

import itertools

seq = [7, 11, 19, 42]
pairer = itertools.pairwise(seq)

list(pairer)
# [(7, 11), (11, 19), (19, 42)]
playground

Contributed by: Lisa Roach • Raymond Hettinger

math
math module includes an abundance of mathematical functions.

There are a lot of news here:

dist() calculates the Euclidean distance between points (3.8+);
perm() and comb() count the number of permutations and combinations (3.8+);
lcm() computes the least common multiple (3.9+);
gcd() now computes the greatest common divisor for an arbitrary number of arguments (3.9+).
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
And prod() multiplies the sequence elements (3.8+):

import math

seq = range(3, 9)
math.prod(seq)
# 20160
playground

Contributed by: Raymond Hettinger • Yash Aggarwal • Keller Fuchs • Serhiy Storchaka • Mark Dickinson • Ananthakrishnan • Pablo Galindo

random
random module handles random numbers.

New randbytes() method generates a random byte string (3.9+):

import random

random.randbytes(4)
# b'\x8b\xd4\x8f\xc9'
playground

Contributed by: Victor Stinner

shlex
shlex module splits the string into tokens according to the Unix command line rules.

And now it also joins the tokens back into the string — thanks to the join() function (3.8+):

import shlex

tokens = ["echo", "-n", "Python is awesome"]
shlex.join(tokens)
# "echo -n 'Python is awesome'"
playground

Contributed by: Bo Bayles

shutil
shutil module works with files and directories: copies, moves and deletes them.

Copying directories has now become a little more convenient — kudos to the dirs_exist_ok parameter in the copytree() function (3.8+). If it is on, the function allows the target directory to exist:

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
playground

Contributed by: Josh Bronson

statistics
statistics module handles mathematical statistics. Like math, it has greatly improved in recent releases. Not scipy yet, but it’s not the kindergarten version Python had in 3.4.

See for yourself:

fmean() computes the arithmetic mean (like mean(), only faster) (3.8+);
geometric_mean() computes the geometric mean (3.8+);
multimode() returns the modes (the most frequent values in the dataset), even if there are multiple ones (in contrast to mode()) (3.8+);
quantiles() splits the dataset into quantiles and returns the cut points (3.8+).
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
NormalDist describes the normal distribution of a random variable (3.8+):

from statistics import NormalDist

birth_weights = NormalDist.from_samples([2.5, 3.1, 2.1, 2.4, 2.7, 3.5])
drug_effects = NormalDist(0.4, 0.15)
combined = birth_weights + drug_effects

round(combined.mean, 1)
# 3.1

round(combined.stdev, 1)
# 0.5
The module received Pearson correlation() and covariance() functions (3.10+):

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
And even the linear_regression() calculator (3.10+):

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
By the way, the statistics module is also famous for its excellent documentation. Check it out.

playground

Contributed by: Raymond Hettinger • Steven D’Aprano • Timothy Wolodzko

zoneinfo
zoneinfo module provides information about time zones around the world. Another new module! (3.9+)

Before the zoneinfo appearance, Python had a single ascetic timezone.utc time zone. Well, not anymore:

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
playground

Contributed by: Paul Ganssle

Summary
We have reviewed as many as 17 modules contributed by 27 devs — and this is without taking into account asyncio, typing and many other lower-level ones. As you can see, the standard library is actively developing. And the new features are quite reasonable. I hope you will find the described novelties useful!

I would also like to specifically thank the contributors for their amazing work:

Carl Meyer for the functools.cached_property() decorator;
Dennis Sweeney for the str.removeprefix() and str.removesuffix() methods;
Ethan Smith for the functools.singledispatchmethod() decorator;
Filipe Laíns for the base64.b32hexencode() and base64.b32hexdecode() functions;
Lisa Roach for the Fraction.as_integer_ratio() method and itertools.accumulate() improvements;
Niklas Fiekas for the int.bit_count() method;
Pablo Galindo for the whole graphlib module and math.prod() function;
Paul Ganssle for the whole zoneinfo module;
Raymond Hettinger for lots of functions in the statistics module, itertools.pairwise() function, key parameter in the bisect module and his community work;
Serhiy Storchaka and Yash Aggarwal for the combinatorics in the math module;
Timothy Wolodzko for the covariance(), correlation(), and linear_regression() functions in the statistics module;
Victor Stinner for the random.randbytes() method.