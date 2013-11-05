<h2 id="pending-tests">Pending tests</h2>

 Pending test-cases are simply those without a callback:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it('should return -1 when the value is not present')
      })
    })

<h2 id="pending-tests">未確定のテスト</h2>

 テスト内容が確定していないものについては、コールバックを記述せずに書いておきます。:

    describe('Array', function(){
      describe('#indexOf()', function(){
        it('should return -1 when the value is not present')
      })
    })
