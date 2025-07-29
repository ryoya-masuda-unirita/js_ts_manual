# JavaScript/TypeScript プログラミング マニュアル

## 目次

- [はじめに](#はじめに)
  - [対象読者](#対象読者)
  - [前提知識](#前提知識)

- [Part 1: 開発環境とツール](#part-1-開発環境とツール)
  - [1. 開発環境の準備](#1-開発環境の準備)
    - [1.1 Node.jsのセットアップ](#11-nodejsのセットアップ)
    - [1.2 Visual Studio Codeの設定](#12-visual-studio-codeの設定)
    - [1.3 開発ツールの導入](#13-開発ツールの導入)
  - [2. プロジェクトの基本構造](#2-プロジェクトの基本構造)
    - [2.1 ディレクトリ構成](#21-ディレクトリ構成)
    - [2.2 設定ファイルの理解](#22-設定ファイルの理解)
    - [2.3 開発サーバーの設定](#23-開発サーバーの設定)

- [Part 2: JavaScript基礎](#part-2-javascript基礎)
  - [1. 変数とデータ型](#1-変数とデータ型)
    - [1.1 変数宣言の基本](#11-変数宣言の基本)
    - [1.2 プリミティブ型](#12-プリミティブ型)
    - [1.3 参照型](#13-参照型)
  - [2. 関数とスコープ](#2-関数とスコープ)
    - [2.1 関数の基本](#21-関数の基本)
    - [2.2 スコープとクロージャ](#22-スコープとクロージャ)
    - [2.3 非同期処理](#23-非同期処理)
  - [3. オブジェクト指向の基礎](#3-オブジェクト指向の基礎)
    - [3.1 オブジェクトの基本](#31-オブジェクトの基本)
    - [3.2 モジュール化](#32-モジュール化)

- [Part 3: TypeScript基礎](#part-3-typescript基礎)
  - [1. TypeScriptの基本](#1-typescriptの基本)
    - [1.1 型アノテーション](#11-型アノテーション)
    - [1.2 インターフェース](#12-インターフェース)
    - [1.3 クラス](#13-クラス)
  - [2. 高度な型システム](#2-高度な型システム)
    - [2.1 ジェネリクス](#21-ジェネリクス)
    - [2.2 型ガード](#22-型ガード)
    - [2.3 デコレータ](#23-デコレータ)

- [Part 4: 実践的な開発手法](#part-4-実践的な開発手法)
  - [1. 効率的な開発フロー](#1-効率的な開発フロー)
    - [1.1 バージョン管理](#11-バージョン管理)
    - [1.2 デバッグ手法](#12-デバッグ手法)
  - [2. テストと品質管理](#2-テストと品質管理)
    - [2.1 ユニットテスト](#21-ユニットテスト)
    - [2.2 統合テスト](#22-統合テスト)
  - [3. パフォーマンス最適化](#3-パフォーマンス最適化)
    - [3.1 ビルド最適化](#31-ビルド最適化)
    - [3.2 実行時最適化](#32-実行時最適化)

- [Part 5: セキュリティと保守性](#part-5-セキュリティと保守性)
  - [1. セキュリティ対策](#1-セキュリティ対策)
    - [1.1 一般的な脆弱性対策](#11-一般的な脆弱性対策)
    - [1.2 セキュアなコーディング](#12-セキュアなコーディング)
  - [2. コード品質の維持](#2-コード品質の維持)
    - [2.1 コーディング規約](#21-コーディング規約)
    - [2.2 リファクタリング](#22-リファクタリング)

- [補足資料](#補足資料)
  - [索引](#索引)
  - [用語集](#用語集)
  - [チートシート](#チートシート)
  - [参考リソース](#参考リソース)

---

## はじめに

このマニュアルは、JavaScriptとTypeScriptの基礎から応用までを体系的に学ぶためのガイドです。プログラミング初心者の方でも理解できるよう、丁寧な説明と実践的な例を多く含んでいます。

各セクションでは、単なる機能の説明だけでなく、「なぜそうするのか」「どのように動くのか」という原理の解説も含めています。これにより、コードをコピー&ペーストするのではなく、理解して実装できる力を養うことを目指しています。

### マニュアルの使い方

1. **段階的な学習**
   - 基礎から応用へと順番に進んでいく構成
   - 各セクションの終わりに理解度確認の問題を用意
   - 実践的な演習を通じて知識を定着

2. **環境構築から始める**
   - Part 1で開発環境の構築方法を詳しく解説
   - 必要なツールのインストールと設定を丁寧に説明
   - トラブルシューティングのガイドも提供

3. **実践的な例示**
   - 実際のプロジェクトで使用される具体例を提供
   - コードスニペットと詳細な説明の組み合わせ
   - よくあるエラーとその解決方法も解説

4. **補足資料の活用**
   - 用語集で専門用語をいつでも確認可能
   - チートシートで主要な構文を素早く参照
   - 索引で必要な情報にすぐにアクセス

### 対象読者

このマニュアルは、以下のような方々を対象としています：

1. **プログラミングを始めたい初学者**
   - プログラミングの基礎から学びたい方
   - Web開発に興味がある方
   - 体系的に学習したい方

2. **JavaScriptから学習を始めたい方**
   - Web開発の第一歩として
   - フロントエンド開発を目指す方
   - 動的なWebサイトを作りたい方

3. **TypeScriptの基礎から学びたい方**
   - 型安全なコーディングを学びたい方
   - より堅牢なアプリケーションを作りたい方
   - JavaScriptからのステップアップを目指す方

4. **Webフロントエンド開発に興味がある方**
   - モダンなWeb開発手法を学びたい方
   - 実践的な開発スキルを身につけたい方
   - プロフェッショナルな開発者を目指す方

### 前提知識

このマニュアルを効果的に活用するために、以下の基礎知識があることを推奨します：

1. **PCの基本的な操作ができること**
   - ファイルやフォルダの操作
   - テキストエディタの基本的な使用
   - Webブラウザの操作

2. **HTML/CSSの基礎的な知識**
   - HTMLの基本的な構造の理解
   - 主要なHTMLタグの使い方
   - 基本的なCSSスタイリング

3. **Visual Studio Codeなどのエディタの基本的な使い方**
   - ファイルの作成と編集
   - 基本的なショートカットキー
   - エディタの設定変更

ただし、これらの知識が不完全な場合でも、必要に応じて補足説明を加えながら進めていきますので、心配せずに学習を始めることができます。

### 学習の進め方

1. **基礎固め（Part 1-2）**
   - 開発環境の整備から始める
   - JavaScriptの基本概念を理解
   - 実践的な例を通じて学習

2. **TypeScriptへの移行（Part 3）**
   - 型システムの基礎を学ぶ
   - JavaScriptとの違いを理解
   - 型安全なコーディングの習得

3. **実践力の向上（Part 4-5）**
   - 実際の開発手法の習得
   - テストとデバッグの方法
   - セキュリティと保守性の考慮

4. **継続的な学習**
   - 補足資料を活用
   - 実践的な演習に取り組む
   - 最新情報のキャッチアップ

それでは、実際の学習を始めていきましょう。次のセクションから、開発環境の構築について詳しく説明していきます。

## Part 1: 開発環境とツール

モダンなJavaScript/TypeScript開発では、効率的な開発を行うために適切な開発環境とツールの設定が不可欠です。このセクションでは、開発に必要な環境構築とツールの導入について、段階的に説明していきます。

### 1. 開発環境の準備

#### 1.1 Node.jsのセットアップ

Node.jsは、JavaScriptの実行環境です。サーバーサイドでJavaScriptを実行できるだけでなく、開発に必要な様々なツールを提供します。

##### インストール手順

1. **Node.jsのダウンロードとインストール**
   - [Node.js公式サイト](https://nodejs.org/)にアクセス
   - LTS（Long Term Support）バージョンをダウンロード
     ```bash
     # インストール後、バージョン確認
     node --version
     npm --version
     ```

2. **npmの初期設定**
   ```bash
   # グローバル設定の確認
   npm config list
   
   # 基本設定
   npm config set init-author-name "あなたの名前"
   npm config set init-license "MIT"
   ```

##### バージョン管理（nvm）の導入

複数のNode.jsバージョンを管理するために、nvmを使用します。

1. **nvmのインストール**

   Linuxの場合:
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
   ```

   Windowsの場合:
   - [nvm-windows](https://github.com/coreybutler/nvm-windows/releases)をダウンロード
   - インストーラーを実行

2. **nvmの基本的な使い方**
   ```bash
   # 利用可能なバージョンの一覧表示
   nvm ls-remote
   
   # 特定のバージョンをインストール
   nvm install 16.14.0  # 例: v16.14.0をインストール
   
   # 使用するバージョンの切り替え
   nvm use 16.14.0
   
   # デフォルトのバージョン設定
   nvm alias default 16.14.0
   ```

##### npmの基本的な使い方

npmは、Node.jsのパッケージマネージャーです。プロジェクトの依存関係を管理します。

1. **プロジェクトの初期化**
   ```bash
   # 新しいディレクトリの作成と移動
   mkdir my-project
   cd my-project
   
   # package.jsonの作成（対話式）
   npm init
   
   # または、デフォルト設定で作成
   npm init -y
   ```

2. **パッケージのインストール**
   ```bash
   # プロジェクトの依存パッケージをインストール
   npm install パッケージ名
   
   # 開発時のみ必要なパッケージをインストール
   npm install --save-dev パッケージ名
   
   # グローバルにパッケージをインストール
   npm install -g パッケージ名
   ```

3. **スクリプトの実行**
   ```json
   // package.jsonの例
   {
     "scripts": {
       "start": "node src/index.js",
       "dev": "nodemon src/index.js",
       "build": "tsc",
       "test": "jest"
     }
   }
   ```
   ```bash
   # スクリプトの実行
   npm run スクリプト名
   ```

#### 1.2 Visual Studio Codeの設定

Visual Studio Code（VSCode）は、Microsoft社が開発した無料のコードエディタです。豊富な機能と拡張性により、JavaScript/TypeScript開発に最適です。

##### 推奨プラグイン

1. **必須プラグイン**
   - ESLint: コード品質とスタイルのチェック
   - Prettier: コードフォーマッター
   - JavaScript and TypeScript Nightly: 最新の言語機能サポート
   - Path Intellisense: ファイルパスの自動補完
   - GitLens: Gitの統合機能強化

2. **便利なプラグイン**
   - Auto Import: 自動インポート
   - npm Intellisense: npmモジュールの自動補完
   - Error Lens: エラー表示の強化
   - Code Spell Checker: スペルチェック
   - Todo Tree: TODOコメントの管理

##### 開発効率を上げる設定

1. **基本設定（settings.json）**
   ```json
   {
     "editor.formatOnSave": true,
     "editor.defaultFormatter": "esbenp.prettier-vscode",
     "editor.codeActionsOnSave": {
       "source.fixAll.eslint": true
     },
     "javascript.updateImportsOnFileMove.enabled": "always",
     "typescript.updateImportsOnFileMove.enabled": "always",
     "editor.tabSize": 2,
     "editor.rulers": [80, 100],
     "files.autoSave": "onFocusChange",
     "terminal.integrated.defaultProfile.windows": "Git Bash",
     "workbench.colorTheme": "Default Dark+"
   }
   ```

2. **キーボードショートカット**

   Windows/Linux:
   - ファイル保存: `Ctrl + S`
   - クイックフィックス: `Ctrl + .`
   - 定義へ移動: `F12`
   - ファイル内検索: `Ctrl + F`
   - プロジェクト内検索: `Ctrl + Shift + F`
   - ターミナル表示/非表示: `` Ctrl + ` ``

   macOS:
   - ファイル保存: `Cmd + S`
   - クイックフィックス: `Cmd + .`
   - 定義へ移動: `F12`
   - ファイル内検索: `Cmd + F`
   - プロジェクト内検索: `Cmd + Shift + F`
   - ターミナル表示/非表示: `` Cmd + ` ``

##### デバッグ環境の構築

1. **launch.jsonの設定**
   ```json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "type": "node",
         "request": "launch",
         "name": "Debug Current File",
         "program": "${file}",
         "skipFiles": ["<node_internals>/**"],
         "outFiles": ["${workspaceFolder}/dist/**/*.js"]
       },
       {
         "type": "chrome",
         "request": "launch",
         "name": "Debug in Chrome",
         "url": "http://localhost:3000",
         "webRoot": "${workspaceFolder}/src"
       }
     ]
   }
   ```

2. **デバッグの基本操作**
   - ブレークポイントの設定: 行番号の左をクリック
   - デバッグ開始: `F5`
   - ステップ実行: `F10`
   - ステップイン: `F11`
   - ステップアウト: `Shift + F11`
   - デバッグ停止: `Shift + F5`

#### 1.3 開発ツールの導入

##### ESLint

ESLintは、コードの品質を保つための静的解析ツールです。

1. **インストール**
   ```bash
   npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
   npx eslint --init
   ```

2. **基本設定（.eslintrc.js）**
   ```javascript
   module.exports = {
     root: true,
     env: {
       browser: true,
       es2021: true,
       node: true,
     },
     extends: [
       'eslint:recommended',
       'plugin:@typescript-eslint/recommended',
     ],
     parser: '@typescript-eslint/parser',
     parserOptions: {
       ecmaVersion: 12,
       sourceType: 'module',
     },
     plugins: ['@typescript-eslint'],
     rules: {
       'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
       'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
       '@typescript-eslint/explicit-module-boundary-types': 'off',
       '@typescript-eslint/no-explicit-any': 'warn',
     },
   };
   ```

##### Prettier

Prettierは、コードを一貫したスタイルにフォーマットするツールです。

1. **インストール**
   ```bash
   npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
   ```

2. **設定ファイル（.prettierrc）**
   ```json
   {
     "semi": true,
     "singleQuote": true,
     "tabWidth": 2,
     "trailingComma": "es5",
     "printWidth": 100,
     "bracketSpacing": true,
     "arrowParens": "avoid"
   }
   ```

3. **ESLintとの統合（.eslintrc.js）**
   ```javascript
   module.exports = {
     extends: [
       // ... 他の設定 ...
       'plugin:prettier/recommended'
     ],
   };
   ```

##### Jest

Jestは、JavaScriptのテストフレームワークです。

1. **インストール**
   ```bash
   npm install --save-dev jest @types/jest ts-jest
   ```

2. **設定ファイル（jest.config.js）**
   ```javascript
   module.exports = {
     preset: 'ts-jest',
     testEnvironment: 'node',
     roots: ['<rootDir>/src'],
     testMatch: [
       '**/__tests__/**/*.+(ts|tsx|js)',
       '**/?(*.)+(spec|test).+(ts|tsx|js)',
     ],
     transform: {
       '^.+\\.(ts|tsx)$': 'ts-jest',
     },
     coverageDirectory: 'coverage',
     collectCoverageFrom: [
       'src/**/*.{js,jsx,ts,tsx}',
       '!src/**/*.d.ts',
     ],
   };
   ```

3. **package.jsonへのスクリプト追加**
   ```json
   {
     "scripts": {
       "test": "jest",
       "test:watch": "jest --watch",
       "test:coverage": "jest --coverage"
     }
   }
   ```

### 2. プロジェクトの基本構造

TypeScript/JavaScriptプロジェクトの効率的な開発には、適切なプロジェクト構造が重要です。このセクションでは、推奨されるディレクトリ構成や各種設定ファイルについて説明します。

#### 2.1 ディレクトリ構成

##### 基本的なディレクトリ構造

```
project-root/
├── src/                # ソースコードのルートディレクトリ
│   ├── types/         # 型定義ファイル
│   ├── utils/         # ユーティリティ関数
│   ├── services/      # ビジネスロジック
│   ├── constants/     # 定数定義
│   └── index.ts       # エントリーポイント
├── tests/             # テストファイル
│   ├── unit/         # ユニットテスト
│   └── integration/  # 統合テスト
├── dist/              # ビルド成果物
├── docs/              # ドキュメント
├── node_modules/      # 依存パッケージ
├── .git/              # Gitリポジトリ
├── .gitignore         # Gitの除外設定
├── package.json       # プロジェクト設定
├── package-lock.json  # 依存関係のロック
├── tsconfig.json      # TypeScript設定
├── .eslintrc.js      # ESLint設定
├── .prettierrc       # Prettier設定
├── jest.config.js    # Jestテスト設定
└── README.md         # プロジェクト説明
```

##### ディレクトリの役割と責務

1. **src/**: ソースコードのメインディレクトリ
   - `types/`: TypeScriptの型定義ファイル
   - `utils/`: 共通のユーティリティ関数
   - `services/`: ビジネスロジックの実装
   - `constants/`: 定数の定義
   - `index.ts`: アプリケーションのエントリーポイント

2. **tests/**: テストコードのディレクトリ
   - `unit/`: 単体テスト
   - `integration/`: 統合テスト
   - `__mocks__/`: モックオブジェクト

3. **dist/**: ビルド後のファイル
   - コンパイル済みのJavaScriptファイル
   - ソースマップ
   - 型定義ファイル（.d.ts）

4. **docs/**: プロジェクトのドキュメント
   - API仕様書
   - 設計ドキュメント
   - 開発ガイドライン

##### ファイル命名規則

1. **TypeScriptファイル**
   ```typescript
   // 一般的なソースファイル
   user-service.ts
   
   // インターフェース定義
   user.interface.ts
   
   // 型定義
   user.types.ts
   
   // テストファイル
   user-service.test.ts
   user-service.spec.ts
   ```

2. **特殊なファイル**
   ```typescript
   // バレル（再エクスポート）ファイル
   index.ts
   
   // 定数定義
   constants.ts
   
   // 環境設定
   environment.ts
   ```

#### 2.2 設定ファイルの理解

##### package.jsonの構造と役割

```json
{
  "name": "project-name",
  "version": "1.0.0",
  "description": "プロジェクトの説明",
  "main": "dist/index.js",
  "types": "dist/index.d.ts",
  "scripts": {
    "start": "node dist/index.js",
    "dev": "ts-node-dev --respawn src/index.ts",
    "build": "tsc",
    "test": "jest",
    "lint": "eslint 'src/**/*.{js,ts}'",
    "format": "prettier --write 'src/**/*.{js,ts}'",
    "clean": "rimraf dist",
    "prepare": "husky install"
  },
  "dependencies": {
    // 本番環境で必要なパッケージ
  },
  "devDependencies": {
    // 開発時のみ必要なパッケージ
  },
  "engines": {
    "node": ">=14.0.0"
  }
}
```

##### tsconfig.jsonの重要な設定

```json
{
  "compilerOptions": {
    // ECMAScriptのターゲットバージョン
    "target": "es2020",
    // モジュールシステム
    "module": "commonjs",
    // 厳格な型チェック
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    // モジュール解決
    "moduleResolution": "node",
    "baseUrl": "./",
    "paths": {
      "@/*": ["src/*"]
    },
    // 出力設定
    "outDir": "./dist",
    "sourceMap": true,
    // その他の設定
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "declaration": true
  },
  "include": [
    "src/**/*"
  ],
  "exclude": [
    "node_modules",
    "dist",
    "**/*.test.ts"
  ]
}
```

##### 環境変数の管理

1. **.env**ファイルの使用
   ```plaintext
   # .env
   API_KEY=your-api-key
   DATABASE_URL=mongodb://localhost:27017
   NODE_ENV=development
   ```

2. **環境別の設定ファイル**
   ```plaintext
   .env                # デフォルト環境変数
   .env.development    # 開発環境用
   .env.test          # テスト環境用
   .env.production    # 本番環境用
   ```

3. **環境変数の型定義**
   ```typescript
   // src/types/env.d.ts
   declare namespace NodeJS {
     interface ProcessEnv {
       NODE_ENV: 'development' | 'production' | 'test';
       API_KEY: string;
       DATABASE_URL: string;
     }
   }
   ```

#### 2.3 開発サーバーの設定

##### 開発サーバーの基本設定

1. **webpack-dev-serverの設定**
   ```javascript
   // webpack.config.js
   module.exports = {
     // ...その他の設定
     devServer: {
       port: 3000,
       hot: true,
       open: true,
       historyApiFallback: true,
       proxy: {
         '/api': {
           target: 'http://localhost:8080',
           changeOrigin: true
         }
       }
     }
   };
   ```

2. **ts-node-devの設定**
   ```json
   {
     "scripts": {
       "dev": "ts-node-dev --respawn --transpile-only src/index.ts"
     }
   }
   ```

##### ホットリロードの設定

1. **基本設定**
   ```javascript
   // webpack.config.js
   module.exports = {
     devServer: {
       hot: true,
       liveReload: true
     }
   };
   ```

2. **モジュールの対応**
   ```typescript
   if (module.hot) {
     module.hot.accept();
   }
   ```

##### 開発時の便利な機能

1. **ソースマップの生成**
   ```javascript
   // webpack.config.js
   module.exports = {
     devtool: 'source-map'  // 本番環境
     // または
     devtool: 'eval-source-map'  // 開発環境
   };
   ```

2. **エラー表示の改善**
   ```typescript
   // エラーバウンダリの実装例
   process.on('unhandledRejection', (reason, promise) => {
     console.error('Unhandled Rejection at:', promise, 'reason:', reason);
   });
   ```

3. **パフォーマンス測定**
   ```typescript
   // 簡単なパフォーマンス測定
   console.time('操作名');
   // 処理
   console.timeEnd('操作名');
   ```

これで基本的なプロジェクト構造と設定が整いました。次のパートでは、JavaScriptの基礎について学んでいきます。

## Part 2: JavaScript基礎

### 1. 変数とデータ型

#### 1.1 変数宣言の基本

```javascript
// 変数宣言の3つの方法とその特徴
// 1. let: ブロックスコープの変数宣言
// - 再代入可能
// - 同じスコープ内での再宣言は不可
// - 巻き上げ（ホイスティング）されるが、TDZ（Temporal Dead Zone）により初期化前のアクセスはエラー
let count = 1;
count = 2; // OK: 再代入可能

// 2. const: 定数宣言
// - 値の再代入が不可
// - オブジェクトのプロパティは変更可能
// - 配列の要素は変更可能
// - 参照の変更はできないが、参照先の値は変更可能
const PI = 3.14;
// PI = 3.15; // エラー: constは再代入不可

// 3. var: 古い変数宣言方法（非推奨）
// - 関数スコープ
// - 巻き上げ（ホイスティング）される
// - 同じスコープ内での再宣言が可能
// - バグの原因になりやすいため使用を避ける
var name = "old"; // 非推奨: 代わりにletまたはconstを使用
```

#### 1.2 プリミティブ型

```javascript
// JavaScriptの基本データ型（プリミティブ型）

// 1. 数値型（Number）
// - 整数と浮動小数点数を同じ型で扱う
// - IEEE 754倍精度浮動小数点数として実装
// - 特殊な値: Infinity, -Infinity, NaN
const integer = 42;        // 整数
const float = 3.14;        // 浮動小数点数
const billion = 1e9;       // 指数表記
const binary = 0b1010;     // 2進数
const octal = 0o744;       // 8進数
const hex = 0xff;          // 16進数

// 2. 文字列型（String）
// - シングルクォート、ダブルクォート、バッククォートで囲む
// - バッククォートを使用するとテンプレートリテラルとして使える
// - エスケープシーケンスを使用可能
const single = 'シングルクォート';
const double = "ダブルクォート";
const template = `値: ${integer}`; // テンプレートリテラル: 変数の埋め込みが可能
const multiline = `
  複数行の
  文字列も
  書けます
`; // 複数行文字列

// 3. 真偽値（Boolean）
// - 条件分岐で使用
// - falsy値: false, 0, "", null, undefined, NaN
// - それ以外はtruthy値として評価される
const isTrue = true;
const isFalse = false;
const truthyCheck = Boolean("文字列"); // true
const falsyCheck = Boolean("");        // false

// 4. null と undefined
// - nullは値が意図的に空であることを示す
// - undefinedは値が設定されていないことを示す
// - 型としても、値としても存在する
const empty = null;       // 意図的に空を表現
let notDefined;          // 未定義（undefined）
const obj = {};
console.log(obj.prop);   // undefined: 存在しないプロパティにアクセス

// 5. シンボル（Symbol）
// - ES2015で導入された新しいプリミティブ型
// - 必ず一意の値となる
// - オブジェクトのプロパティキーとして使用可能
// - 列挙されない（for...inなどで）
const symbol1 = Symbol('description');
const symbol2 = Symbol('description');
console.log(symbol1 === symbol2); // false: 同じ説明でも異なるシンボル

// シンボルの使用例
const obj = {
  [symbol1]: "シンボルをキーとして使用"
};
```

#### 1.3 参照型

```javascript
// JavaScriptの参照型（オブジェクトと配列）

// 1. オブジェクト（Object）
// - キーと値のペアの集合
// - プロパティの動的な追加・削除が可能
// - メソッドを持つことができる
// - プロトタイプベースの継承をサポート
const user = {
  // プロパティ
  name: "田中",          // 文字列
  age: 25,              // 数値
  isAdmin: false,       // 真偽値
  
  // メソッド（オブジェクトのプロパティとして定義された関数）
  greet() {
    // テンプレートリテラルでthisを使用
    // thisは呼び出し元のオブジェクトを参照
    return `こんにちは、${this.name}です`;
  },
  
  // アロー関数での定義（非推奨: thisの束縛が異なる）
  farewell: () => {
    // アロー関数内のthisは外側のスコープのthisを参照
    console.log("さようなら");
  }
};

// オブジェクトの操作
user.email = "tanaka@example.com";  // プロパティの追加
delete user.age;                    // プロパティの削除
console.log("name" in user);        // プロパティの存在確認
Object.keys(user);                  // プロパティ名の配列を取得
Object.values(user);                // 値の配列を取得
Object.entries(user);               // [キー, 値]のペアの配列を取得

// 2. 配列（Array）
// - 順序付きのコレクション
// - 異なる型の要素を混在させることが可能
// - 長さは動的に変更可能
// - 多くの便利なメソッドを持つ
const numbers = [1, 2, 3];

// 配列の操作メソッド
numbers.push(4);     // 末尾に要素を追加
numbers.pop();       // 末尾の要素を削除して返す
numbers.shift();     // 先頭の要素を削除して返す
numbers.unshift(0);  // 先頭に要素を追加

// 配列の高階関数
// map: 各要素を変換して新しい配列を作成
const doubled = numbers.map(n => n * 2);  // [0, 4, 6]

// filter: 条件に合う要素だけの新しい配列を作成
const evenNumbers = numbers.filter(n => n % 2 === 0);  // [0, 2]

// reduce: 配列の要素を集約して1つの値にする
const sum = numbers.reduce((acc, cur) => acc + cur, 0);  // 6

// forEach: 各要素に対して処理を実行
numbers.forEach(n => console.log(n));  // 各要素を出力

// 配列の検索
const index = numbers.indexOf(2);         // 要素のインデックスを検索
const found = numbers.find(n => n > 2);   // 条件に合う最初の要素を返す
const exists = numbers.some(n => n > 2);  // 条件に合う要素が存在するか
const allPass = numbers.every(n => n > 0); // すべての要素が条件を満たすか
```

### 2. 関数とスコープ

#### 2.1 関数の基本

```javascript
// JavaScriptにおける関数の定義方法と特徴

// 1. 関数宣言（Function Declaration）
// - 巻き上げ（ホイスティング）される：宣言前に呼び出し可能
// - 名前付き関数として定義
// - thisは呼び出し元のコンテキストを参照
function greet(name) {
    // 引数のデフォルト値を設定
    name = name || 'ゲスト';
    return `Hello, ${name}!`;
}

// 2. 関数式（Function Expression）
// - 変数に代入する形で定義
// - 巻き上げされない
// - 無名関数（anonymous function）としても定義可能
const sayHello = function(name) {
    return `Hello, ${name}!`;
};

// 3. アロー関数（Arrow Function）
// - より簡潔な構文
// - 独自のthisを持たない（レキシカルスコープのthisを使用）
// - constructorとして使用不可
// - argumentsオブジェクトを持たない
const multiply = (a, b) => {
    return a * b;
};

// アロー関数の省略記法
// - 単一の式の場合、波括弧とreturnを省略可能
const add = (a, b) => a + b;
// - 引数が1つの場合、括弧を省略可能
const square = x => x * x;
// - 引数がない場合は括弧が必要
const getRandom = () => Math.random();

// 4. 高階関数（Higher-Order Functions）
// - 関数を引数として受け取る関数
// - 関数を返す関数
// - 配列のメソッドでよく使用される
const numbers = [1, 2, 3, 4, 5];

// map: 各要素を変換
numbers.map(num => num * 2);

// filter: 条件に合う要素を抽出
numbers.filter(num => num % 2 === 0);

// reduce: 要素を集約
numbers.reduce((acc, cur) => acc + cur, 0);

// 5. コールバック関数
// - 他の関数に引数として渡される関数
// - 非同期処理でよく使用される
function fetchData(callback) {
    setTimeout(() => {
        const data = { id: 1, name: "データ" };
        callback(data);
    }, 1000);
}

fetchData((data) => {
    console.log(data); // 1秒後にデータが表示される
});

// 6. メソッドとしての関数
// - オブジェクトのプロパティとして定義された関数
const calculator = {
    // 通常のメソッド定義
    add(a, b) {
        return a + b;
    },
    // アロー関数での定義（thisの挙動が異なる）
    multiply: (a, b) => a * b
};
```

#### 2.2 スコープとクロージャ

```javascript
// JavaScriptのスコープとクロージャの理解

// 1. スコープの種類
// グローバルスコープ
const globalVar = "グローバル変数";

// 関数スコープ
function functionScope() {
    // この変数は関数の外からアクセス不可
    const functionVar = "関数スコープの変数";
    console.log(globalVar); // グローバル変数にアクセス可能
}

// ブロックスコープ
{
    // letとconstはブロックスコープを作る
    let blockVar = "ブロックスコープの変数";
    const constVar = "定数";
    // varはブロックスコープを無視する（非推奨）
    var ignoresBlock = "関数スコープの変数";
}

// 2. レキシカルスコープ（静的スコープ）
// - 関数は定義された場所のスコープを参照する
function outer() {
    const outerVar = "外部関数の変数";
    
    function inner() {
        // 外部関数の変数にアクセス可能
        console.log(outerVar);
    }
    
    return inner;
}

// 3. クロージャ（Closure）
// - 関数が自身の外部スコープの変数を参照する仕組み
// - データのカプセル化やプライベート変数の実現に使用
function createCounter() {
    // この変数はクロージャによって保持される
    let count = 0;
    
    return {
        // count変数へのアクセスを制限しつつ、
        // 操作するためのメソッドを提供
        increment() {
            return ++count;
        },
        decrement() {
            return --count;
        },
        getCount() {
            return count;
        }
    };
}

const counter = createCounter();
counter.increment(); // 1
counter.increment(); // 2
// count変数に直接アクセスはできない

// 4. thisの振る舞い
// - thisは呼び出し元のコンテキストを参照
// - 呼び出し方法によって値が変わる

// オブジェクトのメソッドとして
const user = {
    name: "ユーザー",
    greet() {
        // thisはuserオブジェクトを参照
        return `こんにちは、${this.name}さん`;
    }
};

// アロー関数内のthis
const arrowThis = {
    name: "アロー",
    // アロー関数は外側のスコープのthisを保持
    greet: () => {
        // このthisはwindowまたはglobalを参照
        console.log(this.name); // undefined
    }
};

// bindによるthisの固定
function normalFunction() {
    return this.value;
}
const boundFunction = normalFunction.bind({ value: 42 });
```

#### 2.3 非同期処理

```javascript
// JavaScriptの非同期処理パターン

// 1. コールバックパターン
// - 最も基本的な非同期処理
// - コールバック地獄（Callback Hell）の問題がある
function fetchDataCallback(callback) {
    setTimeout(() => {
        const data = { id: 1 };
        callback(null, data); // エラーファースト・コールバック
    }, 1000);
}

fetchDataCallback((error, data) => {
    if (error) {
        console.error('エラー:', error);
        return;
    }
    console.log('データ:', data);
});

// 2. Promise
// - コールバック地獄を解消
// - エラーハンドリングが容易
// - チェーン可能な非同期処理
const fetchDataPromise = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true;
            if (success) {
                resolve({ id: 1, name: "データ" });
            } else {
                reject(new Error("データの取得に失敗"));
            }
        }, 1000);
    });
};

// Promiseの使用
fetchDataPromise()
    .then(data => {
        console.log('成功:', data);
        return processData(data); // 別のPromiseを返す
    })
    .catch(error => {
        console.error('エラー:', error);
    })
    .finally(() => {
        console.log('完了処理');
    });

// 3. async/await
// - Promiseをより同期的に書ける
// - try/catchでエラーハンドリング
// - 非同期処理の可読性が向上
async function fetchAndProcessData() {
    try {
        // awaitで非同期処理の完了を待つ
        const data = await fetchDataPromise();
        console.log('データ:', data);
        
        // 複数の非同期処理を順次実行
        const processed = await processData(data);
        const saved = await saveData(processed);
        
        return saved;
    } catch (error) {
        console.error('エラー:', error);
        throw error; // エラーを再スロー
    }
}

// 4. 並列処理
// Promise.all: すべての非同期処理の完了を待つ
const promises = [
    fetchDataPromise(),
    fetchOtherData(),
    fetchMoreData()
];

Promise.all(promises)
    .then(results => {
        console.log('すべての結果:', results);
    })
    .catch(error => {
        console.error('いずれかがエラー:', error);
    });

// Promise.race: 最初に完了した処理の結果を返す
Promise.race(promises)
    .then(firstResult => {
        console.log('最初の結果:', firstResult);
    });

// 5. async/awaitでの並列処理
async function parallelFetch() {
    try {
        // Promise.allとasync/awaitの組み合わせ
        const results = await Promise.all([
            fetchDataPromise(),
            fetchOtherData(),
            fetchMoreData()
        ]);
        
        console.log('すべての結果:', results);
    } catch (error) {
        console.error('エラー:', error);
    }
}
```

### 3. オブジェクト指向の基礎

#### 3.1 オブジェクトの基本

```javascript
// JavaScriptのオブジェクト指向プログラミング

// 1. オブジェクトリテラル
// - 最も基本的なオブジェクトの作成方法
// - キーと値のペアの集合
const user = {
    // プロパティ
    name: "田中",
    age: 25,
    email: "tanaka@example.com",

    // メソッド
    greet() {
        return `こんにちは、${this.name}です`;
    },

    // getter/setter
    get profile() {
        return `${this.name} (${this.age}歳)`;
    },
    
    set age(value) {
        if (value < 0) throw new Error("年齢は0以上である必要があります");
        this._age = value;
    }
};

// 2. クラス構文（ES2015以降）
// - オブジェクト指向プログラミングの基本構造
// - プロトタイプベースの継承をクラスベースの構文で表現
class Person {
    // privateフィールド（ES2022以降）
    #privateField;

    // staticプロパティ
    static species = "Human";

    // コンストラクタ
    constructor(name, age) {
        this.name = name;
        this.age = age;
        this.#privateField = "非公開";
    }

    // インスタンスメソッド
    greet() {
        return `こんにちは、${this.name}です`;
    }

    // staticメソッド
    static createAnonymous() {
        return new Person("名無し", 0);
    }

    // getter
    get profile() {
        return `${this.name} (${this.age}歳)`;
    }

    // privateメソッド（ES2022以降）
    #privateMethod() {
        return "非公開メソッド";
    }
}

// 3. 継承
// - 既存のクラスを拡張して新しいクラスを作成
// - スーパークラスのメソッドやプロパティを継承
class Employee extends Person {
    // 独自のコンストラクタ
    constructor(name, age, employeeId) {
        // スーパークラスのコンストラクタを呼び出し
        super(name, age);
        this.employeeId = employeeId;
    }

    // メソッドのオーバーライド
    greet() {
        // スーパークラスのメソッドを呼び出し
        const baseGreeting = super.greet();
        return `${baseGreeting} 社員番号は${this.employeeId}です`;
    }

    // 独自のメソッド
    work() {
        return `${this.name}が働いています`;
    }
}

// 4. インスタンス化と使用例
const person = new Person("山田", 30);
console.log(person.greet());        // "こんにちは、山田です"
console.log(Person.species);        // "Human"
console.log(person.profile);        // "山田 (30歳)"

const employee = new Employee("鈴木", 25, "E001");
console.log(employee.greet());      // "こんにちは、鈴木です 社員番号はE001です"
console.log(employee instanceof Person);    // true
console.log(employee instanceof Employee);  // true

// 5. プロトタイプと継承チェーン
// - JavaScriptの継承はプロトタイプベース
// - 各オブジェクトは__proto__を通じて継承チェーンを形成
console.log(employee.__proto__ === Employee.prototype);     // true
console.log(Employee.prototype.__proto__ === Person.prototype); // true

// 6. Mixinパターン
// - 複数のオブジェクトの機能を1つのクラスに組み込む
const speakableMixin = {
    speak() {
        return `${this.name}が話しています`;
    }
};

// MixinをEmployeeクラスに適用
Object.assign(Employee.prototype, speakableMixin);
```

#### 3.2 モジュール化

```javascript
// JavaScriptのモジュールシステム

// 1. ESモジュール（推奨）
// user.js
// - エクスポートの方法
// 名前付きエクスポート
export const USER_ROLES = {
    ADMIN: 'ADMIN',
    USER: 'USER'
};

export class User {
    constructor(name, role) {
        this.name = name;
        this.role = role;
    }

    hasAccess(feature) {
        return this.role === USER_ROLES.ADMIN;
    }
}

// デフォルトエクスポート（1ファイルに1つ）
export default class AdminUser extends User {
    constructor(name) {
        super(name, USER_ROLES.ADMIN);
    }
}

// utils.js
// - ユーティリティ関数のエクスポート
export const formatDate = (date) => {
    return new Date(date).toLocaleDateString();
};

export const generateId = () => {
    return Math.random().toString(36).substr(2, 9);
};

// main.js
// - インポートの方法
// 名前付きインポート
import { User, USER_ROLES } from './user.js';
// デフォルトインポート
import AdminUser from './user.js';
// 名前付きインポートの別名指定
import { formatDate as format } from './utils.js';
// モジュール全体をオブジェクトとしてインポート
import * as Utils from './utils.js';

// 2. 動的インポート
// - 必要なタイミングでモジュールを読み込む
async function loadModule() {
    try {
        const module = await import('./heavy-module.js');
        module.doSomething();
    } catch (error) {
        console.error('モジュールの読み込みに失敗:', error);
    }
}

// 3. モジュールの集約（バレル）
// index.js
// - 複数のモジュールをまとめてエクスポート
export { User, AdminUser, USER_ROLES } from './user.js';
export { formatDate, generateId } from './utils.js';

// 4. 循環依存の回避
// - 循環依存は避けるべき
// - 必要な場合は依存関係を整理するか、イベントシステムを使用

// 5. モジュールの初期化
// - モジュールは最初のインポート時に1度だけ評価される
// - 初期化コードは即時実行関数で囲むことが推奨
const initialize = (() => {
    console.log('モジュールを初期化中...');
    // 初期化処理
})();

// 6. モジュールパターン（古い方式）
// - CommonJS形式（Node.js）
const moduleA = require('./moduleA');
module.exports = {
    // エクスポートするものを指定
};

// 7. プライベート変数とクロージャ
const createModule = (() => {
    // プライベート変数
    let privateData = [];

    return {
        // パブリックAPI
        addData(item) {
            privateData.push(item);
        },
        getData() {
            return [...privateData];
        }
    };
})();
```

これらの基本的なオブジェクト指向の概念とモジュール化の手法を理解することで、より構造化された保守性の高いコードを書くことができます。

## Part 3: TypeScript基礎

### 1. TypeScriptの基本

#### 1.1 型アノテーション

```typescript
// TypeScriptの基本的な型システム

// 1. プリミティブ型
// - JavaScriptの基本型に型アノテーションを追加
let name: string = "太郎";          // 文字列型
let age: number = 20;               // 数値型
let isStudent: boolean = true;      // 真偽値型
let nullableValue: null = null;     // null型
let undefinedValue: undefined;      // undefined型
let symbolValue: symbol = Symbol(); // シンボル型

// 2. 配列型
// - 型名の後ろに[]をつける方法
let numbers: number[] = [1, 2, 3];
// - ジェネリック記法
let strings: Array<string> = ["a", "b", "c"];
// - 読み取り専用配列
const readOnlyArray: ReadonlyArray<number> = [1, 2, 3];
// または
const readOnlyArray2: readonly number[] = [1, 2, 3];

// 3. タプル型
// - 固定長の配列で、各要素の型が決まっている
let tuple: [string, number] = ["abc", 123];
// - オプショナルな要素
let optionalTuple: [string, number?] = ["abc"];
// - 可変長タプル
let restTuple: [string, ...number[]] = ["abc", 1, 2, 3];

// 4. ユニオン型とインターセクション型
// - ユニオン型（複数の型のいずれか）
let id: string | number;
id = "abc123";
id = 123;

// - インターセクション型（複数の型のすべて）
type User = {
    name: string;
    age: number;
};

type Employee = {
    employeeId: string;
    department: string;
};

type EmployeeUser = User & Employee;

// 5. リテラル型
// - 特定の値のみを許容する型
let status: "active" | "inactive" | "pending";
let level: 1 | 2 | 3 = 1;

// 6. 型エイリアス
// - 型に名前をつける
type Point = {
    x: number;
    y: number;
};

type ID = string | number;
type UserRole = "admin" | "user" | "guest";

// 7. any型とunknown型
// - any: 型チェックを無効化（非推奨）
let anyValue: any = 4;
anyValue = "string";
anyValue = { key: "value" };

// - unknown: 型安全なany
let unknownValue: unknown = 4;
if (typeof unknownValue === "number") {
    // 型ガードによって数値として扱える
    console.log(unknownValue * 2);
}

// 8. void型とnever型
// - void: 戻り値がない関数の戻り値型
function logMessage(message: string): void {
    console.log(message);
}

// - never: 決して戻り値を返さない関数の戻り値型
function throwError(message: string): never {
    throw new Error(message);
}

// 9. 型推論
// - 明示的な型アノテーションが不要な場合も多い
let inferredString = "文字列"; // string型と推論
let inferredNumber = 42;       // number型と推論
let inferredArray = [1, 2, 3]; // number[]型と推論

// 10. 型アサーション
// - 型を明示的に指定する
let someValue: unknown = "this is a string";
let strLength: number = (someValue as string).length;
// または
let strLength2: number = (<string>someValue).length; // JSXでは使用不可

// 11. const アサーション
// - オブジェクトのプロパティを読み取り専用にする
const config = {
    apiUrl: "https://api.example.com",
    timeout: 5000
} as const;

// 12. 非nullアサーション
// - null/undefinedではないことを明示する
function getNullableValue(): string | null {
    return "value";
}
const value = getNullableValue()!; // string型として扱える

// 13. 型ガード
// - typeof型ガード
function processValue(value: string | number) {
    if (typeof value === "string") {
        // この中ではstring型として扱える
        return value.toUpperCase();
    }
    // この中ではnumber型として扱える
    return value.toFixed(2);
}

// - instanceof型ガード
class Animal {
    name: string;
    constructor(name: string) {
        this.name = name;
    }
}

class Dog extends Animal {
    bark() {
        return "Woof!";
    }
}

function processAnimal(animal: Animal) {
    if (animal instanceof Dog) {
        // この中ではDog型として扱える
        animal.bark();
    }
}
```

#### 1.2 インターフェース

```typescript
// TypeScriptのインターフェース

// 1. 基本的なインターフェース
// - オブジェクトの形状を定義
interface User {
    // 必須プロパティ
    name: string;
    age: number;
    
    // オプショナルプロパティ
    email?: string;
    
    // 読み取り専用プロパティ
    readonly id: number;
    
    // メソッド定義
    greet(): string;
    
    // オプショナルメソッド
    farewell?(): string;
}

// インターフェースの実装例
class Student implements User {
    readonly id: number;
    
    constructor(public name: string, public age: number) {
        this.id = Math.random();
    }
    
    greet() {
        return `こんにちは、${this.name}です`;
    }
}

// 2. インターフェースの拡張
// - 既存のインターフェースを拡張
interface Employee extends User {
    employeeId: string;
    department: string;
    
    // 既存のメソッドをオーバーライド可能
    greet(): string;
}

// 3. インデックスシグネチャ
// - 動的なプロパティ名を持つオブジェクトを定義
interface StringDictionary {
    // 文字列キーに対して文字列値を持つ
    [key: string]: string;
}

interface NumberDictionary {
    // 数値キーに対して任意の型の値を持つ
    [index: number]: any;
}

// 4. 関数型インターフェース
// - 関数の型を定義
interface SearchFunc {
    (source: string, subString: string): boolean;
}

const searchString: SearchFunc = (src, sub) => src.includes(sub);

// 5. ハイブリッドインターフェース
// - オブジェクトと関数の両方の特徴を持つ
interface Counter {
    // 関数として呼び出し可能
    (start: number): string;
    // プロパティも持てる
    interval: number;
    // メソッドも定義可能
    reset(): void;
}

// 6. インターフェースのマージ
// - 同名のインターフェースは自動的にマージされる
interface Box {
    height: number;
    width: number;
}

interface Box {
    scale: number;
}

// 7. Utility Types with Interfaces
// - Partialで全てのプロパティをオプショナルに
type PartialUser = Partial<User>;

// - Requiredで全てのプロパティを必須に
type RequiredUser = Required<User>;

// - Pickで特定のプロパティのみを選択
type UserBasicInfo = Pick<User, "name" | "age">;

// - Omitで特定のプロパティを除外
type UserWithoutId = Omit<User, "id">;

// 8. ジェネリックインターフェース
// - 型パラメータを持つインターフェース
interface Repository<T> {
    get(id: string): T;
    save(item: T): void;
    delete(id: string): boolean;
}

// 実装例
class UserRepository implements Repository<User> {
    get(id: string): User {
        // 実装
        return {} as User;
    }
    
    save(user: User): void {
        // 実装
    }
    
    delete(id: string): boolean {
        // 実装
        return true;
    }
}
```

[続く...]

### 2. 高度な型システム

#### 2.1 ジェネリクス

```typescript
// TypeScriptのジェネリック型システム

// 1. ジェネリック関数
// - 型パラメータを使用して再利用可能な関数を定義
// - 型の安全性を保ちながら柔軟な実装が可能
function getFirst<T>(array: T[]): T {
    return array[0];
}

// 使用例
const firstNumber = getFirst([1, 2, 3]);       // number型
const firstString = getFirst(["a", "b"]);      // string型
const firstObj = getFirst([{id: 1}, {id: 2}]); // {id: number}型

// 複数の型パラメータ
function pair<T, U>(first: T, second: U): [T, U] {
    return [first, second];
}

// 2. ジェネリッククラス
// - クラス全体で型パラメータを使用可能
class Container<T> {
    private value: T;

    constructor(value: T) {
        this.value = value;
    }

    getValue(): T {
        return this.value;
    }

    setValue(value: T): void {
        this.value = value;
    }
}

// 使用例
const numberContainer = new Container<number>(123);
const stringContainer = new Container<string>("hello");

// 3. 制約付きジェネリクス
// - extends キーワードで型パラメータに制約を追加
interface Lengthwise {
    length: number;
}

function logLength<T extends Lengthwise>(arg: T): number {
    console.log(arg.length);
    return arg.length;
}

// OK: string型はlengthプロパティを持つ
logLength("hello");
// OK: 配列はlengthプロパティを持つ
logLength([1, 2, 3]);
// エラー: number型はlengthプロパティを持たない
// logLength(123);

// 4. ジェネリックインターフェース
// - インターフェースで型パラメータを使用
interface Response<T> {
    data: T;
    status: number;
    message: string;
}

// 使用例
interface User {
    id: number;
    name: string;
}

const userResponse: Response<User> = {
    data: { id: 1, name: "田中" },
    status: 200,
    message: "Success"
};

// 5. ジェネリック型エイリアス
// - 型エイリアスで型パラメータを使用
type Nullable<T> = T | null;
type ArrayOrSingle<T> = T | T[];

// 使用例
const nullableString: Nullable<string> = null;
const numberArray: ArrayOrSingle<number> = [1, 2, 3];

// 6. デフォルトの型パラメータ
// - 型パラメータにデフォルト値を設定
interface DefaultGeneric<T = string> {
    value: T;
}

// デフォルトはstring型
const defaultString: DefaultGeneric = { value: "hello" };
// 明示的にnumber型を指定
const explicitNumber: DefaultGeneric<number> = { value: 123 };

// 7. 条件付き型（Conditional Types）
// - 型の条件分岐
type IsArray<T> = T extends any[] ? true : false;

// 使用例
type CheckArray1 = IsArray<string[]>;  // true
type CheckArray2 = IsArray<string>;    // false

// 8. マップ型（Mapped Types）
// - 既存の型から新しい型を生成
type Optional<T> = {
    [P in keyof T]?: T[P];
};

type ReadOnly<T> = {
    readonly [P in keyof T]: T[P];
};

// 使用例
interface Point {
    x: number;
    y: number;
}

type OptionalPoint = Optional<Point>;  // すべてのプロパティがオプショナル
type ReadOnlyPoint = ReadOnly<Point>;  // すべてのプロパティが読み取り専用
```

#### 2.2 型ガード

```typescript
// TypeScriptの型ガード機能

// 1. typeof型ガード
// - プリミティブ型の判別に使用
function processValue(value: string | number | boolean) {
    // 型ガードによって各ブロック内で適切な型として扱われる
    if (typeof value === "string") {
        // このブロックではvalueはstring型
        return value.toUpperCase();
    } else if (typeof value === "number") {
        // このブロックではvalueはnumber型
        return value.toFixed(2);
    } else {
        // このブロックではvalueはboolean型
        return value.toString();
    }
}

// 2. instanceof型ガード
// - クラスのインスタンスの判別に使用
class Animal {
    constructor(public name: string) {}
    move() { console.log("Moving..."); }
}

class Bird extends Animal {
    fly() { console.log("Flying..."); }
}

class Fish extends Animal {
    swim() { console.log("Swimming..."); }
}

function moveAnimal(animal: Animal) {
    if (animal instanceof Bird) {
        // このブロックではanimalはBird型
        animal.fly();
    } else if (animal instanceof Fish) {
        // このブロックではanimalはFish型
        animal.swim();
    } else {
        // このブロックではanimalはAnimal型
        animal.move();
    }
}

// 3. in演算子による型ガード
// - プロパティの存在確認による型の判別
interface Car {
    type: "car";
    wheels: number;
}

interface Airplane {
    type: "airplane";
    wings: number;
}

type Vehicle = Car | Airplane;

function checkVehicle(vehicle: Vehicle) {
    if ("wheels" in vehicle) {
        // このブロックではvehicleはCar型
        console.log(`車輪の数: ${vehicle.wheels}`);
    } else {
        // このブロックではvehicleはAirplane型
        console.log(`翼の数: ${vehicle.wings}`);
    }
}

// 4. リテラル型による型ガード
// - 判別可能なユニオン型（Discriminated Unions）
interface Square {
    kind: "square";
    size: number;
}

interface Rectangle {
    kind: "rectangle";
    width: number;
    height: number;
}

interface Circle {
    kind: "circle";
    radius: number;
}

type Shape = Square | Rectangle | Circle;

function calculateArea(shape: Shape): number {
    switch (shape.kind) {
        case "square":
            // このブロックではshapeはSquare型
            return shape.size * shape.size;
        case "rectangle":
            // このブロックではshapeはRectangle型
            return shape.width * shape.height;
        case "circle":
            // このブロックではshapeはCircle型
            return Math.PI * shape.radius ** 2;
    }
}

// 5. カスタム型ガード関数
// - 独自の型判別ロジックを関数として実装
function isString(value: unknown): value is string {
    return typeof value === "string";
}

function isNumber(value: unknown): value is number {
    return typeof value === "number";
}

// 使用例
function processUnknown(value: unknown) {
    if (isString(value)) {
        // このブロックではvalueはstring型
        console.log(value.toUpperCase());
    } else if (isNumber(value)) {
        // このブロックではvalueはnumber型
        console.log(value.toFixed(2));
    }
}

// 6. 型ガードの結合
// - 複数の型ガードを組み合わせる
function isNonNullObject(value: unknown): value is object {
    return value !== null && typeof value === "object";
}

function hasNameProperty(value: object): value is { name: string } {
    return "name" in value;
}

// 使用例
function processObject(value: unknown) {
    if (isNonNullObject(value) && hasNameProperty(value)) {
        // このブロックではvalueは{ name: string }型
        console.log(value.name);
    }
}
```

[続く...]

#### 2.3 デコレータ

```typescript
// TypeScriptのデコレータ
// - 実験的機能のため、tsconfig.jsonで"experimentalDecorators": trueの設定が必要
// - クラス、メソッド、プロパティ、パラメータの動作を拡張・変更できる

// 1. クラスデコレータ
// - クラス定義を変更または拡張する
// - コンストラクタ関数を受け取り、新しいコンストラクタ関数を返すことができる
function Logger(logString: string) {
    return function(constructor: Function) {
        console.log(logString);
        console.log(constructor);
    }
}

function WithTemplate(template: string, hookId: string) {
    return function<T extends { new(...args: any[]): {name: string} }>(originalConstructor: T) {
        // 新しいコンストラクタ関数を返す
        return class extends originalConstructor {
            constructor(..._: any[]) {
                super();
                const hookEl = document.getElementById(hookId);
                if (hookEl) {
                    hookEl.innerHTML = template;
                    hookEl.querySelector('h1')!.textContent = this.name;
                }
            }
        }
    }
}

// 複数のデコレータを適用（下から上に実行される）
@Logger('ログ出力中 - Person')
@WithTemplate('<h1>Personオブジェクト</h1>', 'app')
class Person {
    name = "Max";

    constructor() {
        console.log('Personオブジェクトを作成中...');
    }
}

// 2. メソッドデコレータ
// - メソッドの定義を変更または監視する
// - PropertyDescriptorを使用してメソッドの振る舞いを変更できる
function Log(target: any, propertyName: string, descriptor: PropertyDescriptor) {
    // オリジナルのメソッドを保存
    const originalMethod = descriptor.value;

    // メソッドをラップした新しい実装
    descriptor.value = function(...args: any[]) {
        console.log(`メソッド ${propertyName} を実行:`);
        console.log(`引数: ${args}`);
        
        // オリジナルのメソッドを実行
        const result = originalMethod.apply(this, args);
        
        console.log(`結果: ${result}`);
        return result;
    }
}

// 3. プロパティデコレータ
// - プロパティの定義を変更または監視する
function ValidateProperty(target: any, propertyName: string) {
    // プロパティの値を保存するための隠しプロパティ名
    const privateField = `_${propertyName}`;

    // プロパティディスクリプタを定義
    Object.defineProperty(target, propertyName, {
        get() {
            return this[privateField];
        },
        set(value: string) {
            if (!value) {
                throw new Error(`${propertyName}は空にできません`);
            }
            this[privateField] = value;
        }
    });
}

// 4. パラメータデコレータ
// - メソッドパラメータの定義を変更または監視する
function Required(target: any, methodName: string, parameterIndex: number) {
    // パラメータのメタデータを保存
    const existingRequiredParameters: number[] = Reflect.getOwnMetadata('required', target, methodName) || [];
    existingRequiredParameters.push(parameterIndex);
    Reflect.defineMetadata('required', existingRequiredParameters, target, methodName);
}

// 5. アクセサデコレータ
// - getterやsetterの定義を変更または監視する
function Enumerable(value: boolean) {
    return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
        descriptor.enumerable = value;
    };
}

// デコレータの使用例
class Product {
    @ValidateProperty
    title: string;

    constructor(t: string) {
        this.title = t;
    }

    @Log
    getPriceWithTax(@Required tax: number) {
        return this.price * (1 + tax);
    }

    @Enumerable(false)
    private price: number = 0;

    @Enumerable(true)
    get normalizedPrice() {
        return `￥${this.price.toFixed(2)}`;
    }
}

// 6. デコレータファクトリ
// - デコレータをカスタマイズするためのファクトリ関数
function MinLength(length: number) {
    return function (target: any, propertyName: string) {
        let value: string;
        
        const descriptor: PropertyDescriptor = {
            get() {
                return value;
            },
            set(newValue: string) {
                if (newValue.length < length) {
                    throw new Error(`${propertyName}は${length}文字以上である必要があります`);
                }
                value = newValue;
            }
        };
        
        Object.defineProperty(target, propertyName, descriptor);
    }
}

// 7. デコレータの合成
// - 複数のデコレータを組み合わせる
function First() {
    console.log("First(): デコレータファクトリを評価");
    return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
        console.log("First(): デコレータを実行");
    };
}

function Second() {
    console.log("Second(): デコレータファクトリを評価");
    return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
        console.log("Second(): デコレータを実行");
    };
}

class Example {
    @First()
    @Second()
    method() {}
}

// 8. メタデータデコレータ
// - reflect-metadataライブラリを使用したメタデータの操作
import 'reflect-metadata';

function Type(type: any) {
    return Reflect.metadata('design:type', type);
}

function ParamTypes(...types: any[]) {
    return Reflect.metadata('design:paramtypes', types);
}

function ReturnType(type: any) {
    return Reflect.metadata('design:returntype', type);
}

class Example2 {
    @Type(String)
    name: string;

    @ParamTypes(String, Number)
    @ReturnType(Boolean)
    method(text: string, num: number): boolean {
        return true;
    }
}

// 9. 実践的なデコレータの使用例
// - ルーティングデコレータ
function Route(path: string) {
    return function (target: any) {
        Reflect.defineMetadata('path', path, target);
    }
}

// - バリデーションデコレータ
function Validate() {
    return function (target: any, propertyName: string, descriptor: PropertyDescriptor) {
        const originalMethod = descriptor.value;

        descriptor.value = function(...args: any[]) {
            // バリデーションロジック
            const requiredParameters: number[] = Reflect.getOwnMetadata('required', target, propertyName) || [];
            
            for (const parameterIndex of requiredParameters) {
                if (args[parameterIndex] === undefined || args[parameterIndex] === null) {
                    throw new Error(`パラメータ ${parameterIndex} は必須です`);
                }
            }

            return originalMethod.apply(this, args);
        }
    }
}
```

これらのデコレータパターンを理解することで、クラスやメソッドの振る舞いを柔軟にカスタマイズできます。次のパートでは、実践的な開発手法について学んでいきます。

## Part 4: 実践的な開発手法

### 1. 効率的な開発フロー

#### 1.1 バージョン管理

```typescript
// Gitを使用した効果的なバージョン管理の例

// 1. 基本的なGitコマンド
// - リポジトリの初期化と基本操作
git init                    // 新規リポジトリの作成
git clone <url>            // リポジトリのクローン
git status                 // 変更状態の確認
git add .                  // 全ての変更をステージング
git commit -m "メッセージ"   // 変更のコミット
git push origin main      // リモートへの変更の反映

// 2. ブランチ管理
// - 効果的なブランチ戦略
// feature/: 新機能開発用
git checkout -b feature/user-auth    // 認証機能用のブランチを作成
git branch                          // ブランチ一覧の表示
git merge feature/user-auth         // 機能をメインブランチにマージ

// bugfix/: バグ修正用
git checkout -b bugfix/login-error  // バグ修正用のブランチを作成

// release/: リリース準備用
git checkout -b release/v1.0.0      // リリース用のブランチを作成

// 3. コミットメッセージの規約
// 形式: <type>: <subject>
// 
// type:
//   feat     : 新機能
//   fix      : バグ修正
//   docs     : ドキュメントのみの変更
//   style    : コードの意味に影響を与えない変更（空白、フォーマット等）
//   refactor : リファクタリング
//   test     : テストコードの追加・修正
//   chore    : ビルドプロセスやツールの変更

// 良いコミットメッセージの例
git commit -m "feat: ユーザー認証機能の実装"
git commit -m "fix: ログインフォームのバリデーションエラーを修正"
git commit -m "docs: APIドキュメントの更新"

// 4. コンフリクト解決
// マージコンフリクトが発生した場合の対処
git status                  // コンフリクトファイルの確認
// ファイルを編集してコンフリクトを解決
git add <resolved-file>     // 解決したファイルをステージング
git commit -m "Merge: コンフリクトの解決"

// 5. 変更の取り消し
git reset --soft HEAD^     // 直前のコミットを取り消し（変更は保持）
git reset --hard HEAD^     // 直前のコミットを完全に取り消し
git revert <commit-hash>   // 特定のコミットを打ち消す新しいコミットを作成

// 6. スタッシュの活用
git stash                  // 作業中の変更を一時保存
git stash list            // スタッシュの一覧表示
git stash pop             // 最新のスタッシュを復元
git stash drop            // 最新のスタッシュを削除
```

#### 1.2 デバッグ手法

```typescript
// TypeScript/JavaScriptのデバッグテクニック

// 1. コンソールデバッグ
// - 基本的なデバッグ出力
console.log('デバッグ情報:', value);              // 基本的な出力
console.info('情報メッセージ');                   // 情報レベルの出力
console.warn('警告メッセージ');                   // 警告レベルの出力
console.error('エラーメッセージ');                // エラーレベルの出力

// - 高度なコンソール機能
console.table([                                  // テーブル形式での出力
    { id: 1, name: '田中' },
    { id: 2, name: '鈴木' }
]);

console.group('グループ名');                      // ログのグループ化
console.log('グループ内のログ1');
console.log('グループ内のログ2');
console.groupEnd();

// - パフォーマンス計測
console.time('処理時間');                        // 時間計測開始
// ... 処理 ...
console.timeEnd('処理時間');                     // 時間計測終了

// 2. デバッガーの活用
// - ソースコード内でブレークポイントを設定
function debuggableFunction() {
    let x = 1;
    debugger;                                   // ブレークポイント
    x++;
    return x;
}

// 3. エラーハンドリング
// - try-catch による例外処理
try {
    // エラーが発生する可能性のある処理
    throw new Error('カスタムエラー');
} catch (error) {
    console.error('エラーが発生:', error);
    // エラーログの送信など
} finally {
    // 必ず実行される処理
}

// - カスタムエラークラス
class ValidationError extends Error {
    constructor(message: string) {
        super(message);
        this.name = 'ValidationError';
    }
}

// - エラーバウンダリ
process.on('unhandledRejection', (reason, promise) => {
    console.error('未処理のPromise拒否:', reason);
});

// 4. ロギング
// - 構造化ログ
interface LogEntry {
    level: 'info' | 'warn' | 'error';
    message: string;
    timestamp: string;
    data?: any;
}

function log(entry: LogEntry) {
    const logLine = `[${entry.timestamp}] ${entry.level}: ${entry.message}`;
    console.log(logLine, entry.data || '');
}

// 5. ソースマップの活用
// webpack.config.js
module.exports = {
    devtool: 'source-map',  // 開発環境用
    // または
    devtool: 'eval-source-map'  // より詳細なデバッグ情報
};

// 6. ブラウザ開発者ツール
// - ネットワークタブの活用
fetch('/api/data')
    .then(response => response.json())
    .then(data => console.log('受信データ:', data))
    .catch(error => console.error('APIエラー:', error));

// - パフォーマンスプロファイリング
performance.mark('開始');
// ... 処理 ...
performance.mark('終了');
performance.measure('処理時間', '開始', '終了');

// 7. 単体テストでのデバッグ
// Jest使用例
describe('デバッグ対象の関数', () => {
    it('期待される動作をすること', () => {
        const result = debuggableFunction();
        expect(result).toBe(2);
    });
});
```

[続く...]

### 2. テストと品質管理

#### 2.1 ユニットテスト

```typescript
// TypeScript/JavaScriptのテスト実装

// 1. Jestの基本設定
// jest.config.js
module.exports = {
    preset: 'ts-jest',
    testEnvironment: 'node',
    roots: ['<rootDir>/src'],
    testMatch: ['**/*.test.ts'],
    collectCoverage: true,
    coverageDirectory: 'coverage',
    coverageThreshold: {
        global: {
            branches: 80,
            functions: 80,
            lines: 80,
            statements: 80
        }
    }
};

// 2. 基本的なテストの書き方
// calculator.ts
export class Calculator {
    add(a: number, b: number): number {
        return a + b;
    }

    subtract(a: number, b: number): number {
        return a - b;
    }

    multiply(a: number, b: number): number {
        return a * b;
    }

    divide(a: number, b: number): number {
        if (b === 0) throw new Error('0で除算できません');
        return a / b;
    }
}

// calculator.test.ts
import { Calculator } from './calculator';

describe('Calculator', () => {
    let calculator: Calculator;

    // 各テストの前に実行
    beforeEach(() => {
        calculator = new Calculator();
    });

    // テストケース
    test('2つの数値を加算できる', () => {
        expect(calculator.add(2, 3)).toBe(5);
    });

    test('2つの数値を減算できる', () => {
        expect(calculator.subtract(5, 3)).toBe(2);
    });

    test('2つの数値を乗算できる', () => {
        expect(calculator.multiply(2, 3)).toBe(6);
    });

    test('2つの数値を除算できる', () => {
        expect(calculator.divide(6, 2)).toBe(3);
    });

    test('0での除算は例外をスローする', () => {
        expect(() => calculator.divide(6, 0)).toThrow('0で除算できません');
    });
});

// 3. モック（Mock）とスパイ（Spy）
// userService.ts
export class UserService {
    async fetchUser(id: string): Promise<any> {
        const response = await fetch(`/api/users/${id}`);
        return response.json();
    }
}

// userService.test.ts
jest.mock('./userService');

describe('UserService', () => {
    let userService: jest.Mocked<UserService>;

    beforeEach(() => {
        userService = new UserService() as jest.Mocked<UserService>;
    });

    test('ユーザー情報を取得できる', async () => {
        const mockUser = { id: '1', name: '田中' };
        userService.fetchUser.mockResolvedValue(mockUser);

        const result = await userService.fetchUser('1');
        expect(result).toEqual(mockUser);
        expect(userService.fetchUser).toHaveBeenCalledWith('1');
    });
});

// 4. 非同期テスト
// asyncFunction.test.ts
describe('非同期関数のテスト', () => {
    // Promise を使用したテスト
    test('Promise のテスト', () => {
        return fetchData().then(data => {
            expect(data).toBe('データ');
        });
    });

    // async/await を使用したテスト
    test('async/await のテスト', async () => {
        const data = await fetchData();
        expect(data).toBe('データ');
    });

    // エラーハンドリングのテスト
    test('エラーのテスト', async () => {
        await expect(fetchDataWithError()).rejects.toThrow('エラー');
    });
});

// 5. カバレッジレポート
// package.json
{
    "scripts": {
        "test": "jest",
        "test:coverage": "jest --coverage",
        "test:watch": "jest --watch"
    }
}

// 6. スナップショットテスト
// component.test.tsx
import { render } from '@testing-library/react';

test('コンポーネントのスナップショットテスト', () => {
    const { container } = render(<MyComponent />);
    expect(container).toMatchSnapshot();
});
```

#### 2.2 統合テスト

```typescript
// 統合テストの実装例

// 1. APIエンドポイントのテスト
// app.test.ts
import request from 'supertest';
import app from './app';
import { db } from './database';

describe('User API', () => {
    beforeAll(async () => {
        await db.connect();
    });

    afterAll(async () => {
        await db.close();
    });

    beforeEach(async () => {
        await db.clear();
    });

    test('ユーザーを作成できる', async () => {
        const response = await request(app)
            .post('/api/users')
            .send({
                name: '田中',
                email: 'tanaka@example.com'
            });

        expect(response.status).toBe(201);
        expect(response.body).toHaveProperty('id');
        expect(response.body.name).toBe('田中');
    });

    test('無効なデータでは400エラーを返す', async () => {
        const response = await request(app)
            .post('/api/users')
            .send({
                name: ''  // 名前は必須
            });

        expect(response.status).toBe(400);
        expect(response.body).toHaveProperty('error');
    });
});

// 2. データベース統合テスト
// database.test.ts
describe('Database Integration', () => {
    beforeAll(async () => {
        await db.connect();
    });

    afterAll(async () => {
        await db.close();
    });

    beforeEach(async () => {
        await db.clear();
    });

    test('ユーザーをデータベースに保存できる', async () => {
        const user = await db.users.create({
            name: '田中',
            email: 'tanaka@example.com'
        });

        const found = await db.users.findById(user.id);
        expect(found).toBeDefined();
        expect(found.name).toBe('田中');
    });

    test('一意性制約が機能する', async () => {
        await db.users.create({
            email: 'tanaka@example.com',
            name: '田中'
        });

        await expect(db.users.create({
            email: 'tanaka@example.com',  // 同じメールアドレス
            name: '鈴木'
        })).rejects.toThrow();
    });
});

// 3. E2Eテスト（Cypress使用例）
// cypress/integration/login.spec.ts
describe('ログインフロー', () => {
    beforeEach(() => {
        cy.visit('/login');
    });

    it('正常にログインできる', () => {
        cy.get('[data-testid=email]').type('user@example.com');
        cy.get('[data-testid=password]').type('password123');
        cy.get('[data-testid=submit]').click();

        cy.url().should('include', '/dashboard');
        cy.get('[data-testid=welcome]').should('contain', 'ようこそ');
    });

    it('無効な認証情報ではエラーを表示する', () => {
        cy.get('[data-testid=email]').type('invalid@example.com');
        cy.get('[data-testid=password]').type('wrongpass');
        cy.get('[data-testid=submit]').click();

        cy.get('[data-testid=error]').should('be.visible');
    });
});

// 4. コンポーネント統合テスト
// React Testing Libraryの使用例
import { render, fireEvent, waitFor } from '@testing-library/react';
import UserList from './UserList';

describe('UserList Component', () => {
    test('ユーザーリストを表示できる', async () => {
        const { getByText, getAllByRole } = render(<UserList />);
        
        // データ読み込み中の表示
        expect(getByText('読み込み中...')).toBeInTheDocument();
        
        // データ読み込み完了後
        await waitFor(() => {
            const users = getAllByRole('listitem');
            expect(users).toHaveLength(3);
        });
    });

    test('ユーザーの検索が機能する', async () => {
        const { getByPlaceholderText, getAllByRole } = render(<UserList />);
        
        const searchInput = getByPlaceholderText('ユーザーを検索');
        fireEvent.change(searchInput, { target: { value: '田中' } });
        
        await waitFor(() => {
            const users = getAllByRole('listitem');
            expect(users).toHaveLength(1);
            expect(users[0]).toHaveTextContent('田中');
        });
    });
});
```

[続く...]

### 3. パフォーマンス最適化

#### 3.1 ビルド最適化

```typescript
// TypeScript/JavaScriptのビルド最適化テクニック

// 1. Tree Shaking
// webpack.config.js
module.exports = {
    mode: 'production',  // プロダクションモードで自動的にTree Shakingが有効化
    optimization: {
        usedExports: true,  // 使用されているエクスポートのみを含める
        minimize: true      // コードの最小化
    }
};

// Tree Shakingの効果的な書き方
// bad.ts - Tree Shakingされにくい
export default {
    helper1: () => { /* ... */ },
    helper2: () => { /* ... */ }
};

// good.ts - Tree Shakingされやすい
export const helper1 = () => { /* ... */ };
export const helper2 = () => { /* ... */ };

// 2. コード分割
// 動的インポート
const MyComponent = React.lazy(() => import('./MyComponent'));

// ルートベースの分割
const routes = [
    {
        path: '/dashboard',
        component: React.lazy(() => import('./pages/Dashboard'))
    },
    {
        path: '/profile',
        component: React.lazy(() => import('./pages/Profile'))
    }
];

// Suspenseでラッピング
function App() {
    return (
        <Suspense fallback={<Loading />}>
            <Router>
                <Switch>
                    {routes.map(route => (
                        <Route
                            key={route.path}
                            path={route.path}
                            component={route.component}
                        />
                    ))}
                </Switch>
            </Router>
        </Suspense>
    );
}

// 3. バンドル分析
// package.json
{
    "scripts": {
        "analyze": "webpack-bundle-analyzer stats.json"
    }
}

// webpack.config.js
const BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin;

module.exports = {
    plugins: [
        new BundleAnalyzerPlugin()
    ]
};

// 4. キャッシュ最適化
// webpack.config.js
module.exports = {
    output: {
        filename: '[name].[contenthash].js'  // コンテンツハッシュを使用
    },
    optimization: {
        moduleIds: 'deterministic',  // モジュールIDの安定化
        runtimeChunk: 'single',      // ランタイムコードの分離
        splitChunks: {               // 共通モジュールの分割
            cacheGroups: {
                vendor: {
                    test: /[\\/]node_modules[\\/]/,
                    name: 'vendors',
                    chunks: 'all'
                }
            }
        }
    }
};
```

#### 3.2 実行時最適化

```typescript
// 実行時のパフォーマンス最適化テクニック

// 1. メモ化
// Reactコンポーネントのメモ化
const MemoizedComponent = React.memo(function MyComponent(props) {
    return (
        <div>
            {/* 重い処理を含むレンダリング */}
            {expensiveOperation(props.data)}
        </div>
    );
});

// useMemoフックの使用
function SearchResults({ query, data }) {
    const filteredData = React.useMemo(() => {
        return data.filter(item => 
            item.name.toLowerCase().includes(query.toLowerCase())
        );
    }, [query, data]);  // 依存配列

    return (
        <ul>
            {filteredData.map(item => (
                <li key={item.id}>{item.name}</li>
            ))}
        </ul>
    );
}

// useCallbackフックの使用
function ParentComponent() {
    const [count, setCount] = useState(0);

    const handleClick = useCallback(() => {
        setCount(c => c + 1);
    }, []);  // 空の依存配列

    return <ChildComponent onClick={handleClick} />;
}

// 2. 仮想化（Virtualization）
// react-windowを使用した例
import { FixedSizeList } from 'react-window';

function VirtualizedList({ items }) {
    const Row = ({ index, style }) => (
        <div style={style}>
            {items[index].name}
        </div>
    );

    return (
        <FixedSizeList
            height={400}
            width={300}
            itemCount={items.length}
            itemSize={35}
        >
            {Row}
        </FixedSizeList>
    );
}

// 3. イベント最適化
// デバウンス
function debounce<T extends (...args: any[]) => any>(
    func: T,
    wait: number
): (...args: Parameters<T>) => void {
    let timeout: NodeJS.Timeout;

    return function(...args: Parameters<T>) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func(...args), wait);
    };
}

// 使用例
const handleSearch = debounce((query: string) => {
    // APIリクエストなどの重い処理
    searchAPI(query);
}, 300);

// スロットル
function throttle<T extends (...args: any[]) => any>(
    func: T,
    limit: number
): (...args: Parameters<T>) => void {
    let inThrottle: boolean;

    return function(...args: Parameters<T>) {
        if (!inThrottle) {
            func(...args);
            inThrottle = true;
            setTimeout(() => inThrottle = false, limit);
        }
    };
}

// 使用例
const handleScroll = throttle(() => {
    // スクロール処理
    updateScrollPosition();
}, 100);

// 4. メモリ管理
// メモリリークの防止
function Component() {
    useEffect(() => {
        const subscription = eventEmitter.subscribe(handleEvent);
        
        // クリーンアップ関数
        return () => {
            subscription.unsubscribe();
        };
    }, []);

    // WeakMapの使用
    const cache = new WeakMap();
    
    function getCachedData(obj: object) {
        if (!cache.has(obj)) {
            cache.set(obj, computeExpensiveData(obj));
        }
        return cache.get(obj);
    }
}

// 5. Web Workers
// worker.ts
const worker = new Worker('worker.js');

worker.postMessage({
    type: 'HEAVY_CALCULATION',
    data: largeDataSet
});

worker.onmessage = (event) => {
    const result = event.data;
    updateUI(result);
};

// 6. パフォーマンス測定
// パフォーマンスマーク
performance.mark('startProcess');
// 重い処理
performance.mark('endProcess');

performance.measure(
    'processTime',
    'startProcess',
    'endProcess'
);

// React Performance Profiler
import { Profiler } from 'react';

function onRenderCallback(
    id: string,
    phase: "mount" | "update",
    actualDuration: number,
    baseDuration: number,
    startTime: number,
    commitTime: number
) {
    console.log(`Component ${id} took ${actualDuration}ms to render`);
}

function App() {
    return (
        <Profiler id="App" onRender={onRenderCallback}>
            <MyComponent />
        </Profiler>
    );
}
```

これらの最適化テクニックを適切に組み合わせることで、アプリケーションの性能を大幅に向上させることができます。次のパートでは、セキュリティと保守性について学んでいきます。

## Part 5: セキュリティと保守性

### 1. セキュリティ対策

```typescript
// TypeScript/JavaScriptのセキュリティ実装

// 1. XSS（クロスサイトスクリプティング）対策
// - 入力値のサニタイズ
function sanitizeInput(input: string): string {
    return input
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;')
        .replace(/'/g, '&#x27;')
        .replace(/\//g, '&#x2F;');
}

// DOMPurifyの使用
import DOMPurify from 'dompurify';

function renderHTML(content: string): void {
    const clean = DOMPurify.sanitize(content);
    document.getElementById('content').innerHTML = clean;
}

// Reactでの安全なHTML表示
function SafeComponent({ html }: { html: string }) {
    return <div dangerouslySetInnerHTML={{ __html: DOMPurify.sanitize(html) }} />;
}

// 2. CSRF（クロスサイトリクエストフォージェリ）対策
// - トークンの生成と検証
function generateCSRFToken(): string {
    return crypto.randomBytes(32).toString('hex');
}

// Expressミドルウェアの例
app.use((req, res, next) => {
    if (!req.session.csrfToken) {
        req.session.csrfToken = generateCSRFToken();
    }
    res.locals.csrfToken = req.session.csrfToken;
    next();
});

// APIリクエストでのトークン検証
const validateCSRF = (req, res, next) => {
    const token = req.headers['x-csrf-token'];
    if (!token || token !== req.session.csrfToken) {
        return res.status(403).json({ error: 'Invalid CSRF token' });
    }
    next();
};

// 3. 認証とセッション管理
// - セキュアなパスワードハッシュ化
import * as bcrypt from 'bcrypt';

async function hashPassword(password: string): Promise<string> {
    const saltRounds = 12;
    return bcrypt.hash(password, saltRounds);
}

async function verifyPassword(password: string, hash: string): Promise<boolean> {
    return bcrypt.compare(password, hash);
}

// JWTを使用した認証
import * as jwt from 'jsonwebtoken';

interface TokenPayload {
    userId: string;
    role: string;
}

function generateToken(payload: TokenPayload): string {
    return jwt.sign(payload, process.env.JWT_SECRET!, {
        expiresIn: '1h',
        algorithm: 'HS256'
    });
}

function verifyToken(token: string): TokenPayload {
    return jwt.verify(token, process.env.JWT_SECRET!) as TokenPayload;
}

// 4. セキュアなHTTPヘッダー
// Expressでのセキュリティヘッダー設定
import helmet from 'helmet';

app.use(helmet());  // 基本的なセキュリティヘッダーを設定

app.use(helmet.contentSecurityPolicy({
    directives: {
        defaultSrc: ["'self'"],
        scriptSrc: ["'self'", "'unsafe-inline'"],
        styleSrc: ["'self'", "'unsafe-inline'"],
        imgSrc: ["'self'", "data:", "https:"],
    }
}));

// 5. 入力バリデーション
// - Zodを使用した型安全なバリデーション
import { z } from 'zod';

const UserSchema = z.object({
    username: z.string().min(3).max(20),
    email: z.string().email(),
    password: z.string().min(8).regex(/[A-Z]/).regex(/[0-9]/)
});

type User = z.infer<typeof UserSchema>;

function validateUser(data: unknown): User {
    return UserSchema.parse(data);
}

// 使用例
try {
    const user = validateUser({
        username: "john_doe",
        email: "john@example.com",
        password: "Password123"
    });
    // バリデーション成功
} catch (error) {
    // バリデーションエラーの処理
    console.error(error);
}

// 6. セキュアな環境変数管理
// .env
// DATABASE_URL=postgresql://user:password@localhost:5432/db
// JWT_SECRET=your-secret-key
// API_KEY=your-api-key

// 環境変数の型定義
declare global {
    namespace NodeJS {
        interface ProcessEnv {
            DATABASE_URL: string;
            JWT_SECRET: string;
            API_KEY: string;
            NODE_ENV: 'development' | 'production' | 'test';
        }
    }
}

// 環境変数のバリデーション
const envSchema = z.object({
    DATABASE_URL: z.string().url(),
    JWT_SECRET: z.string().min(32),
    API_KEY: z.string(),
    NODE_ENV: z.enum(['development', 'production', 'test'])
});

// 起動時に環境変数を検証
function validateEnv() {
    try {
        envSchema.parse(process.env);
    } catch (error) {
        console.error('環境変数の検証に失敗:', error);
        process.exit(1);
    }
}
```

### 2. コード品質の維持

```typescript
// コード品質を維持するためのプラクティス

// 1. ESLintの設定
// .eslintrc.js
module.exports = {
    parser: '@typescript-eslint/parser',
    extends: [
        'eslint:recommended',
        'plugin:@typescript-eslint/recommended',
        'plugin:security/recommended'
    ],
    plugins: [
        '@typescript-eslint',
        'security'
    ],
    rules: {
        // セキュリティ関連のルール
        'security/detect-object-injection': 'error',
        'security/detect-non-literal-regexp': 'error',
        'security/detect-unsafe-regex': 'error',
        
        // TypeScriptの厳格なルール
        '@typescript-eslint/explicit-function-return-type': 'error',
        '@typescript-eslint/no-explicit-any': 'error',
        '@typescript-eslint/strict-boolean-expressions': 'error',
        
        // コード品質のルール
        'complexity': ['error', 10],
        'max-lines-per-function': ['error', 50],
        'max-depth': ['error', 3]
    }
};

// 2. Prettierの設定
// .prettierrc
{
    "semi": true,
    "trailingComma": "es5",
    "singleQuote": true,
    "printWidth": 80,
    "tabWidth": 2,
    "useTabs": false
}

// 3. コードドキュメンテーション
/**
 * ユーザー情報を処理するサービスクラス
 * @class UserService
 */
class UserService {
    /**
     * ユーザーを作成する
     * @param {CreateUserDto} userData - ユーザー作成に必要なデータ
     * @returns {Promise<User>} 作成されたユーザー
     * @throws {ValidationError} バリデーションエラー
     */
    async createUser(userData: CreateUserDto): Promise<User> {
        // 実装
    }
}

// 4. エラー処理
// カスタムエラークラス
class AppError extends Error {
    constructor(
        public readonly code: string,
        message: string,
        public readonly statusCode: number = 500
    ) {
        super(message);
        this.name = 'AppError';
    }
}

// エラーハンドリングミドルウェア
function errorHandler(
    error: Error,
    req: Request,
    res: Response,
    next: NextFunction
): void {
    if (error instanceof AppError) {
        res.status(error.statusCode).json({
            code: error.code,
            message: error.message
        });
    } else {
        // 予期しないエラー
        console.error(error);
        res.status(500).json({
            code: 'INTERNAL_ERROR',
            message: '内部サーバーエラー'
        });
    }
}

// 5. ロギング
// Winston設定
import winston from 'winston';

const logger = winston.createLogger({
    level: 'info',
    format: winston.format.combine(
        winston.format.timestamp(),
        winston.format.json()
    ),
    transports: [
        new winston.transports.File({ filename: 'error.log', level: 'error' }),
        new winston.transports.File({ filename: 'combined.log' })
    ]
});

// 開発環境では標準出力も追加
if (process.env.NODE_ENV !== 'production') {
    logger.add(new winston.transports.Console({
        format: winston.format.simple()
    }));
}

// 6. テスト可能な設計
// 依存性注入を使用した設計
interface UserRepository {
    findById(id: string): Promise<User>;
    save(user: User): Promise<void>;
}

class UserService {
    constructor(private readonly userRepo: UserRepository) {}

    async updateUser(id: string, data: UpdateUserDto): Promise<User> {
        const user = await this.userRepo.findById(id);
        if (!user) {
            throw new AppError('USER_NOT_FOUND', 'ユーザーが見つかりません', 404);
        }
        
        Object.assign(user, data);
        await this.userRepo.save(user);
        return user;
    }
}

// テストコード
describe('UserService', () => {
    let userService: UserService;
    let mockUserRepo: jest.Mocked<UserRepository>;

    beforeEach(() => {
        mockUserRepo = {
            findById: jest.fn(),
            save: jest.fn()
        };
        userService = new UserService(mockUserRepo);
    });

    test('存在しないユーザーの更新は404エラー', async () => {
        mockUserRepo.findById.mockResolvedValue(null);

        await expect(userService.updateUser('123', {}))
            .rejects
            .toThrow('ユーザーが見つかりません');
    });
});
```

これらのセキュリティ対策とコード品質維持の手法を適切に実装することで、安全で保守性の高いアプリケーションを開発できます。

## 補足資料

### 索引

- [はじめに](#はじめに)
- [Part 1: 開発環境とツール](#part-1-開発環境とツール)
- [Part 2: JavaScript基礎](#part-2-javascript基礎)
- [Part 3: TypeScript基礎](#part-3-typescript基礎)
- [Part 4: 実践的な開発手法](#part-4-実践的な開発手法)
- [Part 5: セキュリティと保守性](#part-5-セキュリティと保守性)

### 用語集

- [JavaScript](#javascript)
- [TypeScript](#typescript)
- [Node.js](#nodejs)
- [npm](#npm)
- [Visual Studio Code](#visual-studio-code)
- [ESLint](#eslint)
- [Prettier](#prettier)
- [Jest](#jest)
- [webpack](#webpack)
- [ts-node-dev](#ts-node-dev)
- [tsconfig.json](#tsconfigjson)
- [.env](#env)
- [Git](#git)
- [nvm](#nvm)
- [Supertest](#supertest)
- [bcrypt](#bcrypt)

### チートシート

- [ショートカットキー](#ショートカットキー)
- [よくあるエラーと解決方法](#よくあるエラーと解決方法)
- [コードフォーマットのルール](#コードフォーマットのルール)
- [テストの実行方法](#テストの実行方法)
- [デバッグの基本操作](#デバッグの基本操作)

### 参考リソース

- [MDN Web Docs](https://developer.mozilla.org/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Node.js Documentation](https://nodejs.org/docs/)
- [Express.js Documentation](https://expressjs.com/)
- [Jest Documentation](https://jestjs.io/docs/getting-started)
- [Webpack Documentation](https://webpack.js.org/concepts/)
- [ts-node-dev Documentation](https://github.com/whitecolor/ts-node-dev)
- [ESLint Documentation](https://eslint.org/docs/latest/)
- [Prettier Documentation](https://prettier.io/docs/en/index.html)
- [Supertest Documentation](https://github.com/visionmedia/supertest)
- [bcrypt Documentation](https://www.npmjs.com/package/bcrypt)
