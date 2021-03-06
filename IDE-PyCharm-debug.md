# PyCharmを使ってみよう（デバッグ入門編）
- 背景
  - デバッグ実行時に、細かく動作確認したいなら[Thonny](https://github.com/naltoma/python_intro/blob/master/IDE-Thonny-Debug.md)を使おう。
  - 行単位で問題ないなら、より一般的なIDEである[PyCharm](https://www.jetbrains.com/pycharm/)をオススメ。
    - 主な特徴
      - デバッグ実行は行単位。どこで停止してほしいかを詳細に設定可能。
        - 例えば「while文で条件がxxの時に停止」といった設定も可能。今回は一番シンプルな「breakpointの設定」だけをやります。
      - バージョン管理システム、テストサポート等も充実。
- ＜目次＞
  - <a href="#init">環境構築、起動、初期設定</a>
  - <a href="#debug">コード例でデバッグ実行してみる</a>
  - <a href="#frame">スタックフレームの移動と確認</a>
  - <a href="#note">注意</a>

<hr>

## <a name="init">環境構築、起動、初期設定</a>
1. ダウンロード
  - [PyCharm公式サイト](https://www.jetbrains.com/pycharm/) -> Download -> Community版 (188MB)をダウンロード。
2. インストール
  - ダウンロードしたdmgファイルをダブルクリック。
  - 「アプリケーション」フォルダに、ドラッグ＆ドロップ。
3. アプリの起動
  - 「アプリケーション」フォルダにある「PyCharm CE」を実行。
4. 初期設定
  - Pythonインタプリタの設定
    - PyCharm CEが起動したら、左上のPyCharmメニューから「Preferences...」を選択。
    - 左の「Project Interpreter」を選択。
    - 右上の「...」を選択し、「Add Local」を選択。
    - 「/usr/bin/python」と書かれている箇所を削除し、/usr/local/bin/python3を選択。
      - 一番上までスクロールし、/が見えたらそれをダブルクリック。
      - /から、/usr/ -> /usr/local/ -> /usr/local/bin/ -> /usr/local/bin/python3と辿っていく。
      - 右下のOKを選択。
    - 右下の「Apply」をクリックし、「OK」をクリック。（設定画面が閉じて、設定が始まる）
  - PyCharmで利用するディレクトリを用意
    - ターミナルを起動し、mkdir PycharmProjectsを実行。

<hr>

## <a name="debug">コード例でデバッグ実行してみる</a>
- 今回の流れ
  - コード例を用意。
  - PyCharmで開く。
  - 通常実行してみる。
  - 設定無しでデバッグ実行してみる。
  - breakpointsを設定してデバッグ実行してみる。
- コード例を用意。
  - コードをダウンロード。  
    - [github:python_demo_module](https://github.com/naltoma/python_demo_module)へアクセス。
    - 右端にある「背景緑のClone or download」をクリック。
    - 「Doownload ZIP」をクリック。
  - 解凍して作業ディレクトリに移動。
    - ダウンロードしたファイル python_demo_module-master.zip を、ダブルクリックして展開（解答）する。
- PyCharmで開く。
  - PyCharmを起動する。
  - 「Open」を選択し、先程展開したフォルダを開く。
    - 「~/Download/python_demo_module-master」として展開されているはず。このフォルダを選択して、右下の「Open」を選択。
- 通常実行してみる。
  - 実行したいファイルを開く。
    - 左側のプロジェクトメニューから「import_case1.py」をダブルクリックして開こう。
  - Runメニューから「Run...」を選択。
  - 先程開いたファイルのモジュール名「import_case1」を選択。
    - 実行結果が下のウィンドウに出力されるはず。
    - 同じファイルを再実行するときは、右上の「右向き三角アイコン」をクリックするだけで良い。（ショートカットも用意されてるので調べてみよう）
- 設定無しでデバッグ実行してみる。
  - Runメニューから「Debug 'import_case1'...」を選択するか、右上の「虫アイコン」をクリックしよう。これだけでデバッグ実行される。
  - 何も設定していない状態でデバッグ実行すると、トラブルが起きたときだけそこで一時停止する。何も問題ない場合には最後まで実行して終了する。
    - これが一般的なIDEのデバッグ実行。[Thonnyを使ったデバッグ実行](https://github.com/naltoma/python_intro/blob/master/IDE-Thonny-Debug.md)では冒頭行から自動停止したが、これは特殊な例。
- breakpointsを設定してデバッグ実行してみる。
  - デバッガが一時停止して欲しい場所をbreakpointと呼ぶ。今回は、import_case1.pyの3行目にbreakpointを設定してみよう。
  - breakpointの設定。
    - import_case1.pyを開いているウィンドウを眺めると、コードの左側に「灰色背景に行番号」が付与されているはずだ。行番号ではなく、「灰色背景」をクリックすることでbreakpointを付けたり、削除したりすることができる。なお、breakpointは複数箇所に設定することが可能。
    - 3行目にbreakpointを付けてみよう。
    - 一度breakpointを外して、もう一度付けてみよう。
  - breakpointを設定した状態でデバッグ実行してみよう。
    - breakpoint設定行が濃い青背景になり、一時停止した状態になるはずだ。
      - **濃い青背景でハイライトされてる箇所は、次に実行する行（まだ実行していない行）** であることに注意。
  - 一時停止した状態から処理を続ける方法は、大別して3種類ある。
    - **step over**: 次の行に移動する。もし関数呼び出しの行なら、関数を実行し終えて次の行に移動して停止する。
    - **step into**: もし関数呼び出しなら、関数の中に移動して停止する。（関数ではないなら、単に次の行に移動する）
      - step into (ただのstep into): print()等の公式関数であっても、その関数内に移動する。
      - **step into My Code**: 自作関数の場合だけ移動する。
    - **step out**: その行を含む関数を呼び出しているところまで移動する。
  - ここでは、my_math.factR()関数の中に移動するために「step into My Code」を1度実行しよう。
    - 下Debugパネルの上部に、「↓➘➘➘➚➘」のようなアイコンが並んでいる箇所を探そう。この中の「左から3番目の➘（赤線付き）アイコン」が、step into my codeのためのアイコン。これを1度クリックしよう。
      - 自動的にmy_math.pyファイルが開き、RactR()関数の2行目で停止しているはずだ。  
        - この時点で、RactR()の引数nは10であることが薄く表示されていることを確認できるはずだ。同様の結果が下部のdebugウインドウでも表示されている。
        - PyCharm等の一般的なIDEでは、行単位でのみ停止・処理をしていく。
  - step into 2回目
    - もう一度step into my codeを実行すると、2行目の条件文が判定され、Falseとなるためにelseブロックに移動して停止するはずだ。
  - step into 3回目
    - elseブロックの処理は「return n * factR(n-1)」である。
      - nは10に置き換えられる。
      - factR(n-1)は、引数が9と処理された状態で関数呼び出しを行う。つまり、factR(9)を実行しようとする。これは関数呼び出しのため、step into実行すると改めて関数の中に移動して一時停止する。
  - これ以降は基本的に同じ動作の繰り返し。ここではここで一旦停止しよう。
    - 今回は動作確認を省いた「step over」「step out」については、各自でやってみよう。（時間があれば別の機会にやります）

<hr>

## <a name="frame">スタックフレームの移動と確認</a>
- デバッグ実行で一時停止している間は、「今いくつのスタックフレームがあるのか」、「どの順番でフレームを生成したのか」、「今いるフレームはどこか」、「フレーム内の様子はどうなっているか」等の情報を確認することができる。
- スタックフレームの確認。
  - step into 3回目の状態では、以下の3つのフレームが生成されている。
    - 「import_case1.pyを処理するためのフレーム」（最初のフレーム）
    - 「factR(10)を処理するためのフレーム」（2番目のフレーム）
    - 「factR(9)を処理するためのフレーム」（3番目のフレーム）
  - 現状
    - 3つのフレームが上記の順に作成された。スタックフレームは「スタックに積み上げる」ため、最初のフレームが一番下に、そこから2番目のフレームを積み上げ、今は3番目のフレーム factR(9) の中で停止している。
    - この様子はデバッグパネルの左下「MainThread」の下部に「逆順」に示されている。
      - 今いる3番目のフレームが「factR, my_math.py:2」。
        - my_math.pyの2行目、factRの中にいることが読み取れる。
        - このフレーム内に記録されてる変数は右側に表示されており、n=9であることが読み取れる。
  - フレームを移動して確認してみよう。
    - 一つ手前のフレーム（ここでは1回目のfactR呼び出し）の様子を確認したい場合、MainThreadで濃い青表示されてる一つ下のフレーム「factR, my_math.py:5」を選択すると良い。
      - my_math.pyの5行目、factRの中にいることが読み取れる。同時に、ファイル内では薄い青表示になっており、ここから先程のfactR()に移動したことが分かる。
      - このフレーム内に記録されてる変数は、n=10であることが読み取れる。
    - 更に一つ手前のフレーム（ここではimport_case1.py）の様子を確認したい場合、更にひとつ下のフレーム「<module>, import_case1.py:3」を選択すると良い。
      - import_case1.pyの3行目にいることが読み取れる。
      - このフレーム内に記録されてる変数は「Special Variables」となっており、展開するとファイル名等が保存されていることが分かる。これらの値は、ファイル実行した際に保存されたもの。

<hr>

## <a name="note">注意</a>
- デバッガは、終了するまで動き続けます。
  - よくある状況
    - デバッグ実行中にバグ要因に気づき、コードを修正。修正が正しく機能するか確認するために再度デバッグ実行。
      - この時点で2個のデバッガが並行して動いています。機能的には問題ありませんが、デバッガ起動する度にCPU, メモリ等のリソースを奪い続けることになります。
  - 適切な方法
    - デバッグ実行中にバグ要因に気づき、コードを修正。**デバッガを終了させ**、修正が正しく機能するか確認するために再度デバッグ実行。
