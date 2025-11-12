{"author":"ip-note","title":"【Blogger】見出しデザインのカスタマイズ","draft":"false","date":"2025-08-10","image":"20250525150358.jpg","categories":["ブログ作成・カスタマイズ"]}
Bloggerの投稿エディタでは、見出しを行ごとに簡単に設定できるようになっている。

<div align="center">
[{{< figure src="image/20250525150358.jpg" >}}:300]
</div>


見出しには、h1（主見出し）、h2（見出し）、h3（小見出し）、h4（準見出し）がある。

h1は主にブログ記事のタイトルとして用いることが推奨されているため、文中では実質的にh2以降を使用することとなる。

記事に見出しを用いることは多いが、記事の見栄えを良くするために、見出しのデザインを変更したい場合もあるだろう。

Bloggerのデザインテンプレートをカスタマイズするには、以下の手順でHTMLとCSSを修正する必要がある。

<h3 id="見出しデザインのカスタマイズ方法">見出しデザインのカスタマイズ方法</h3>

<h4 id="主な手順">主な手順</h4>

<div>
1. Bloggerの管理画面 → [テーマ] → [HTMLを編集] を開く<br/>
2. HTML内で、見出し（h1, h2など）のスタイルを定義している箇所を探す<br/>
<br/>
※例えば、<style> タグ内または外部CSSファイルのリンクを探す<br/>
※デザインテンプレート「Qooq」であれば、個別記事本文のコメント以降にある、「#single-content h2 {」以降が編集対象となる<br/>

3. 見出しのスタイルを変更
</div>


<h4 id="カスタマイズ例">カスタマイズ例</h4>


```
h2 {
  font-size: 32px; /* お好みのサイズに変更 */
  padding: 0.5em; /* 文字周りの余白 */
  font-weight: bold; /* 太字にする場合 */
  font-style: italic; /* 斜体にする */
  color: #333; /* 文字色変更 */
  }
```



<h4 id="主なプロパティ一覧">主なプロパティ一覧</h4>

以下、表のデザインに関するプロパティ一覧を掲載する。

<h5 id="1-フォント関連のプロパティ">1. フォント関連のプロパティ</h5>

<table>
<thead>
<tr>
<th> プロパティ </th>
<th> 説明 </th>
<th> 使用例 </th>
</tr>
</thead>
<tbody>
<tr>
<td> font-size </td>
<td> フォントサイズ </td>
<td> 24px </td>
</tr>
<tr>
<td> font-weight </td>
<td> 太さ </td>
<td> normal, bold, lighter </td>
</tr>
<tr>
<td> font-style </td>
<td> 斜体 </td>
<td> normal, italic, oblique </td>
</tr>
<tr>
<td> font-family </td>
<td> フォントの種類 </td>
<td> Arial, sans-serif </td>
</tr>
<tr>
<td> color </td>
<td> 文字色 </td>
<td> #000000 </td>
</tr>
<tr>
<td> line-height </td>
<td> 行間 </td>
<td> 1.5</td>
</tr>
<tr>
<td> letter-spacing </td>
<td> 文字間隔 </td>
<td> 2px </td>
</tr>
<tr>
<td> word-spacing </td>
<td> 単語間の間隔 </td>
<td> 4px </td>
</tr>
<tr>
<td> text-transform </td>
<td> 文字の変換 </td>
<td> uppercase, lowercase, capitalize </td>
</tr>
<tr>
<td> text-shadow </td>
<td> 文字の影 </td>
<td> 2px 2px 5px gray </td>
</tr>
</tbody>
</table>


<h5 id="2-配置装飾関連のプロパティ">2. 配置・装飾関連のプロパティ</h5>

<table>
<thead>
<tr>
<th> プロパティ </th>
<th> 説明 </th>
<th> 使用例 </th>
</tr>
</thead>
<tbody>
<tr>
<td> text-align </td>
<td> テキストの配置 </td>
<td> left, centor, right, justify </td>
</tr>
<tr>
<td> text-decoration </td>
<td> 下線・取り消し線 </td>
<td> none, underline, line-through, overline </td>
</tr>
<tr>
<td> white-space </td>
<td> 改行の処理 </td>
<td> normal, nowrap, pre </td>
</tr>
</tbody>
</table>


<h5 id="3-背景ボーダー関連のプロパティ">3. 背景・ボーダー関連のプロパティ</h5>

<table>
<thead>
<tr>
<th> プロパティ </th>
<th> 説明 </th>
<th> 使用例 </th>
</tr>
</thead>
<tbody>
<tr>
<td> background-color </td>
<td> 背景色 </td>
<td> #f8f8f8 </td>
</tr>
<tr>
<td> background-image </td>
<td> 背景画像 </td>
<td> url('image.jpg') </td>
</tr>
<tr>
<td> border </td>
<td> ボーダーの設定 </td>
<td> 2px solid #ff6600 </td>
</tr>
<tr>
<td> border-radius </td>
<td> 角の丸み </td>
<td> 10px </td>
</tr>
<tr>
<td> padding </td>
<td> 内側の余白 </td>
<td> 10px </td>
</tr>
<tr>
<td> margin </td>
<td> 外側の余白 </td>
<td> 20px 10px </td>
</tr>
</tbody>
</table>


<h5 id="4-ボックスデザイン">4. ボックスデザイン</h5>

<table>
<thead>
<tr>
<th> プロパティ </th>
<th> 説明 </th>
<th> 使用例 </th>
</tr>
</thead>
<tbody>
<tr>
<td> display </td>
<td> 表示形式 </td>
<td> block, inline, flex, grid </td>
</tr>
<tr>
<td> width </td>
<td> 幅 </td>
<td> 80%, auto </td>
</tr>
<tr>
<td> height </td>
<td> 高さ </td>
<td> 50px, auto </td>
</tr>
<tr>
<td> box-shadow </td>
<td> ボックスの影 </td>
<td> 3px 3px 10px gray </td>
</tr>
</tbody>
</table>


<h3 id="適用方法">適用方法</h3>

変更を保存し、ブログを更新して適用されているか確認すれば良い。

もし特定の部分だけ変更したい場合は、BloggerのHTML内でクラス名を特定し、そのクラスをCSSで変更することもできる。