# 初めてのペア・プログラミング
- 共通補足: 説明文では便宜上「変数x」「変数y」と記載しているが、その変数が何を表すのか分かるように、適切な変数名を付けよう。

<hr>

## ＜目次＞
- <a href="#ex1">演習1: シェルとPythonインタプリタの使用。</a>
  - <a href="#ex1-howto">演習1の進め方</a>
  - <a href="#ex1.1">演習1.1: 作業用ディレクトリの準備。</a>
  - <a href="#ex1.2">演習1.2: 作業用ディレクトリの状態確認。</a>
  - <a href="#ex1.3">演習1.3: Pythonインタプリタを使ってみる。</a>
- <a href="#ex2">演習 2: print()関数と変数の利用。</a>
  - <a href="#ex2-howto">演習2以降の進め方</a>
  - <a href="#ex2.1">演習 2.1: print()関数の利用。</a>
  - <a href="#ex2.2">演習 2.2: 変数を用いたprint()関数の利用。</a>
  - <a href="#ex2.3">演習 2.3: 変数を用いたprint()関数の利用、その2。</a>
  - <a href="#ex2.4">演習 2.4: スクリプトファイルの実行。</a>
- <a href="#ex3">演習3: 数値演算とブーリアンの利用。</a>
  - <a href="#ex3.1">演習 3.1: 変数の利用。</a>
  - <a href="#ex3.2">演習 3.2: 判定してみよう。</a>
  - <a href="#ex3.3">演習 3.3: 判定結果を出力するスクリプトファイルの作成。</a>
- <a href="#ex4">演習4: マニュアル（ヘルプor公式ドキュメント）の利用。</a>
  - <a href="#ex4.1">演習 4.1: help()コマンド・公式ドキュメントの利用。</a>
  - <a href="#ex4.2">演習 4.2: ドキュメントの活用。</a>
  - <a href="#ex4.3">演習 4.3: ドキュメントを踏まえたコード作成。</a>
- <a href="#exx">余裕があるグループ向けのおまけ</a>
  - <a href="#exxX">演習 X: 関数を使ってみよう。</a>
    - <a href="#exxX.1">演習 X.1: 下記コードをインタプリタに入力し、実行してみよう。</a>
    - <a href="#exxX.2">演習 X.2: 関数の仕組みをなんとなく理解できたら、自分で関数を書いてみよう。</a>


<hr>

## <a name="ex1">演習1: シェルとPythonインタプリタの使用。</a>
### <a name="ex1-howto">演習1の進め方</a>
- 演習1については一度 driver, observer を担当して1.1〜1.3までやろう。次に、担当を入れ替えてもう一度1.1〜1.3をやること。（同じ演習を、担当を入れ替えて2回繰り返すことになります）

<hr>

### <a name="ex1.1">演習1.1: 作業用ディレクトリの準備。</a>
- 作業内容
  - ターミナルを起動し、今回演習を作業するためのディレクトリとして「prog1/week2」を作成し、そこに移動せよ。
- ヒント
  - ディレクトリ作成にはmkdirコマンド。ディレクトリの移動にはcd。カレントディレクトリの確認にはpwdコマンドを使おう。
- 補足
  - レポートには、ターミナル上でコマンドを実行した様子と、「prog1/week」に移動したことが分かるように、移動後にカレントディレクトリを確認した結果を掲載すること。

<hr>

### <a name="ex1.2">演習1.2: 作業用ディレクトリの状態確認。</a>
- 作業内容
  - 作成した作業用ディレクトリ「prog1/week2」にはファイルが一つもないはずだ。そのことを確認せよ。
- ヒント
  - ファイル一覧を表示するにはlsコマンドを使おう。
- 補足
  - レポートには、ターミナル上でコマンドを実行した様子を掲載すること。

<hr>

### <a name="ex1.3">演習1.3: Pythonインタプリタを使ってみる。</a>
- 作業内容
  - Pythonインタプリタを起動し、print('test')を実行してからインタプリタを終了せよ。
- レポートには、下記3点の様子を掲載すること。
  - ターミナル上からPythonインタプリタを起動する様子。
  - インタプリタ上でprint()関数を実行する様子。
  - インタプリタを終了して、シェルに戻る様子。

<hr>

## <a name="ex2">演習 2: print()関数と変数の利用。</a>

### <a name="ex2-howto">演習2以降の進め方</a>
- 演習2については「2.1をどちらかがdriverとしてやる。終えたらdriverを交代して2.2をやる」ように交代しながらやろう。
- observerは、直前の内容を把握していないと交代した時に取り組めないはず。わからない場合は質問しよう。

<hr>

### <a name="ex2.1">演習 2.1: print()関数の利用。</a>
- 作業内容
  - 以下のように出力するプログラムを作成せよ。
- 補足
  - 1行毎に1つのprint()文を用いて構わない。
  - 変数は使わず、直接print()文の中にすべての文字列を埋め込んで構わない。
  - レポートにはコードと実行結果を掲載すること。
- 出力したい内容
```
naltoma に遭遇した。
naltoma はレポート課題の始まりを高らかに宣言した。
naltoma は楽しそうに待ち構えている。
```

<hr>

### <a name="ex2.2">演習 2.2: 変数を用いたprint()関数の利用。</a>
- 作業内容
  - naltomaは敵であり、敵はnaltoma以外にも数多く待ち構えている。他の敵にも対応しやすくするため、敵の名前を変数xに保存し、変数xを用いて演習2.1と同様の出力をするように実行するプログラムを作成せよ。
- 補足
  - 変数名は妥当だと思う名称に変更すること。
  - レポートには、コードと実行結果を掲載すること。

<hr>

### <a name="ex2.3">演習 2.3: 変数を用いたprint()関数の利用、その2。</a>
- 作業内容
  - 変数名にTAの名前を代入し、演習 2.2と同じコードで再度出力せよ。この時、出力結果が臨んだ通りに変更されることを確認せよ。
- 補足
  - TAの名前はニックネーム・実名・その他、naltomaと異なる名称であればなんでも構わない。
  - レポートには、コードと実行結果を掲載すること。

<hr>

### <a name="ex2.4">演習 2.4: スクリプトファイルの実行。</a>
- 作業内容
  - 演習2.3のコードを「week2_ex2_3.py」というファイル名で保存し、シェル上で実行せよ。
- 補足
  - ひとまず「シェル＝ターミナル」と考えて良い。Pythonインタプリタではなく、ターミナルで実行すること。
  - レポートには、シェル上で実行する様子と、実行結果を掲載すること。

<hr>

## <a name="ex3">演習3: 数値演算とブーリアンの利用。</a>
### <a name="ex3.1">演習 3.1: 変数の利用。</a>
- 作業内容
  - 出会った敵「naltoma」のレベルは1である。この値を変数xに保存せよ。
- 補足
  - 変数名は適切に命名すること。
  - レポートには、変数に保存するコードを掲載すること。

<hr>

### <a name="ex3.2">演習 3.2: 判定してみよう。</a>
- 作業内容
  - あなたは特殊技「レベル5デス」を使用することができるとしよう。この技は「敵のレベルが5の倍数なら、敵を倒す」ものとする。naltomaを「レベル5デス」で倒すことが可能か判定するために、次の手順で判定せよ。
- 手順
  - [手順1] 敵のレベルを5で割った余りを求め、その結果を変数yに保存する。
  - [手順2] 変数yには5で割った余りが保存されている。これを利用して「5の倍数か否か」を判定する。
  - [手順3] 判定結果をprint()出力する。
- 補足
  - 変数名は適切に命名すること。
  - 判定結果はブール型で出力するものとする。
  - レポートには、手順1〜手順2のコードと実行結果を掲載すること。

<hr>

### <a name="ex3.3">演習 3.3: 判定結果を出力するスクリプトファイルの作成。</a>
- 作業内容
  - 演習3.2のコードを「week2_ex3_3.py」というファイル名で保存し、シェル上で実行せよ。
- 補足
  - レポートには、シェル上で実行する様子と、実行結果を掲載すること。（演習3.2までと同じインタプリタ上ではないことに注意）

<hr>

## <a name="ex4">演習4: マニュアル（ヘルプor公式ドキュメント）の利用。</a>
### <a name="ex4.1">演習 4.1: help()コマンド・公式ドキュメントの利用。</a>
- 作業内容
  - print()関数について、help()コマンドか公式ドキュメントで調べよ。
- 補足
  - レポートには、print()関数について説明している箇所冒頭数行程度を掲載し、分かったこと、分からないことを考察せよ。（分からないことについて減点することはしません）

<hr>

### <a name="ex4.2">演習 4.2: ドキュメントの活用。</a>
- 作業内容
  - 「print('hoge', 'fuga', 'piga')」を実行すると、それぞれの要素が「スペースで連結された文字列」として出力されるはずだ。ことのことについて、help()コマンドもしくは公式ドキュメントではどのように説明しているだろうか。該当箇所を探し出せ。
- 補足
  - レポートには、説明している箇所をコピペすること。

<hr>

### <a name="ex4.3">演習 4.3: ドキュメントを踏まえたコード作成。</a>
- 作業内容
  - 先程は「スペースで連結された文字列」として出力されたが、ここでは連結文字なしに3つの要素を繋げて出力したい。すなわち「hogefugapiga」と出力させたい。print('hogefugapiga')ではなく、連結文字を指定するにはどうしたら良いだろうか。そのコードを「week2_ex4_3.py」というファイル名で保存し、シェル上で実行せよ。
- 補足
  - レポートには、シェル上で実行する様子と、実行結果を掲載すること。（演習4.2までと同じインタプリタ上ではないことに注意）

<hr>

# <a name="exx">余裕があるグループ向けのおまけ</a>
## <a name="exxX">演習 X: 関数を使ってみよう。</a>
### <a name="exxX.1">演習 X.1: 下記コードをインタプリタに入力し、実行してみよう。</a>
```
def encount_enemy(name):
    print(name, 'に遭遇した。')
    print(name, 'はレポート課題の始まりを高らかに宣言した。')
    print(name, 'は楽しそうに待ち構えている。')

encount_enemy(name='naltoma')
encount_enemy(name='TA')
encount_enemy('naltoma')
```
- 補足
  - このコードは「3回print()実行するコードに、encount_enemy() という名前を付けて定義した（この時点ではまだ何も実行されない）。その名前を指定することでコードを実行させた。」という例である。
  - print()関数の前の空白は「半角スペース4つ」で統一しよう。
  - 何もない「空行」は必要です。改行するだけで良いですが、必ず空行を入力してください。

<hr>

### <a name="exxX.2">演習 X.2: 関数の仕組みをなんとなく理解できたら、自分で関数を書いてみよう。</a>