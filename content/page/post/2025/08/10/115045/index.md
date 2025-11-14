{"author":"ip-note","title":"ブログ記事へのソースコードの埋め込み","draft":"false","date":"2025-08-10","image":"20250523224620.jpg","categories":["ブログ作成・カスタマイズ"]}
ブログ記事中で、ソースコードを載せることが多くなってきた。

コードをそのまま載せると記事が長くなってしまい、見た目がよろしくない。　

そこで、記事をコンパクトにするため、ソースコードを埋め込む（コードブロックを作成する）方法を調べてみた。

<div align="center">
{{< figure src="image/20250523224620.jpg" >}}
</div>


特に、


- 埋め込みたいコードに含まれるタグによるエラーの解消
- 勝手にコードが改行されてしまうのをスクロール表示にする
- スクロールバーのつまみの色変更

という点で苦戦したので、方法を備忘録として残しておきたい。



<ul class="table-of-contents">
    <li>[Google-code-prettifyの導入（準備）](#Google-code-prettifyの導入準備)
            * [スクロールバーのデザイン変更時の注意](#スクロールバーのデザイン変更時の注意)
        
    </li>
    <li>[記事にコードを挿入](#記事にコードを挿入)
            * [挿入時の注意](#挿入時の注意)
        
    </li>
    * [コピーボタンの配置は？](#コピーボタンの配置は)


<h3 id="Google-code-prettifyの導入準備">Google-code-prettifyの導入（準備）</h3>

- Blogger管理画面を開く
- 「テーマ」 を選び、「HTMLの編集」をクリックする
- 下記Javascriptコードを、HTML内の&lt;head&gt;...&lt;/head&gt;タグ間の任意の場所（例えば、&lt;/head&gt;の直前）に貼り付ける




```javascript
<script; src='https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js?skin=sunburst'/>

```

* さらに下記コードを、上のJavascriptコードの直下に貼り付ける。

```css
<style>
    pre.prettyprint {
      font-size: 12px; /* コード内のフォントサイズ */
      word-wrap: normal; /* 単語の途中での改行を無効にする */
      overflow: auto; /* 内容がはみ出た場合、スクロールバーを表示 */
      white-space: pre; /* 改行を抑制してそのまま表示 */
      max-height: 12em; /* 最大高さ指定、超えるとスクロール */
    }
    .prettyprint ol.linenums &gt; li {
      list-style-type: decimal;  /* コードの各行に数字番号を表示 */
    }
    pre.prettyprint::-webkit-scrollbar {
      width: 8px; /* スクロールバーの幅 */
    }
    pre.prettyprint::-webkit-scrollbar-thumb {
    background-color: #aaa;  /* スクロールバーのつまみの色 */
    }
</style>

```

<h4 id="スクロールバーのデザイン変更時の注意">スクロールバーのデザイン変更時の注意</h4>

最初にスクロールバーのつまみの色だけを変更しようと（::-webkit-scrollbar-thumb）を追記したが、反映されなかった。

どうやら、最低限スクロールバーのベースとなるスタイル（::-webkit-scrollbar）の記入が必要な場合があるとのこと。

このため、１で記載したサンプルコードには（::-webkit-scrollbar）（スクロールバーの幅の設定）も追記している。

<h3 id="記事にコードを挿入">記事にコードを挿入</h3>

- 記事をHTMLビューに切り替える
- コードを貼り付けたい場所に、下記のコードを挿入


```html
<pre class='prettyprint linenums'>
書きたいコード
</pre>

```

<h4 id="挿入時の注意">挿入時の注意</h4>

&lt;pre&gt;と&lt;/pre&gt;の間に挟まれたコード内に「&lt;script&gt;」や「&lt;link&gt;」等のタグがあると、Blogger側のエラーとして識別されてしまう。

例えば、書きたいコードに

&lt;style type="text/css"&gt;

と入れても、ソースコードが記事に表示されない。

その場合、

<strong>「<」→「&amp;lt;」 </strong>

<strong>「>」→「&amp;gt;」</strong>

への置換が必要になる。

例えば

&lt;style type="text/css"&lt;であれば、

&amp;lt;style type="text/css"&amp;gt;

と入力すると、エラーが解消される。

<h3 id="コピーボタンの配置は">コピーボタンの配置は？</h3>

なお、コードブロックを作成すると見栄えは良くなるが、今度はコードブロック内の今度をコピーしようとする際にいちいちスクロールバーを操作したりと、不便なこともあるかと思う。

コードブロック中にコピーボタンを配置する方法についても以下の記事で紹介しているので、適宜参考としてみて欲しい。

[コードブロックにコピーボタンを配置 - グルメ漫画を味わい尽くす](https://u-zan.hatenablog.com/entry/2025/08/10/115228)