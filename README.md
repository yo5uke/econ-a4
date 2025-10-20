# 経済学研究用Typstテンプレート Econ-a4

## インストール

**注:** このテンプレートは英語論文用です。

***Note:*** このテンプレートはQuarto 1.8以降が必要です。それ未満のバージョンの方は、[こちら](https://quarto.org/docs/get-started/)から1.8以上のバージョンをインストールしてください。最新バージョンをインストールすれば問題ありません。

このテンプレートを使用するには、以下のコマンドを実行してください。

``` bash
quarto use template yo5uke/econ-a4
```

## 使い方

新しいQuartoドキュメントを作成し、YAMLヘッダーに以下のように記述します。

``` yaml
---
title: "タイトル"
author: "著者名"
date: "日付"
format:
  econ-a4: default
---
```

ヘッダーはカスタマイズ可能です。

```yaml
---
title: |
  An Example of a Research Paper Using Econ A4 Typst Template
author: 
  - name: First Author
    affiliation: University of Example
    email: email@example.com
  - name: Second Author
    affiliation: Institute of Sample Studies
    email: email@example.jp
date: 2025-10-19
date-format: long
abstract: |
  This is an example abstract for a research paper using the Econ A4 Typst template. It summarizes the main findings and contributions of the paper. The template is designed to meet the formatting requirements of economic journals and includes features such as section numbering and a table of contents. Researchers can easily customize the template to fit their specific needs while adhering to academic standards. Overall, this template aims to facilitate the writing process for economists and researchers in related fields.
jel-codes: 
  - C10
  - C50
keywords: 
  - Econometrics
  - Data Analysis
  - Research Methodology
format:
  econ-a4-typst: 
    number-sections: true
    toc: true
---
```

QuartoにおけるデフォルトのTypst出力から、表紙に関する設定をはじめ、行間、フォントサイズ、マージンなどが経済学論文で使用できるように調整されています。

タイトル、著者、日付、要旨、JEL classification、キーワードなどを設定できます。論文用ですのでタイトル、著者、日付、アブストラクトは必須です。著者は複数人対応しています。

タイトルもしくは要旨に改行を入れたい場合は以下のようにバックスラッシュ（\）で改行を指定してください（Typstにおける改行の指定方法です）。

```yaml
abstract: |
  This is the first line. \
  This is the second line.
```

```yaml
format:
  econ-a4-typst: 
    number-sections: true
    toc: true
```

`number-sections: true`でセクション番号を付与、`toc: true`で目次を表示します。必要に応じて設定してください。基本的なQuartoの設定ができますので、他の設定については[Quartoのドキュメント](https://quarto.org/docs/output-formats/typst.html)を参照してください。

## 使用例

使用例は[こちら](template.qmd)をご覧ください。

## 限界

本テンプレートの限界は以下の点です。

- 表紙の脚注への対応
- PandocによるBibliography管理への対応

特に2点目に関しては、位置にこだわりがなければYAMLヘッダーに`bibliography: references.bib`と書くことで対応可能です。しかし、位置を指定して参考文献欄を出力したい場合は対応が必要です。

原始的な方法ではありますがTypstコードを直接書くことで対応可能です。例えば以下のようにします。

```` markdown
## References

```{{=typst}}
#bibliography("references.bib")
```
````

これを任意の位置に書くことで参考文献欄を出力できます。これについても[template.qmd](template.qmd)に例がありますので参照してください。

## ライセンス

このテンプレートはMITライセンスの下で公開されています。
