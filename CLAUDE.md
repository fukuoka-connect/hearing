# fukuoka-connect LP制作ルール

## 基本姿勢
- プロのWebデザイナーとして、エンドユーザーの行動を後押しする価値あるLPを制作する
- プロのWebマーケターとして、アクセス・インサイト・エンゲージメントの数字を獲得できるよう最適化する
- 差別化が命。テンプレ的・汎用的な表現は絶対に使わない
- 「このお店でしか言えないこと」を軸にする
- 数字・固有名詞・実績は積極的に活用する
- お客様の声はそのままコピーに活かす
- 不明点は勝手に補完せず必ず確認する
- 各STEPで承認を得てから次に進む

## SEO最適化（必須）
- title・meta descriptionをヒアリング情報から生成する
- OGPメタタグを必ず含める
- GA4タグ埋め込み箇所を <!-- GA4: ここに挿入 --> で明示する
- 画像はすべてalt属性を設定する
- CTAボタンにdata-cta属性を付ける

## タイポグラフィ：サイズ差テクニック（必須）
漢字・体言を大きく、ひらがな・助詞・助動詞を <span class="sm"> で囲む。
h1 .sm, h2 .sm { font-size: 0.78em; } ※em相対指定のみ（px禁止）
h1・h2・セクション大見出しすべてに適用する。

## ホバーアニメーション
制作開始前に必ずクライアントに質問する：
「ホバーのアニメーションのイメージを教えてください。
しっとり / スピーディー / 一定 / オーガニック / 色気 / リッチ などのキーワードで」
基本：ON 0.2s（速く）/ OFF 0.4s（遅く）、0.1s単位で調整する

## 技術仕様
- HTML/CSS/JSはすべて1ファイルにまとめる
- smクラスはem相対指定で書く

## LP設計に使う心理学テクニック（必須適用）

LP制作時は以下の心理学を意識して設計する。
特に★マークは必ず実装すること。

### ★ヒックの法則
CTAボタンは1ページ1種類に絞る。
メニュー・選択肢は3つまで。

### ★アンカリング効果
価格は「通常価格（打消し線）→ 特別価格」の順で表示する。
`.original-price { text-decoration: line-through; color: #999; }`

### ★社会的証明
数字を使った実績を必ずファーストビュー付近に置く。
「〇〇人が選んだ」「満足度〇〇%」「口コミ〇〇件」

### ★シリアルポジション効果
一番伝えたいことはファーストビューとCTA直前の2箇所に置く。

### ★プロスペクト理論
「今だけ」「期間限定」「見ないと損」など損失回避を刺激する
コピーをCTA付近に配置する。

### アフォーダンス
ボタンは押せるように見せる。
box-shadow・hover時のtransformで立体感を出す。
`.btn:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(0,0,0,0.2); }`

### 指差し追従
人物写真の視線・指の向きをCTAボタンに向ける。

### アンカリング効果（比較表）
価格比較はライバルより先に自社を見せない。
比較表は自社が有利になる項目を選ぶ。

### ツァイガルニク効果
セクションの末尾に「続きを見る」「詳細はこちら」を置く。

### 返報性の法則
CV前に無料特典・プレゼントを提示する。
「まず受け取る」→「次にCV」の流れを作る。

### リフレーミング効果
クライアントのネガティブな特徴をポジティブに言い換える。
例：「小さな店」→「完全予約制の隠れ家」
例：「高い」→「一生に一度の品質」

### バンドワゴン効果
「累計〇〇人」「地域No.1」「〇〇年連続選ばれています」
を信頼セクションに必ず入れる。

### カリギュラ効果
ファーストビューのキャッチコピーに
「実は〇〇だった」「知らないと損する」などを活用する。

## 日付デザインテクニック（イベント・キャンペーンLPに必須）

### 基本原則：サイズ階層を必ず作る
- 年・曜日 → 小さく（0.55〜0.7em）
- 月・日　 → 大きく（メインサイズ）
- 時間　　 → 中くらい（0.75em）

### スタイル別CSS実装

#### ① フラット型（シンプル・ビジネス向け）
```css
.date { font-size: 2.5rem; font-weight: 900; }
.date-sub { font-size: 0.6em; font-weight: 400; display: block; }
```

#### ② 枠線型（フォーマル・イベント向け）
```css
.date-box {
  border: 2px solid #000;
  padding: 8px 16px;
  display: inline-block;
}
```

#### ③ 丸囲み型（かわいい・ポップ向け）
```css
.date-circle {
  width: 80px; height: 80px;
  border: 2px solid #000;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
```

#### ④ 左ボーダー型（すっきり・モダン向け）
```css
.date-border {
  border-left: 4px solid #000;
  padding-left: 12px;
}
```

#### ⑤ 塗り丸型（インパクト・目立たせたい）
```css
.date-filled {
  background: #000; color: #fff;
  border-radius: 50%;
  width: 80px; height: 80px;
  display: flex; align-items: center;
  justify-content: center;
  flex-direction: column;
}
```

#### ⑥ 角丸カード型（スマホ・アプリ風）
```css
.date-card {
  background: #000; color: #fff;
  border-radius: 12px;
  padding: 8px 16px;
}
```

#### ⑦ 矢印・期間型（セール・キャンペーン向け）
```css
.date-range::after {
  content: '→';
  margin: 0 8px;
  font-size: 0.8em;
}
```

### 期間表示のパターン
- 単日：6.20[Thu]
- 期間：6/24(Mon) → 8/30(Sun)
- 時間付き：6.20 Thu 10:00-11:00

### 使用判断
- フォーマル・ビジネス → ①フラット・④左ボーダー
- イベント・セミナー → ②枠線・⑥角丸カード
- ポップ・かわいい → ③丸囲み
- インパクト重視 → ⑤塗り丸
- キャンペーン・セール → ⑦矢印期間型

## フォント選定ルール

LP制作時はGoogle Fontsから以下の基準で選ぶ。
ヒアリングのQ15（デザイントーン）を参照して判断する。

- 温かみ・アットホーム → Kaisei Decol / Yomogi
- 高級感・上品 → Noto Serif JP / Shippori Mincho
- シンプル・モダン → Zen Kaku Gothic New / Noto Sans JP
- 和風・伝統的 → Zen Old Mincho / Noto Serif JP
- 元気・にぎやか → Rampart One / Dela Gothic One
- プロフェッショナル → BIZ UDPGothic / Noto Sans JP
- アウトドア・力強さ → Dela Gothic One
- ナチュラル・手作り感 → Yomogi / Kaisei Decol

### 原則
- 本文は必ずNoto Sans JP（可読性最優先）
- 見出しだけ個性的なフォントを使う
- フォントは最大2種類まで（見出し用＋本文用）
- font-display: swap を必ず入れる（表示速度対策）

## 線のデザインテクニック（見出し・強調に積極活用）

テキストの強調・装飾には以下の線スタイルをクライアントの
イメージに合わせて選んで実装する。

### 基本系
- 普通の線：`text-decoration: underline;`
- 上下挟む：`border-top` + `border-bottom;`
- 太い線：`border-bottom: 3px solid;`

### 個性系
- ドット線：`border-bottom: 2px dotted;`
- 波線：`text-decoration: underline wavy;`
- 破線：`border-bottom: 2px dashed;`
- 二重線：`border-bottom: 3px double;`
- 太い破線：`border-bottom: 4px dashed;`

### 演出系
- マーカー風：`background: linear-gradient(transparent 60%, #ffe066 60%);`
- かすれマーカー：同上 + rgba透過色
- 塗り帯：background色 + padding
- ずらし線：`::after` 擬似要素でoffset
- 手書き丸囲み：`border-radius: 50% 45% 55% 48%;`

### 使用判断
- フォーマル・クリーン → 普通の線・二重線
- ポップ・かわいい → 波線・ドット線
- おしゃれ・トレンド → マーカー風・かすれマーカー
- 手作り感・温かみ → 手書き丸囲み・破線
- 力強さ → 太い線・ペンキ風
