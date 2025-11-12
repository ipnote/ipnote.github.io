{"author":"ip-note","title":"【Blogger】ブログ記事への表の挿入","draft":"false","date":"2025-08-10","image":"20250525153407.jpg","categories":["ブログ作成・カスタマイズ"]}
ブログ内で記事中に表を挿入したくなったので、挿入方法を調べてみた。

挿入する表は、以下のような感じにしてみたい。

<div align="center">
{{< figure src="image/20250525153407.jpg" >}}
</div>


表を挿入するには、HTMLとCSSを使用する。

一見敷居が高そうにも見えるが、以下の方法を行うだけで表を作成できる。

<ul class="table-of-contents">
    * [HTMLコードの貼り付けで作成](#HTMLコードの貼り付けで作成)
    <li>[デザインのカスタマイズ](#デザインのカスタマイズ)
            * [CSSの追加機能の利用](#CSSの追加機能の利用)
            * [記事の「HTMLビュー」に直接](#記事のHTMLビューに直接)
        
    </li>
    * [どちらの方法でカスタマイズすべき？](#どちらの方法でカスタマイズすべき)


<h3 id="HTMLコードの貼り付けで作成">HTMLコードの貼り付けで作成</h3>

以下のコードを記事の「HTMLビュー」に貼り付けると、シンプルな表が作成される。


```html
<table>
  <thead>
    <tr>
      <th>見出し1</th>
      <th>見出し2</th>
      <th>見出し3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>データ1</td>
      <td>データ2</td>
      <td>データ3</td>
    </tr>
    <tr>
      <td>データ4</td>
      <td>データ5</td>
      <td>データ6</td>
    </tr>
  </tbody>
</table>

```



これで、以下のような表を記事の中に挿入することができる。

{{< figure src="image/20250525154216.png" >}}

しかしこれでは少し寂しいので、更に表のデザインをカスタマイズしたい。

<h3 id="デザインのカスタマイズ">デザインのカスタマイズ</h3>

デザインを変更する方法は、主に以下の２通りある。

CSSの追加機能はBloggerを前提とした説明ではあるが、コードは他のブログでも共通して使えるかと思う。

<h4 id="CSSの追加機能の利用">CSSの追加機能の利用</h4>

Bloggerの「テーマ」→「カスタマイズ」→ 「詳細設定」→「文字の色」の横にある▼をクリックすると出てくる「CSSを追加」を選択し、例えば以下のCSSを追加すると、表を見やすくすることができる。


```css
table {
  width: 100%;
  border-collapse: collapse;
  margin: 10px 0;
  font-size: 14px;
  text-align: left;
}
th, td {
  border: 1px solid #dddddd;
  padding: 5px;
}
th {
  background-color: #898989;
  color: white;
}
tr:nth-child(even) {
  background-color: #f9f9f9;
}

```



これで、さっきの表が以下のような見た目になる。

<div align="center">
{{< figure src="image/20250525154446.png" >}}
</div>


ただし、この方法だと全ての記事内の表に同じデザインが適用される。

もし、特定の記事内の表だけデザインを変更したい場合は、以下の方法で編集すると良い。

以下は、コードの補足である。
- th（ヘッダーセル）は見出し、td（データセル）は各データを表示
- border-collapse: collapse; を指定すると線が重ならない
- nth-child(even) で偶数行の背景色を変え、見やすくする

<h4 id="記事のHTMLビューに直接">記事の「HTMLビュー」に直接 <style></style>
</h4>

表を変更したい記事の「HTMLビュー」に <style> を以下のように書きこみ、その下に表のHTMLコードを追加することでも、変更可能である。


```css
<style>
  table {
    width: 100%;
    border-collapse: collapse;
    margin: 10px 0;
    font-size: 14px;
    text-align: left;
  }
  th, td {
    border: 1px solid #dddddd;
    padding: 5px;
  }

  th {
    background-color: #898989;
    color: white;
  }
  tr:nth-child(even) {
    background-color: #f9f9f9;
  }
</style>

```



<h3 id="どちらの方法でカスタマイズすべき">どちらの方法でカスタマイズすべき？</h3>

通常であれば、「追加CSS」 を使うのがベストだと思う。

記事毎に<style>を書き込む必要が無くなる。

特定の記事のみ変えたいなら、記事内の <style> を使うと便利。

スプレッドシートからのコピペでも作成できるらしいが、そちらはまだ試したことがないのでこの記事では紹介を省きたい。