# 技術スタック

## 概要

このドキュメントでは、my-taskプロジェクトで使用している技術スタックの詳細を説明します。

## フロントエンド

### フレームワーク

#### Next.js 16.0.3
- **役割**: Reactベースのフルスタックフレームワーク
- **使用理由**:
  - App Routerによる最新のルーティング機能
  - サーバーサイドレンダリング（SSR）とスタティックサイトジェネレーション（SSG）のサポート
  - 組み込みの画像最適化とフォント最適化
  - ファイルベースルーティング
  - API Routesによるバックエンド機能
- **公式ドキュメント**: https://nextjs.org/docs

### UIライブラリ

#### React 19.2.0
- **役割**: UIコンポーネントライブラリ
- **使用理由**:
  - コンポーネントベースの宣言的UI構築
  - 豊富なエコシステムとコミュニティ
  - 最新のReact機能（Server Components、Actions等）のサポート
- **公式ドキュメント**: https://react.dev/

## 開発言語

### TypeScript 5
- **役割**: 型安全なJavaScriptのスーパーセット
- **使用理由**:
  - 静的型チェックによるバグの早期発見
  - IDEの補完機能向上
  - コードの可読性と保守性の向上
  - リファクタリングの安全性
- **公式ドキュメント**: https://www.typescriptlang.org/

## ビルドツール・開発環境

### パッケージマネージャー

#### pnpm (latest)
- **役割**: Node.jsパッケージマネージャー
- **使用理由**:
  - ディスク容量の効率的な使用（ハードリンクによる共有）
  - npmより高速なインストール
  - 厳格な依存関係管理
  - monorepoサポート
- **公式ドキュメント**: https://pnpm.io/

### リンター・フォーマッター

#### Biome 2.2.0
- **役割**: 高速なリンター・フォーマッター
- **使用理由**:
  - ESLintとPrettierの代替として単一ツールで完結
  - Rustで実装された高速な実行速度
  - 設定が簡単でゼロコンフィグで動作
  - Next.jsとReactのルールを標準サポート
- **公式ドキュメント**: https://biomejs.dev/
- **設定ファイル**: `biome.json`
- **主な機能**:
  - コードフォーマット（indentStyle: space, indentWidth: 2）
  - リンティング（recommended rulesを使用）
  - インポートの自動整理
  - Gitとの統合

### ランタイム管理

#### mise
- **役割**: 開発環境のツールバージョン管理
- **使用理由**:
  - 複数のツール（Node.js、pnpm等）を一元管理
  - プロジェクトごとのバージョン固定
  - 自動的な環境セットアップ
  - タスクランナー機能
- **公式ドキュメント**: https://mise.jdx.dev/
- **設定ファイル**: `mise.toml`, `mise.local.toml`
- **管理対象**:
  - Node.js 24.11.1
  - pnpm latest

#### 定義済みタスク
```bash
mise run install       # 依存関係のインストール
mise run build         # プロジェクトのビルド
mise run biome-start   # Biomeデーモンの起動
mise run biome-stop    # Biomeデーモンの停止
mise run lint          # リンターの実行
mise run fmt           # フォーマッターの実行
```

## ランタイム

### Node.js 24.11.1
- **役割**: JavaScriptランタイム
- **使用理由**:
  - LTS版による安定性
  - 最新の言語機能のサポート
  - パフォーマンスの向上
- **管理方法**: miseによるバージョン固定

## スタイリング

### CSS Modules
- **役割**: コンポーネントスコープのCSS
- **ファイル**: `app/globals.css`, `app/page.module.css`
- **特徴**:
  - ローカルスコープによるスタイルの分離
  - CSS変数によるテーマ管理
  - ダークモード対応

## フォント

### Geist
- **役割**: Vercel公式フォントファミリー
- **種類**:
  - Geist Sans: サンセリフフォント
  - Geist Mono: 等幅フォント
- **最適化**: next/fontによる自動最適化

## 開発フロー

### コマンド

#### 開発
```bash
pnpm dev      # 開発サーバー起動（http://localhost:3000）
```

#### ビルド
```bash
pnpm build    # プロダクションビルド
pnpm start    # プロダクションサーバー起動
```

#### コード品質
```bash
pnpm lint     # Biomeでリントチェック
pnpm format   # Biomeでコード整形
```

## ディレクトリ構成

```
my-task/
├── app/                 # Next.js App Router
│   ├── favicon.ico     # ファビコン
│   ├── globals.css     # グローバルスタイル
│   ├── layout.tsx      # ルートレイアウト
│   ├── page.module.css # ページ固有スタイル
│   └── page.tsx        # トップページ
├── public/             # 静的ファイル
│   ├── next.svg
│   ├── vercel.svg
│   └── ...
├── _docs/              # プロジェクトドキュメント
│   └── tech-stack.md   # 技術スタック（このファイル）
├── biome.json          # Biome設定
├── mise.toml           # mise設定
├── mise.local.toml     # miseローカル設定（gitignore対象）
├── next.config.ts      # Next.js設定
├── tsconfig.json       # TypeScript設定
├── package.json        # 依存関係とスクリプト
└── pnpm-lock.yaml      # pnpmロックファイル
```

## バージョン管理

### Git
- **ブランチ戦略**: フィーチャーブランチワークフロー
- **メインブランチ**: `main`
- **開発ブランチ**: `feat/*`

### コミットメッセージ
- **規約**: Conventional Commits
- **フォーマット**: `<type>(<scope>): <subject>`
- **使用可能なtype**:
  - `feat`: 新機能
  - `fix`: バグ修正
  - `docs`: ドキュメント
  - `style`: コードスタイル
  - `refactor`: リファクタリング
  - `test`: テスト
  - `chore`: 雑務
  - `build`: ビルドシステム
  - `ci`: CI設定

## 環境変数

### 設定ファイル
- `.env.local`: ローカル環境変数（gitignore対象）
- `.env.local.example`: 環境変数のテンプレート

