{"author":"ip-note","title":"コードブロックにコピーボタンを配置","draft":"false","date":"2025-08-10","image":"20250523225443.jpg","categories":["ブログ作成・カスタマイズ"]}
ブログデザインのカスタマイズに関する記事を書いていると、多少長いコードを掲載することがある。

コードブロックでデザインはスッキリさせることができるものの、読者がそのコードを参考にしたり、自分の環境で試したりする場合、コードを一括でコピーできる機能があると非常に便利だ。

※コードブロックの方法は、以下の記事で説明している

[ブログ記事へのソースコードの埋め込み - グルメ漫画を味わい尽くす](https://u-zan.hatenablog.com/entry/2025/08/10/115045)

しかし、Bloggerの標準仕様では、コードブロックに「コピー」ボタンは付いていない。

今回はJavaScriptとCSSを使って、コードブロックにコピー機能を追加する方法を紹介する。

<div align="center">
{{< figure src="image/20250523225443.jpg" >}}
</div>


<h3 id="CSSを追加する">CSSを追加する</h3>

Bloggerの「テーマ」→「カスタマイズ」→「HTMLの編集」で、以下のCSSを<head>内または<style>タグに追加する。


```css
/* コードブロック全体を囲むコンテナ（ボタンとコードをまとめて管理） */
.code-block {
  position: relative;
  margin-bottom: 1.5em;
}

/* コピー用ボタンの見た目と位置 */
.copy-btn {
  position: absolute;
  top: 4px;
  right: 20px;
  padding: 4px 8px;
  font-size: 12px;
  background-color: #f8f8f8;
  border: 1px solid #ccc;
  border-radius: 4px;
  cursor: pointer;
  z-index: 10;
}

/* コードとボタンが重ならないようにpreタグに上部余白を確保 */
.code-block pre {
  padding-top: 2.5em;
  font-size: 12px;
  overflow: auto;
  white-space: pre;
  max-height: 11.5em;
}

```



<h3 id="対象記事へのコードブロックコピーボタンの埋め込み">対象記事へのコードブロック＋コピーボタンの埋め込み</h3>

記事の編集画面で「HTML表示」に切り替えて、以下のように載せたいコードを<div>タグと<pre>タグで挟み込む形で埋め込む。


```html
<!-- コードブロック + コピー用ボタン -->
<div class='code-block'>
  <button class='copy-btn' onclick='copyCode(this)'&gt;Copy&lt;/button>
  <pre class='prettyprint linenums'>
コードブロック内に載せたいコード
}
  </pre>
</div>

```



<h3 id="表示確認と調整">表示確認と調整</h3>

これで、対象のコードブロックに「コピー」ボタンが表示されるようになる。

スタイルやボタンの文言などは自由にカスタマイズ可能である。