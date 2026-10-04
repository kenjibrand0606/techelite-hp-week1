# ダミー歯科クリニック 企業紹介ページ

架空の歯科クリニックの紹介ページ（1ページ）。HTML5 + CSS のみで、JavaScript は使っていません。

## ファイル構成

```
.
├── index.html
├── css/
│   └── style.css
├── img/
│   └── favicon.svg   ← ダミーのファビコン（同梱）※写真は下記を配置
└── README.md
```

## 必要な画像

| 用途 | 配置パス | 推奨サイズ | 比率 | 備考 |
|---|---|---|---|---|
| ヒーロー背景 | `img/hero.jpg` | 1920 × 1080 px | 16:9 | 左側に白いグラデーションが重なるため、被写体は右寄りの構図がおすすめ |
| 診療内容：一般歯科 | `img/service-general.jpg` | 800 × 600 px | 4:3 | |
| 診療内容：小児歯科 | `img/service-pediatric.jpg` | 800 × 600 px | 4:3 | |
| 診療内容：ホワイトニング | `img/service-whitening.jpg` | 800 × 600 px | 4:3 | |

- カード画像は `object-fit: cover` で 4:3 にトリミング表示されるので、比率が違っても崩れません。
- 画像が無いときは、ヒーローもカードも淡い水色の背景で表示されます。
- ファイル名やパスを変える場合は、`index.html` の `src` と `css/style.css` の `.hero` の `url()` を合わせて変更してください。

### 仮画像（placehold.co）を使う場合

`index.html` の `src` を次のように書き換えれば確認できます。

```
https://placehold.co/800x600?text=General
https://placehold.co/800x600?text=Pediatric
https://placehold.co/800x600?text=Whitening
```

ヒーローは `css/style.css` の `.hero` を次のように変更します。

```css
url("https://placehold.co/1920x1080?text=Hero") center / cover no-repeat,
```

## 仕様メモ

- ブレイクポイント（モバイルファースト）：SP 〜767px / タブレット 768〜1024px / PC 1025px〜
- テーマカラーと余白は `css/style.css` 冒頭の `:root` の CSS 変数で管理しています。
- 命名規則は BEM です。共通パーツは `.section-title` と `.button`（`--primary` / `--white`）。
- SP のハンバーガーアイコンは見た目だけで、押しても動きません（JS なしのため）。
- アニメーションは `transition` だけです。`prefers-reduced-motion` が有効な環境では無効になります。
- 電話番号・メールアドレス・住所はすべてダミーです。
