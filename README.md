🌦 weather-forecast

Vue3 + TypeScript を用いた天気予報 Web アプリ

📌 プロジェクト概要

WeatherVue3 は、
Vue3 と TypeScript を用いて天気情報を取得・表示するシンプルな Web アプリです。

外部 API から取得した天気データをもとに、
現在の天気や気温を分かりやすく表示することを目的として制作しました。

本プロジェクトは、
Vue3（Composition API）と TypeScript、API 連携、コンポーネント分割の基礎理解を深めるための学習用アプリです。

🎯 制作の目的・背景

Vue3 を学習する中で、

TypeScript を用いた基本的な型の扱い方

API からデータを取得し、型を意識して管理する流れ

コンポーネントを分割して画面を構成する考え方

を、実際に動くアプリを通して理解したいと考え、本アプリを制作しました。

学習目的のプロジェクトとして、
「天気を確認する」というシンプルなユースケースを設定し、
コードの分かりやすさと構成の理解を重視しています。

🛠 使用技術

Vue.js（Vue3 / Composition API）

TypeScript

Vite

HTML / CSS

OpenWeatherMap API

Axios API

� プロジェクト構造

```
WeatherForecast/
├── public/                 # 静的リソース
├── src/
│   ├── components/         # Vueコンポーネント
│   │   └── WeatherCard.vue # 天気情報カードコンポーネント
│   ├── App.vue             # メインアプリコンポーネント
│   ├── main.ts             # アプリのエントリーポイント
│   ├── style.css           # グローバルスタイル
│   └── shims-vue.d.ts      # Vueの型定義
├── index.html              # HTMLテンプレート
├── package.json            # プロジェクト設定と依存関係
├── vite.config.ts          # Vite設定
├── tsconfig*.json          # TypeScript設定
└── README.md               # プロジェクトドキュメント
```

🚀 インストールと実行

### 環境要件

- Node.js ^20.19.0 || >=22.12.0

### 依存関係のインストール

```bash
npm install
```

### 開発モードでの実行

```bash
npm run dev
```

アプリが `http://localhost:5173` で起動します。

### 本番ビルド

```bash
npm run build
```

### 本番ビルドのプレビュー

```bash
npm run preview
```

### 型チェック

```bash
npm run type-check
```

�🔧 主な機能

天気情報 API からデータを取得

現在の天気・気温の表示

コンポーネント分割による画面構成

データ取得時の基本的なエラーハンドリング

💡 学んだこと・工夫した点

Vue3（Composition API）を用いた基本的な構成

API 連携の流れ（取得 → 加工 → 表示）

コンポーネントを分割することで、
見通しの良いコード構成になること

エラーが発生した際に、原因を一つずつ確認しながら対応する姿勢

📝 備考
本プロジェクトは、
Vue3 と TypeScript、Web API の基礎を学習する目的で制作した個人開発アプリです。
実務に近い形で Web アプリ開発の流れを体験することを重視しました。