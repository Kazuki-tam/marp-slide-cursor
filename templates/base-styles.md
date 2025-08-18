# 基本スタイルテンプレート

## フロントマター設定パターン

### パターン1: ビジネス提案用
```yaml
---
marp: true
theme: gaia
paginate: true
backgroundColor: #fff
size: 16:9
style: |
  section {
    font-size: 20px;
    line-height: 1.6;
    padding: 50px;
  }
  h1 { font-size: 2.5em; margin-bottom: 0.5em; }
  h2 { font-size: 2em; margin-bottom: 0.4em; }
  h3 { font-size: 1.5em; margin-bottom: 0.3em; }
  ul, ol { margin: 0.5em 0; }
  li { margin-bottom: 0.3em; }
  table { 
    font-size: 0.9em; 
    margin: 1em auto;
    max-width: 90%;
  }
  img { max-width: 100%; height: auto; }
  .lead h1 { font-size: 3em; }
  .lead h2 { font-size: 2.2em; }
---
```

### パターン2: 技術提案用
```yaml
---
marp: true
theme: uncover
paginate: true
backgroundColor: #fafafa
size: 16:9
style: |
  section {
    font-size: 18px;
    line-height: 1.5;
    padding: 40px;
  }
  h1 { font-size: 2.2em; color: #2c5282; }
  h2 { font-size: 1.8em; color: #2d3748; }
  h3 { font-size: 1.4em; color: #4a5568; }
  code { 
    font-size: 0.85em; 
    background: #f7fafc;
    padding: 0.2em 0.4em;
    border-radius: 3px;
  }
  pre {
    font-size: 0.8em;
    max-height: 400px;
    overflow-y: auto;
  }
  table { font-size: 0.85em; }
  .lead { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
  .lead h1, .lead h2 { color: white; }
---
```

### パターン3: 報告書用
```yaml
---
marp: true
theme: default
paginate: true
backgroundColor: #ffffff
size: 16:9
header: 'プロジェクト報告書'
footer: '© 2024 Company Name'
style: |
  section {
    font-size: 19px;
    line-height: 1.6;
    padding: 45px;
  }
  header { 
    font-size: 0.7em; 
    color: #666; 
    text-align: right;
  }
  footer { 
    font-size: 0.7em; 
    color: #666; 
    text-align: center;
  }
  h1 { 
    font-size: 2.3em; 
    border-bottom: 3px solid #4299e1;
    padding-bottom: 0.2em;
  }
  h2 { 
    font-size: 1.9em; 
    border-left: 5px solid #4299e1;
    padding-left: 0.3em;
  }
  table {
    font-size: 0.85em;
    border-collapse: collapse;
    margin: 1em auto;
  }
  th, td {
    border: 1px solid #e2e8f0;
    padding: 0.5em;
  }
  th { background-color: #f7fafc; }
---
```

---

## レスポンシブ対応スタイル

### モバイル・小画面対応
```css
@media (max-width: 768px) {
  section {
    font-size: 16px !important;
    padding: 30px !important;
  }
  h1 { font-size: 2em !important; }
  h2 { font-size: 1.6em !important; }
  h3 { font-size: 1.3em !important; }
  table { font-size: 0.75em !important; }
  img { max-width: 100% !important; }
}
```

### 大画面対応
```css
@media (min-width: 1200px) {
  section {
    font-size: 22px;
    padding: 60px;
  }
  .lead h1 { font-size: 3.5em; }
  .lead h2 { font-size: 2.5em; }
}
```

---

## 色彩パターン

### コーポレートブルー
```css
:root {
  --primary-color: #2c5282;
  --secondary-color: #4299e1;
  --accent-color: #63b3ed;
  --text-color: #2d3748;
  --background-color: #f7fafc;
}
```

### ウォームカラー
```css
:root {
  --primary-color: #c53030;
  --secondary-color: #e53e3e;
  --accent-color: #fc8181;
  --text-color: #2d3748;
  --background-color: #fffaf0;
}
```

### モノクローム
```css
:root {
  --primary-color: #2d3748;
  --secondary-color: #4a5568;
  --accent-color: #718096;
  --text-color: #1a202c;
  --background-color: #ffffff;
}
```

---

## アイコン・装飾パターン

### ステータスアイコン
```markdown
✅ 完了・成功
🟡 進行中・注意
🔴 課題・問題
⚠️ 警告・リスク
💡 アイデア・提案
🚀 将来・展望
📊 データ・分析
🎯 目標・ターゲット
⏰ 時間・スケジュール
💰 コスト・予算
```

### 装飾罫線
```markdown
---
***
___
<!-- 水平線のバリエーション -->
```

### 強調ボックス
```css
.highlight-box {
  background: #e6fffa;
  border-left: 5px solid #38b2ac;
  padding: 1em;
  margin: 1em 0;
}

.warning-box {
  background: #fffbeb;
  border-left: 5px solid #f6ad55;
  padding: 1em;
  margin: 1em 0;
}

.info-box {
  background: #ebf8ff;
  border-left: 5px solid #4299e1;
  padding: 1em;
  margin: 1em 0;
}
```

---

## タイポグラフィ設定

### 日本語フォント最適化
```css
section {
  font-family: 
    "Hiragino Kaku Gothic ProN", 
    "Hiragino Sans", 
    "Noto Sans CJK JP", 
    "Yu Gothic Medium", 
    "Meiryo", 
    sans-serif;
  font-feature-settings: "palt";
  letter-spacing: 0.02em;
}

code, pre {
  font-family: 
    "Fira Code", 
    "Source Code Pro", 
    "Consolas", 
    "Monaco", 
    monospace;
}
```

### 行間・余白調整
```css
h1, h2, h3 {
  line-height: 1.2;
  margin-top: 1em;
  margin-bottom: 0.5em;
}

p {
  line-height: 1.6;
  margin-bottom: 1em;
}

ul, ol {
  line-height: 1.5;
  margin: 0.5em 0;
  padding-left: 1.5em;
}

li {
  margin-bottom: 0.3em;
}
```

---

## 画像・メディア制御

### 画像サイズ制御
```css
/* 標準画像サイズ */
.img-small { max-width: 300px; }
.img-medium { max-width: 500px; }
.img-large { max-width: 700px; }
.img-full { max-width: 100%; }

/* アスペクト比維持 */
img {
  height: auto;
  object-fit: contain;
}
```

### Mermaid図表制御
```css
.mermaid {
  max-width: 800px;
  margin: 1em auto;
}

.mermaid svg {
  max-width: 100%;
  height: auto;
}
```

---

## テーブルスタイル

### 基本テーブル
```css
table {
  width: 90%;
  margin: 1em auto;
  border-collapse: collapse;
  font-size: 0.85em;
}

th, td {
  padding: 0.7em 0.5em;
  text-align: left;
  border-bottom: 1px solid #e2e8f0;
}

th {
  background-color: #f7fafc;
  font-weight: 600;
  border-bottom: 2px solid #cbd5e0;
}

tr:hover {
  background-color: #f9fafb;
}
```

### コンパクトテーブル
```css
.table-compact {
  font-size: 0.75em;
}

.table-compact th,
.table-compact td {
  padding: 0.4em 0.3em;
}
```

---

## アニメーション・エフェクト（控えめ）

### フェードイン効果
```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.fade-in {
  animation: fadeIn 0.5s ease-out;
}
```

### ホバー効果
```css
.hover-scale:hover {
  transform: scale(1.02);
  transition: transform 0.2s ease;
}

.hover-shadow:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transition: box-shadow 0.2s ease;
}
```

---

## プリント対応

### 印刷用スタイル
```css
@media print {
  section {
    font-size: 12pt;
    line-height: 1.4;
    padding: 1cm;
  }
  
  h1 { font-size: 18pt; }
  h2 { font-size: 16pt; }
  h3 { font-size: 14pt; }
  
  .no-print { display: none; }
  
  a:after {
    content: " (" attr(href) ")";
    font-size: 0.8em;
    color: #666;
  }
}
```
