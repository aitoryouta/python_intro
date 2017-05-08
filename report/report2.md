# 課題レポート2: うるう年判定関数を作ってみよう

- ＜目次＞
  - <a href="#abst">課題概要</a>
  - <a href="#howto">取り組み方</a>
  - <a href="#report">レポートに含める内容</a>
  - <a href="#level1">詳細仕様: レベル1「うるう年判定せよ」</a>
  - <a href="#level2">詳細仕様: レベル2「レベル1のコードを関数定義せよ」</a>
  - <a href="#upload">提出方法</a>

<hr>

## <a name="abst">課題概要</a>
- ユーザ入力により、任意の自然数を入力として受け取るものと仮定する。
- 受け取った自然数が、うるう年に該当する年であるか否かを判定してみよう。
- 判定するコードを書けたら、それを関数定義してみよう。

<hr>

## <a name="howto">取り組み方</a>
- ペアや友人らと話し合って取り組んで構わないが、考察は自分自身の考えを述べること。試して分かったこと、自身で解決できなかった部分等についてどう取り組んだか、といった過程がわかるように示すこと。（考えを図表や文章を駆使して表現して報告する練習です）
- 今回からレポートのテンプレートを用意していません。ゼロからレポート作成して下さい。

<hr>

## <a name="report">レポートに含める内容</a>
- レポート作成は当面「googleドキュメント」を使うこと。
- レポートには下記を含めること。
  - **タイトル**
    - 今回は【プログラミング1、レポート課題2: 「うるう年判定関数を作ってみよう」】。
  - **提出日**: yyyy-mm-dd
  - **報告者**: 学籍番号、氏名
    - 複数人で相談しながらやった場合、相談者らを「協力者: 学籍番号、氏名」として示そう。
  - **課題説明**
    - 1,2行程度で課題の内容を説明しよう。
  - **書いたコード**
  - **実行結果**
  - **考察**
    - 課題への取り組みを通し、課題の意義、課題から分かったこと、今後の展望などを述べる。失敗やつまづきがあれば、それらについての失敗分析を含めること。
  - 参考リンク: [実験レポートの書き方](http://www.report.gusoku.net/jikken/jikkenreport.html)
  - その他
    - 通常は感想等をレポートには含めませんが、練習なので課題に取り組みながら何か感じたこと、悩んでいること等、書きたいことがあれば自由に書いてください。（なければ省略OK）

<hr>

## <a name="level1">詳細仕様: レベル1「うるう年判定せよ」</a>
- うるう年判定法
  - 事前情報: 判定したい年を西暦で用意するものとする。西暦は「正の自然数≒（int型オブジェクト）」とする。
  - 判定条件
    - 西暦が4で割り切れる年はうるう年である。
    - ただし、4で割り切れても100で割り切れる年はうるう年ではない。
    - ただし、100で割り切れても400で割り切れる年はうるう年である。
- 出力テンプレート
  - 以下のテンプレートにおいて、
    - **xxx** は、判定したい年とする。
      - 2行目のxxxは、ユーザ入力である。
      - 3行目と4行目のxxxは、読み込んだユーザ入力を確認するための出力文である。
  - うるう年の場合
```
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: xxx
受け取った数値はxxxです。
西暦xxx年は、うるう年です。
```
  - うるう年でない場合（4行目の出力だけが異なる）
```
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: xxx
受け取った数値はxxxです。
西暦xxx年は、うるう年ではありません。
```
- 実行例
  - 以下は、書いたコードを「level1.py」というファイルに保存し、1900, 1992, 2000, 2017の4ケースについて動作確認した例である。
```
oct:tnal% python3 level1.py
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: 1900
受け取った数値は1900です。
西暦1900年は、うるう年ではありません。
oct:tnal% python3 level1.py
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: 1992
受け取った数値は1992です。
西暦1992年は、うるう年です。
oct:tnal% python3 level1.py
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: 2000
受け取った数値は2000です。
西暦2000年は、うるう年です。
oct:tnal% python3 level1.py
うるう年に該当するか否かを判定します。
判定したい年をint型で入力して下さい: 2017
受け取った数値は2017です。
西暦2017年は、うるう年ではありません。
```

- 補足
  - レベル1の時点では、関数定義しなくて良い。
  - 読み込んだ文字列をint型に変換するにはキャストを使おう。
  - 書いたコードを **level1.py** というファイル名で保存し、レポートとは別に提出すること。
  - レポートには1900年と1992年の判定結果を掲載すると共に、そのコードにたどり着くまでにどのような経緯を辿ったか解説すること。

<hr>

## <a name="level2">詳細仕様: レベル2「レベル1のコードを関数定義せよ」</a>
- レベル1ではうるう年判定するコードを書き、level1.pyというファイル名で保存したはずだ。
- レベル2ではレベル1のコードを参考に、以下の仕様を満たす関数を定義せよ。
- 仕様
  - 関数名: **judge_leap_year**
  - 入力（引数）
    - なし
  - 処理
    - うるう年判定。レベル1と同様の出力を伴うこと。
  - 戻り値
    - **うるう年判定結果（bool型オブジェクト）**。うるう年である場合にはTrueを返し、そうでない場合にはFalseを返すこと。
- 補足
  - 動作確認のための追加コードについて
    - 関数定義だけではコードが正しく動作するか判断できない。そこで、
      - (1) 関数定義をした後で、下記1行のコードを追加すること。
      - (2) 動作確認のため、ターミナルからファイル実行する形で実行せよ。この時、レベル1と同じ結果が得られることを確認せよ。
```
judge_leap_year()
```
  - 書いたコードを **level2.py** というファイル名で保存し、レポートとは別に提出すること。
  - レポートには1900年と1992年の判定結果を掲載すると共に、そのコードにたどり着くまでにどのような経緯を辿ったか解説すること。
  - レベル1の「ファイル保存しただけのコード」とレベル2の「関数定義したコード」の違いについて、考察せよ。


<hr>

## <a name="upload">提出方法</a>
- 提出物は、作成した「ソースファイル（level1.py, level2.py）と、「レポートファイル（report2）」である。レポートはgoogleドキュメントで作成すること。
- レポートは電子ファイルで提出するものとする。
  - google drive の「report2」の中に、各自のアカウント名でフォルダを作成せよ。（e175701の学生は、e175701というフォルダを作成せよ）
  - 作成したフォルダに、前述の提出物をアップロードせよ。
- レポートのファイル名を「report2」とする。
- 提出先＆〆切: 授業ページを参照。