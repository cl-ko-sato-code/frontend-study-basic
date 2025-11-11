---
marp: true
theme: default
class: lead
paginate: true
style: |
  section {
    background: linear-gradient(135deg, #0a192f, #112d4e);
    color: #ffffff;
    font-family: 'Segoe UI', 'Hiragino Sans', 'Noto Sans JP', sans-serif;
  }
  h1, h2, h3 {
    color: #ffffff;
    border-bottom: 2px solid #29b6f6;
    padding-bottom: 0.2em;
  }
  table {
    width: 100%;
    border-collapse: collapse;
    border: 1px solid #29b6f6;
    color: #ffffff;
  }
  th {
    background: #1b3b5f;
    text-align: left;
    padding: 0.5em 0.7em;
  }
  td {
    background: #132a44;
    border-top: 1px solid #29b6f6;
    padding: 0.5em 0.7em;
  }
  tr:nth-child(even) td {
    background: #0e2137;
  }
  code {
    background: #15395b;
    padding: 0.2em 0.4em;
    border-radius: 4px;
    color: #00eaff;
    font-family: Consolas, 'Fira Code', 'Courier New', monospace;
  }
  pre {
    background: #081a29;
    color: #ffffff;
    padding: 1em;
    border-radius: 8px;
    box-shadow: inset 0 0 10px rgba(0,180,216,0.4);
    overflow-x: auto;
    font-family: Consolas, 'Fira Code', 'Courier New', monospace;
  }
  /* ==== highlight.js classes (Marp uses hljs) ==== */
  pre code.hljs { background: transparent; color: #ffffff; }
  .hljs-tag      { color: #64b5f6; }   /* <tag> */
  .hljs-name     { color: #4dd0e1; }   /* <, > などの記号やタグ名一部 */
  .hljs-attr     { color: #b0bec5; }   /* 属性名 */
  .hljs-string   { color: #b2ebf2; }   /* 属性値 */
  .hljs-symbol,
  .hljs-meta     { color: #4dd0e1; }
  .hljs-comment  { color: #7f96a3; font-style: italic; }
  .hljs-keyword  { color: #80cbc4; }
  strong, em { color: #00eaff; }
---

# 第1回：HTMLとは何か  
### Webの構造を支える言語

---

## 今日の目的
- HTMLが**何のために存在するか**を理解する  
- ブラウザがHTMLを**どう読み込み表示しているか**を理解する  
- **よく使うHTMLタグ**を体系的に把握する  
- 最近追加された**便利な要素**を知る

---

## HTMLとは？
- **HyperText Markup Language** の略  
- 「見た目」ではなく **構造** を定義する言語  
- Webページの内容を**意味的に記述**するために存在  
- ブラウザ、検索エンジン、機械が読み取れる形式

---

## HTMLが存在する理由
- Webは「**情報共有**」のために設計された  
- HTMLは文書を**構造化**するためのルール  
- 検索・翻訳・スクレイピングなど、**機械が理解できる文書**を作るための仕組み

---

## ブラウザがHTMLを読み込む流れ

1. HTMLを読み込む  
2. **DOMツリー（構造）** を構築  
3. CSSを読み込み → **CSSOMツリー** を構築  
4. DOM + CSSOM → **レンダーツリー生成**  
5. **描画（ペイント）**  

📄 → 🌲 → 🎨 → 🖼️

---

## head / body の役割
```html
<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>サンプルページ</title>
  </head>
  <body>
    <h1>こんにちは</h1>
    <p>これはHTMLの例です。</p>
  </body>
</html>
```
- `<head>`：ブラウザや検索に必要なメタ情報  
- `<body>`：実際に画面に表示される内容

---

## よく使うタグ（構造）
| タグ | 意味 | よく使う場面 |
|------|------|---------------|
| `<header>` | ページやセクションのヘッダー | ロゴ・ナビ |
| `<nav>` | ナビゲーション領域 | メニューリンク |
| `<main>` | 文書の主内容 | ページの中心部分 |
| `<section>` | トピックごとの区切り | 機能・製品紹介など |
| `<article>` | 独立したコンテンツ単位 | ブログ・ニュースなど |
| `<footer>` | ページのフッター | コピーライト・リンクなど |

---

## よく使うタグ（テキスト）
| タグ | 役割 |
|------|------|
| `<h1>`〜`<h6>` | 見出し構造を定義 |
| `<p>` | 段落 |
| `<a>` | リンク |
| `<span>` | インライン要素をグループ化 |
| `<strong>` / `<em>` | 重要 / 強調 |
| `<br>` / `<hr>` | 改行 / 区切り線 |

---

## リスト・表関連タグ
| タグ | 概要 |
|------|------|
| `<ul>` / `<ol>` / `<li>` | 箇条書きリスト |
| `<dl>` / `<dt>` / `<dd>` | 用語と説明のペア |
| `<table>` | 表全体 |
| `<thead>` / `<tbody>` / `<tr>` / `<td>` | 表の構造化 |

---

## メディア関連タグ
| タグ | 機能 |
|------|------|
| `<img>` | 画像を表示 |
| `<video>` | 動画を埋め込み |
| `<audio>` | 音声を埋め込み |
| `<source>` | メディアの複数形式を指定 |
| `<picture>` | 画面幅に応じて画像を切替 |

---

## フォーム関連タグ
| タグ | 説明 |
|------|------|
| `<form>` | 入力フォームの全体 |
| `<input>` | テキスト・チェックボックスなど |
| `<textarea>` | 複数行テキスト |
| `<select>` / `<option>` | プルダウン |
| `<button>` | 送信ボタン |
| `<label>` | 入力項目の説明 |

---

## 最近の便利タグ
| タグ | 機能 | 例 |
|------|------|------|
| `<details>` / `<summary>` | 折りたたみセクション |
| `<dialog>` | モーダルダイアログ |
| `<template>` | 非表示のHTMLテンプレート |
| `<slot>` | Web Components内で使う差し込み箇所 |

---

## 便利タグの例
```html
<details open>
  <summary>もっと詳しく</summary>
  <p>この中に補足情報を入れられます。</p>
</details>

<dialog open>
  <p>確認しますか？</p>
  <button>OK</button>
</dialog>
```
> **Note:** 上記のコードブロックは ` ```html ` の言語指定により、hljsのクラスが付与され色分けされます。

---

## HTMLを書くときの考え方
- 「**見た目ではなく意味**」を意識する  
- CSSで装飾、JavaScriptで動きを追加  
- HTMLの役割：**構造を定義すること**  
- Reactでも最終的に**HTML要素を生成している**

---

## 演習
1. 自分の所属する会社・チームの紹介ページをHTMLで作ってみよう  
2. ページ構造を意識して、`header`, `main`, `section`, `footer`を使う  
3. `details` や `dialog` を1つ使ってみる

---

## 次回予告
👉 **第2回：CSS基礎とデザインの考え方**  
HTMLで作った構造に、見た目とレイアウトを与えます。
