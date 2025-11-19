{"author":"ip-note","title":"一般的な著作権表示の話とOSSでの表示義務","draft":"false","date":"2025-09-12","image":"20250917201049.jpg","categories":["著作権","知的財産権全般"]}
<div align="center">
{{< figure src="image/20250917201049.jpg" >}}
</div>

ソフトウェアやWebサイト、文章や画像など、あらゆる著作物に「©2025 ○○」といった著作権表示が付いているのをよく目にする。

しかし実は、日本の著作権法ではこの表示が義務付けられているわけではない。

とはいえ「表示しなくても権利が守られる」ことと「表示しない方がよい」ことは別問題である。

本記事では、著作権表示が法的に義務ではない理由と、それでも表示しておくべき実務的な意味、さらにOSS（オープンソース・ソフトウェア）における表示義務のポイントを整理する。

<h3 id="著作権表示は義務ではないOSSの場合を除く">著作権表示は義務ではない（OSSの場合を除く）</h3>

上述の通り、日本の著作権法では義務ではない。

日本が加盟する万国著作権条約では、「著作権を表記すれば守る」と規定されている。

しかし、日本はベルヌ条約にも加盟しており、この条約では「手続きせずとも、著作物の創作と同時に著作権が発生する」としている。

両方加盟している場合はベルヌ条約が優先されるので、著作権表示は必要ないというわけである。

<h3 id="著作権表示しておくのが無難">著作権表示しておくのが無難</h3>

仮にOSSを使用しない場合であっても、著作権表示により以下のようなメリットがあるため、特別な理由が無い限りは表示しておいた方が良い。

<h4 id="権利帰属先が明確となる">権利帰属先が明確となる</h4>

「誰が著作権者か」を示すことで、利用者がライセンス交渉や問い合わせをしやすくなる。

また、無断利用された場合にも、権利者を主張しやすくなる。

ソフトウェアやWebサイトなど、他人が利用することを前提にする場合は特に重要となる。

<h4 id="無断利用の抑止">無断利用の抑止</h4>

著作権表記があると、利用者に「これは著作権のあるものだ」と意識させられるため、結果的に無断利用を減らせる。

裁判での故意・過失の立証にも有利に働くこともメリットである（「知らなかった」と言いにくくなる）。

<h4 id="ベルヌ条約に非加盟の国で著作権が有効となる">ベルヌ条約に非加盟の国で著作権が有効となる</h4>

多くの国はベルヌ条約に加盟しているが、中には万国著作権条約にしか加盟していない国もある。

著作権表示をすれば、そんな国でも著作権を発生させることができる。

<h4 id="権利保護期間の証拠となり得る">権利保護期間の証拠となり得る</h4>

「©2025 Author Name」のように年を入れることで、「いつからいつまで権利が発生しているか」の証拠の一助になる。

<h3 id="OSSの場合は著作権表示ライセンス表示義務あり">OSSの場合は著作権表示・ライセンス表示義務あり</h3>

ただし、OSSの場合は、殆どの全てのOSSライセンスにおいて、著作権表示・ライセンス表示義務が規定されている点には気を付けたい。

例えば、MITライセンスであれば以下のような著作権＋ライセンス文の表示が義務づけられる。

```
Copyright <YEAR> <COPYRIGHT HOLDER>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

このように、上部では著作権表示、またライセンス文の中には「著作権表示および許諾表示を記載すること」と定められている。

<h3 id="ソフトウェアにおける表示場所">ソフトウェアにおける表示場所</h3>

表示場所は、ソフトウェアの配布形態に応じて多少異なり、例えば以下の場所が挙げられる。

- ソースコードの先頭コメント（各ファイルまたは主要ファイル）
- ソースコードのLICENSEファイルやCOPYRIGHTファイル
- アプリケーションの「ヘルプ」「About」画面など
- WebサービスならフッターなどのWeb画面上
- 取扱説明書

ただし、OSSライセンスによっては表示場所が指定されていることもあるので注意したい。

例えば、TOPPERSライセンスでは、ライブラリ形式など、他のソフトウェア開発に使用できる形で再配布する場合には、再配布に伴うドキュメント（利用者マニュアルなど）に表示するすることが求められる。

なお、ソースコード内にライセンス表示すると見つけづらいので、できれば別のテキストファイルとするのが望ましい。

<h3 id="著作権表示の例OSS">著作権表示の例（OSS）</h3>

以下はOSSを想定した表示例となる。

<strong>表示例１</strong>

```
Copyright  [年号] [原著作者名]
Copyright  [年号] [他の改変者名 (存在する場合)]
...
Copyright  [年号] [自分の名前 (改変した場合)]

[OSSのライセンス文]
```

<strong>表示例２</strong>

```
Copyright <年> [原著作権者], [他の改変者名 (存在する場合)]..., [自分の名前 (改変した場合)]

[OSSのライセンス文]
```

「Copyright」は、「Copyright ©」と表すこともある。

Copyrightと©は意味が重複するのでいずれか一方だけでも良いとされているが、OSSの場合はライセンスの条文を参考にすること。

基本的には、配布元の記載を踏襲するのが良い（例：MITならCopyrightのみ）。

なお、万国著作権条約で保障されているのは「©」であるが、©は環境依存文字のため、(c)や(C)と表示することも多い。

「All Rights Reserved」と表記しているものも見かけるが、これは書く必要はない。

ブエノスアイレス条約では「All Rights Reserved」の表記をすることで著作権が保護されると定められているのだが、日本はブエノスアイレス条約の非加盟国のため、「All Rights Reserved」と記載することに意味はないのである。

よって、OSSの配布元が記載していれば記載しておく、ぐらいの位置づけで良いかと思う。

OSSを改変せずに公開または再頒布するのであれば、著作権表示の箇所はそのまま書けば足りる（原著作者だけのときもあれば、他の改変者の名前があるときもある）。

もし自分で改変していれば、Copyrightの欄に自身の名前を追加すれば良い。