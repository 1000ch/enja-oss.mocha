<h2 id="exclusive-tests">Exclusive tests</h2>

<h2 id="exclusive-tests">排他的なテスト</h2>

 The exclusivity feature allows you to run only the specified suite or test-case
 by appending `.only()` to the call as shown here:

 排他的な処理や限定的なのテストには、このように`.only()`を使うと良いでしょう。

    describe('Array', function(){
      describe.only('#indexOf()', function(){
        ...
      })
    })

  Or a specific test-case:

  また、特定のテストケースに対しては:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it.only('should return -1 unless present', function(){

        })

        it('should return the index when present', function(){

        })
      })
    })

  Note that currently only one `.only()` call is respected, this
  effectively turns into a `--grep`.

  `--grep`した場合にわかりやすいように、`.only()`は1度だけ呼ばれることを想定されています。