<h2 id="usage">mocha(1)</h2>

    Usage: mocha [debug] [options] [files]
    
    Commands:
    
      init <path>
      initialize a client-side mocha setup at <path>
    
    Options:
    
      -h, --help                      output usage information
      -V, --version                   output the version number
      -r, --require <name>            require the given module
      -R, --reporter <name>           specify the reporter to use
      -u, --ui <name>                 specify user-interface (bdd|tdd|exports)
      -g, --grep <pattern>            only run tests matching <pattern>
      -i, --invert                    inverts --grep matches
      -t, --timeout <ms>              set test-case timeout in milliseconds [2000]
      -s, --slow <ms>                 "slow" test threshold in milliseconds [75]
      -w, --watch                     watch files for changes
      -c, --colors                    force enabling of colors
      -C, --no-colors                 force disabling of colors
      -G, --growl                     enable growl notification support
      -d, --debug                     enable node's debugger, synonym for node --debug
      -b, --bail                      bail after first test failure
      -A, --async-only                force all tests to take a callback (async)
      --recursive                     include sub directories
      --debug-brk                     enable node's debugger breaking on the first line
      --globals <names>               allow the given comma-delimited global [names]
      --check-leaks                   check for global variable leaks
      --interfaces                    display available interfaces
      --reporters                     display available reporters
      --compilers <ext>:<module>,...  use the given module(s) to compile files

    使い方: mocha [debug] [options] [files]
    
    コマンド:
    
      init <path>
      <path>にMochaの初期設定を行います
    
    Options:
    
      -h, --help                      ヘルプを表示します
      -V, --version                   Mochaのバージョンを出力します
      -r, --require <name>            モジュールを指定します
      -R, --reporter <name>           使うレポーターを指定します
      -u, --ui <name>                 テストスタイルを指定します (bdd|tdd|exports)
      -g, --grep <pattern>            <pattern>にマッチしたテストのみを実行します
      -i, --invert                    `--grep`のマッチングの逆です
      -t, --timeout <ms>              タイムアウトの時間をミリ秒で指定します [2000]
      -s, --slow <ms>                 "slow"と判定する閾値をミリ秒で指定します [75]
      -w, --watch                     ファイルの変更を監視します
      -c, --colors                    カラー出力を有効にします
      -C, --no-colors                 カラー出力を無効にします
      -G, --growl                     growl通知を有効にします
      -d, --debug                     nodeのデバッガーを有効にします `node --debug`と同義です
      -b, --bail                      テストの最初の例外を捕捉します
      -A, --async-only                全てのテストでコールバックをとるようにします (非同期)
      --recursive                     サブディレクトリのテストも含むようにします
      --debug-brk                     nodeのデバッガのブレークを有効にします
      --globals <names>               許容するグローバル変数をカンマ区切りで指定します
      --check-leaks                   グローバル変数のリークをチェックします
      --interfaces                    利用可能なテストスタイルを表示します
      --reporters                     利用可能なレポーターを表示します
      --compilers <ext>:<module>,...  指定のモジュールでファイルをコンパイルします

<h3 id="watch-option">-w, --watch</h3>

  カレントディレクトリで1度実行するだけで、変更を検知しテストを再度実行します。

<h3 id="compilers-option">--compilers</h3>

  CoffeeScriptのサポートはしていません。CoffeeScript、あるいはその他のコンパイルを必要とする
  言語の場合には（`--watch`オプションと一緒に）その拡張子とコンパイラモジュールを指定します。
  例えば、`--compilers coffee:coffee-script`のようにします。

<h3 id="bail-option">-b, --bail</h3>

  最初の例外のみを補足したい場合には、`--fail`を使ってください！

<h3 id="debug-option">-d, --debug</h3>

  nodeのデバッガを有効にします。このオプションを有効にすることで`node debug <file ...>`が実行され、コードのステップ実行や、__debugger__ステートでのブレークを行うことができます。

<h3 id="globals-option">--globals &lt;names&gt;</h3>

  許容するグローバル変数をカンマ区切りで指定します。例えばアプリケーションで`app`と`YUI`をグローバル変数に配置しているなら、`--globals app,YUI`とします。

<h3 id="ignore-leaks-option">--check-leaks</h3>

  テスト実行時のグローバル変数のリークチェックを有効にするには、`--check-leaks`を指定します。チェック対象としないグローバル変数は、`--globals jQuery,MyLib`といったように、`--globals`で指定してください。

<h3 id="require-option">-r, --require &lt;name&gt;</h3>

  `--require`オプションは[should.js](http://github.com/visionmedia/should.js)のようなライブラリを使うのに便利です。テストファイル毎にわざわざ`require('should')`と指定せずとも、`--require should`とするだけで指定することが出来ます。
  これは`var should = require('should')`のようにmodule.exportにrequireしなければならない場合でも、有効です。

<h3 id="ui-option">-u, --ui &lt;name&gt;</h3>

  テストインターフェースを指定します。デフォルトは`bdd`です。

<h3 id="reporter-option">-R, --reporter &lt;name&gt;</h3>

  `--reporter`オプションで、テストレポーターを指定することが出来ます。デフォルトは`dot`です。これはサードパーティーのレポーターも指定することが出来ます。例えば`mocha-lcov-reporter`を使いたい場合は、`npm install mocha-lcov-reporter`を実行し`--reporter mocha-lcov-reporter`としてください。

<h3 id="timeout-option">-t, --timeout &lt;ms&gt;</h3>

  テストのタイムアウトの時間を指定します。デフォルトは2秒です。ミリ秒か、`s`を付けることで、秒で指定することが可能です。例: `--timeout 2s` or `--timeout 2000`

<h3 id="slow-option">-s, --slow &lt;ms&gt;</h3>

  `slow`と判定する閾値を指定します。デフォルトは75ミリ秒です。Mochaではテストの実行が遅い場合にそれをハイライトで表示します。

<h3 id="grep-option">-g, --grep &lt;pattern&gt;</h3>

  `--grep`を指定することで、パターンにマッチしたテストのみを実行することが出来ます。`pattern`は内部的に`RegExp`にコンパイルされます。

  例えば`api`や`app`に関連するテストだけを行いたい場合は、次のようにすると良いでしょう。;
  どちらかを実行したい場合は`--grep api`か`--grep app`を指定します。同じようにスイートやテストケースのタイトルも指定することが可能で、`--grep users`や`--grep GET`のような指定も有効です。

    describe('api', function(){
      describe('GET /api/users', function(){
        it('respond with an array of users')
      })
    })

    describe('app', function(){
      describe('GET /users', function(){
        it('respond with an array of users')
      })
    })
