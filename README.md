# my-task

これは [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app) でブートストラップされた [Next.js](https://nextjs.org) プロジェクトです。

## 技術スタック

- **フレームワーク**: Next.js 16.0.3 (App Router)
- **ライブラリ**: React 19.2.0
- **言語**: TypeScript 5
- **パッケージマネージャー**: pnpm
- **リンター/フォーマッター**: Biome 2.2.0
- **ランタイム管理**: mise

## 必須要件

- Node.js 24.11.1 (mise経由で自動インストール)
- pnpm (mise経由で自動インストール)

## 開発環境のセットアップ

### 1. mise のインストール

```bash
# macOS/Linux
curl https://mise.run | sh

# または Homebrew
brew install mise
```

### 2. プロジェクトのセットアップ

```bash
# mise が自動的に Node.js と pnpm をインストール
mise install

# 依存関係のインストール
mise run install
# または
pnpm install
```

## はじめに

開発サーバーを起動します：

```bash
pnpm dev
```

ブラウザで [http://localhost:3000](http://localhost:3000) を開いて結果を確認してください。

`app/page.tsx` を編集することでページの編集を開始できます。ファイルを編集すると、ページが自動的に更新されます。

## 利用可能なコマンド

### 開発・ビルド

```bash
pnpm dev      # 開発サーバーを起動
pnpm build    # プロダクションビルド
pnpm start    # プロダクションサーバーを起動
```

### コード品質

```bash
pnpm lint     # Biomeでコードをチェック
pnpm format   # Biomeでコードを自動整形
```

### mise タスク

```bash
mise run install       # 依存関係のインストール
mise run build         # プロジェクトをビルド
mise run biome-start   # Biomeデーモンを起動
mise run biome-stop    # Biomeデーモンを停止
mise run fmt           # フォーマッターを実行
```

## プロジェクト構成

```
my-task/
├── app/              # Next.js App Router
│   ├── layout.tsx   # ルートレイアウト
│   └── page.tsx     # トップページ
├── public/          # 静的ファイル
├── biome.json       # Biome設定
├── mise.toml        # mise設定とタスク定義
├── next.config.ts   # Next.js設定
├── tsconfig.json    # TypeScript設定
└── package.json     # 依存関係とスクリプト
```

## 詳細情報

Next.jsについてさらに学ぶには、以下のリソースをご覧ください：

- [Next.js ドキュメント](https://nextjs.org/docs) - Next.jsの機能とAPIについて学ぶ
- [Next.js チュートリアル](https://nextjs.org/learn) - インタラクティブなNext.jsチュートリアル

[Next.js GitHubリポジトリ](https://github.com/vercel/next.js)もチェックしてみてください - フィードバックや貢献を歓迎します！

## Vercelへのデプロイ

Next.jsアプリをデプロイする最も簡単な方法は、Next.jsの作成者による [Vercelプラットフォーム](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) を使用することです。

詳細については、[Next.jsデプロイメントドキュメント](https://nextjs.org/docs/app/building-your-application/deploying)をご覧ください。
