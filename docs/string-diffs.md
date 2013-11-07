<h2 id="string-diffs">String diffs</h2>

  Mocha supports the `err.expected`, and `err.actual` properties
  when available to present expectations to the developer. Currently
  Mocha provides string diffs, however in the future object diffs and
  others may be provided.

<h2 id="string-diffs">文字列の差分</h2>

  結果が期待する挙動と異なり、その差分が表示可能な場合は`err.expected`、`err.actual`の2つのプロパティを利用することが出来ます。
  現在Mochaでは、文字列の差分だけでなく、オブジェクトやその他の差分もサポートしています。

  ![string diffs](http://f.cl.ly/items/3L0T1A0h2N1J3G021i0F/Screen%20Shot%202012-03-01%20at%202.31.31%20PM.png)