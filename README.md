# Marp + Cursor AI スライド生成環境

MarpとCursor AIを組み合わせて、LLM指示でプレゼンテーション資料を自動生成できるテンプレート環境です。

## 📁 ディレクトリ構成

```
slide-agent/
├── .cursor/
│   └── rules/
│       ├── core-rule.mdc              # 基本ルール
│       └── marp-slide-generation.mdc  # Marp専用ルール
├── templates/
│   ├── business-proposal.md           # ビジネス提案書テンプレート
│   ├── technical-proposal.md          # 技術提案書テンプレート
│   └── project-report.md              # プロジェクト報告書テンプレート
├── presentations/
│   ├── sample-presentation.md         # サンプルスライド
│   └── assets/
│       ├── images/                    # 画像ファイル
│       └── themes/                    # カスタムテーマ
└── README.md
```

## 🚀 セットアップ

### 1. VS Code拡張機能のインストール

必要な拡張機能をインストールしてください：

- **Marp for VS Code** (`marp-team.marp-vscode`)
- **Cursor** (AI機能を使用する場合)

### 2. Marp CLIのインストール（オプション）

コマンドライン操作が必要な場合：

```bash
npm install -g @marp-team/marp-cli
```

## 📖 スライド作成ガイド

### 📏 レイアウトパターン

以下のパターンを活用して一貫性のあるスライドを作成：

- **Pattern 1**: タイトルスライド
- **Pattern 2**: リストスライド（最大5項目）
- **Pattern 3**: 比較表スライド（最大4列）
- **Pattern 4**: 図表メインスライド
- **Pattern 5**: 2カラムレイアウト
- **Pattern 6**: コードブロックスライド
- **Pattern 7**: 数字・統計スライド
- **Pattern 8**: プロセス・フロースライド
- **Pattern 9**: 課題・解決策スライド
- **Pattern 10**: まとめスライド

### 🎨 デザイン原則

1. **1スライド1メッセージ**: 伝えたいことを1つに絞る
2. **情報量制限**: 画面内に収まる適切な分量
3. **視認性重視**: 読みやすいフォントサイズ・余白
4. **統一感**: 一貫したレイアウトパターン

#### サイズ制限ガイドライン

**テキスト**:
- リスト項目: 最大5個
- 表の列数: 最大4列
- 1行の文字数: 40文字以内

**画像・図表**:
- 標準画像幅: 700px
- Mermaid図: 最大800px相当
- コードブロック: 10行以内

**アイコン使用例**:
- ✅ 完了・成功
- 🔴 課題・問題  
- 💡 提案・アイデア
- 📊 データ・分析
- 🚀 将来・展望

## 💡 使用方法

### LLM指示でスライド生成

Cursor AIに以下のような指示を出してください：

### テンプレートの選択

目的に応じてテンプレートを選択：

**ビジネス提案向け**: `business-proposal.md`
- エグゼクティブ向けの構成
- ROI・コスト重視
- ビジュアル中心のレイアウト

**技術提案向け**: `technical-proposal.md`
- 技術者向けの詳細設計
- アーキテクチャ図・コード例
- 実装・検証計画

**報告書向け**: `project-report.md`
- 進捗・実績の可視化
- 数値データの効果的表示
- 課題・リスクの整理

## 📋 Marp記法リファレンス

### 基本構造

```markdown
---
marp: true
theme: gaia
---

# タイトルスライド

---

# 通常のスライド

内容...
```

### 画像・レイアウト

```markdown
![bg left:40% 80%](image.jpg)     # 背景画像（左40%、80%サイズ）
![width:300px](image.jpg)         # 幅指定
![height:200px](image.jpg)        # 高さ指定
![bg fit](image.jpg)              # 背景にフィット
```

### ページ固有設定

```markdown
<!-- _class: lead -->           # このページのみクラス適用
<!-- _backgroundColor: #123 --> # このページのみ背景色変更
```

### カスタマイズ

フロントマターで設定をカスタマイズ：

```yaml
---
marp: true
theme: gaia                    # テーマ (default, gaia, uncover)
paginate: true                # ページ番号
backgroundColor: #fff         # 背景色
size: 16:9                   # アスペクト比
style: |                      # カスタムCSS
  section { font-size: 20px; }
---
```

## 🎨 テーマとカスタマイズ

### 標準テーマ

- **default**: シンプルな白背景
- **gaia**: モダンなデザイン
- **uncover**: ダークな背景

### スタイル設定

目的に応じたスタイルを選択：

- **ビジネス提案用**: Gaiaテーマ + 企業カラー
- **技術提案用**: Uncoverテーマ + 技術者向けフォント
- **報告書用**: Defaultテーマ + 読みやすさ重視

### 色彩パターン

**コーポレートブルー**:
- プライマリ: #2c5282
- セカンダリ: #4299e1

**ウォームカラー**:
- プライマリ: #c53030
- セカンダリ: #e53e3e

**モノクローム**:
- プライマリ: #2d3748
- セカンダリ: #4a5568

### カスタムテーマ

`presentations/assets/themes/` にCSSファイルを配置してカスタムテーマを作成できます。

## 📤 エクスポート

### VS Code内でエクスポート

1. Marpファイルを開く
2. `Ctrl+Shift+P` (macOS: `Cmd+Shift+P`)
3. "Marp: Export slide deck..." を選択
4. フォーマットを選択（HTML, PDF, PPTX等）

### CLIでエクスポート

```bash
# PDF出力
marp presentations/sample-presentation.md --pdf

# HTML出力
marp presentations/sample-presentation.md --html

# PowerPoint出力
marp presentations/sample-presentation.md --pptx
```

## ✅ 品質チェックリスト

スライド作成後の確認項目：

### レイアウト確認
- [ ] 1スライド1メッセージが守られている
- [ ] 情報量が適切（画面内に収まる）
- [ ] 画像サイズが指定されている
- [ ] 表の列数が4列以下
- [ ] リスト項目が5個以下

### 視認性確認  
- [ ] フォントサイズが適切
- [ ] 色のコントラストが十分
- [ ] 余白が適切に配置されている
- [ ] アニメーション・装飾が過剰でない

### 一貫性確認
- [ ] 統一されたテーマ・スタイル
- [ ] アイコンの統一的使用
- [ ] フォントファミリーの統一

## 🔧 トラブルシューティング

### よくある問題と対策

#### プレビューが表示されない
- Marp for VS Code拡張機能がインストールされているか確認
- ファイルの先頭に `marp: true` があるか確認

#### 画像が表示されない
- 画像パスが正しいか確認
- 相対パスを使用しているか確認

#### テーマが適用されない
- フロントマターの `theme` 設定を確認
- テーマ名のスペルミスがないか確認

#### テキストが多すぎる
**対策**: 要点を3つに絞る、詳細は別スライドへ

#### 表が画面からはみ出る  
**対策**: 列数を減らす、縦方向のレイアウトに変更

#### 画像が適切でない
**対策**: `width:`または`height:`でサイズ指定

#### Mermaid図が複雑すぎる
**対策**: 図を分割、ノード数を6個以下に制限

### レンダリング問題
1. VS Code Marp拡張の再起動
2. キャッシュクリア
3. 画像パスの確認

### スタイル適用されない
1. フロントマターの記法確認
2. CSS構文エラーチェック
3. テーマとの競合確認

## 🤝 貢献

このテンプレート環境の改善にご協力ください：

1. 新しいテンプレートの追加
2. ルールの改善
3. ドキュメントの拡充
4. バグ報告・機能要望

## 📝 ライセンス

このプロジェクトはMITライセンスのもとで公開されています。

## 🔗 関連リンク

### 公式ドキュメント
- [Marp公式サイト](https://marp.app/)
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
- [Marp CLI](https://github.com/marp-team/marp-cli)
- [Cursor](https://cursor.com/)

### 参考資料
- [Markdown記法ガイド](https://www.markdownguide.org/)
- [プレゼンテーションデザインのベストプラクティス](https://www.presentation-guru.com/)

### 配布時の注意点
- 画像パスの確認
- フォントの埋め込み
- ファイルサイズの最適化

---

**Marp + Cursor AI環境で効率的なプレゼンテーション作成を！**
