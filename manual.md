# Angular開発のための JavaScript/TypeScript マニュアル

## 目次

- [はじめに](#はじめに)
- [Part 1: 開発環境とツール（初めの一歩）](#part-1-開発環境とツール初めの一歩)
  - [1.1 Angularプロジェクトの開発環境](#11-angularプロジェクトの開発環境)
  - [1.2 基本的なコマンドと開発フロー](#12-基本的なコマンドと開発フロー)
- [Part 2: JavaScript基礎](#part-2-javascript基礎)
- [Part 3: TypeScript基礎](#part-3-typescript基礎)
- [Part 4: Angular固有の機能](#part-4-angular固有の機能)
- [Part 5: デバッグとトラブルシューティング](#part-5-デバッグとトラブルシューティング)
- [Part 6: テストの基礎](#part-6-テストの基礎)
- [Part 7: セキュリティの基礎](#part-7-セキュリティの基礎)
- [Part 8: パフォーマンス最適化](#part-8-パフォーマンス最適化)
- [Part 9: 実践的なユースケース](#part-9-実践的なユースケース)
- [Part 10: 開発フロー](#part-10-開発フロー)

## はじめに

このマニュアルは、Angular開発に必要なJavaScriptとTypeScriptの知識を体系的に学ぶためのガイドです。
プログラミング初心者の方でも理解できるよう、基礎から丁寧に解説していきます。

### このマニュアルの使い方

1. **段階的な学習**: 
   - 各パートは基礎から応用へと段階的に構成されています
   - 必要な部分から読み進めることができます
   - コードサンプルを実際に試しながら学習することを推奨します

2. **環境準備**:
   - Part 1 で開発環境のセットアップを行います
   - 実際に手を動かしながら学習することで、より深い理解が得られます

3. **トラブルシューティング**:
   - 各セクションには「よくある問題と解決方法」が含まれています
   - エラーが発生した場合は、該当するセクションを参照してください

### 前提知識

このマニュアルを効果的に活用するために、以下の知識があると望ましいです：

- PCの基本的な操作ができること
- HTML/CSSの基礎的な知識
- テキストエディタ（Visual Studio Codeなど）の基本的な使い方

前提知識が不足している場合でも、丁寧に解説していきますので、焦らず順を追って学習してください。

## Part 1: 開発環境とツール（初めの一歩）

### 1.1 Angularプロジェクトの開発環境

#### 1.1.1 Node.jsのインストールと基礎知識

##### Node.jsとは

Node.jsは、JavaScriptをサーバーサイドで実行するための環境です。Angular開発には必須のツールとなります。

**なぜNode.jsが必要なのか？**

Angular開発において、Node.jsは以下の役割を果たします：

1. パッケージ管理（npm）
2. 開発サーバーの実行
3. ビルドツールの実行
4. テスト環境の提供

##### Node.jsのインストール手順

1. Node.jsの公式サイト（https://nodejs.org/）にアクセス
2. LTS（Long Term Support）バージョンをダウンロード
3. インストーラーを実行

インストールの確認：
```bash
# バージョンの確認
node -v
npm -v
```

期待される出力例：
```
v18.17.0  # Node.jsのバージョン
9.6.7     # npmのバージョン
```

##### バージョン管理（nvmの使い方）

nvm（Node Version Manager）を使用すると、複数のNode.jsバージョンを管理できます。

**nvmのインストール**:

Linux/macOSの場合：
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```

Windowsの場合：
- [nvm-windows](https://github.com/coreybutler/nvm-windows/releases)からインストーラーをダウンロード

**基本的なnvmコマンド**:
```bash
# 利用可能なNode.jsバージョンの一覧表示
nvm list-remote

# 特定のバージョンをインストール
nvm install 18.17.0

# 使用するバージョンの切り替え
nvm use 18.17.0

# インストール済みバージョンの確認
nvm list
```

#### 1.1.2 Angular CLIの導入

##### Angular CLIとは

Angular CLIは、Angularアプリケーションの作成、開発、テスト、デプロイを支援するコマンドラインツールです。

**主な機能**:
- プロジェクトの作成
- コンポーネント、サービスなどの自動生成
- 開発サーバーの起動
- ビルドとデプロイ

##### インストール手順

```bash
# グローバルにAngular CLIをインストール
npm install -g @angular/cli

# インストールの確認
ng version
```

期待される出力例：
```
Angular CLI: 16.2.0
Node: 18.17.0
Package Manager: npm 9.6.7
OS: Windows 10
```

##### 基本的なコマンドの説明

```bash
# 新しいプロジェクトの作成
ng new my-app

# コンポーネントの生成
ng generate component my-component

# 開発サーバーの起動
ng serve

# プロダクションビルド
ng build --prod
```

#### 1.1.3 Visual Studio Codeの設定

##### 推奨の拡張機能

1. **Angular Essential**:
   - Angular Language Service
   - Angular Snippets
   - Angular Console

インストール手順：
1. VS Codeを起動
2. 拡張機能タブを開く（Ctrl+Shift+X）
3. 以下の拡張機能を検索してインストール：
   - "Angular Language Service"
   - "Angular Snippets (Version X)"
   - "Angular Console"

##### デバッグ環境の設定

1. `launch.json`の作成：
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Launch Chrome against localhost",
      "url": "http://localhost:4200",
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```

2. ブレークポイントの設定方法：
   - コード行の左側をクリック
   - F9キーを押す
   - デバッグビュー（Ctrl+Shift+D）からブレークポイントを管理

##### エディタの基本的な使い方

**よく使うショートカット**:

| 操作 | Windows | Mac |
|------|---------|-----|
| ファイル内検索 | Ctrl+F | Cmd+F |
| プロジェクト内検索 | Ctrl+Shift+F | Cmd+Shift+F |
| 定義へ移動 | F12 | F12 |
| コード整形 | Alt+Shift+F | Opt+Shift+F |
| クイックフィックス | Ctrl+. | Cmd+. |

### 1.2 基本的なコマンドと開発フロー

#### 1.2.1 npmの基本

##### package.jsonの役割と構造

`package.json`は、プロジェクトの設定と依存関係を管理する重要なファイルです。

```json
{
  "name": "my-angular-app",
  "version": "0.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "dependencies": {
    "@angular/common": "^16.2.0",
    "@angular/core": "^16.2.0"
    // ... その他の依存関係
  },
  "devDependencies": {
    "@types/jasmine": "~4.3.0",
    "@types/node": "^18.17.0"
    // ... その他の開発用依存関係
  }
}
```

主なセクション：
- `scripts`: 実行可能なnpmスクリプト
- `dependencies`: アプリケーションの実行に必要なパッケージ
- `devDependencies`: 開発時のみ必要なパッケージ

##### よく使うnpmコマンド

```bash
# パッケージのインストール
npm install

# 特定のパッケージをインストール
npm install パッケージ名

# 開発依存パッケージとしてインストール
npm install --save-dev パッケージ名

# パッケージの更新
npm update

# スクリプトの実行
npm run スクリプト名
```

##### パッケージのインストールと更新

**パッケージのバージョン管理**:
```bash
# 特定のバージョンをインストール
npm install パッケージ名@バージョン

# 最新バージョンにアップデート
npm install パッケージ名@latest

# パッケージの依存関係を表示
npm list
```

#### 1.2.2 Angular CLIコマンド

##### プロジェクト作成（ng new）

```bash
# 基本的なプロジェクト作成
ng new my-app

# オプションを指定してプロジェクト作成
ng new my-app --routing --style scss
```

主なオプション：
- `--routing`: ルーティング機能を追加
- `--style`: スタイルシート形式を指定（css/scss/sass/less）
- `--prefix`: セレクタープレフィックスを指定
- `--skip-tests`: テストファイルを生成しない

##### コンポーネント作成（ng generate）

```bash
# コンポーネントの生成
ng generate component my-component

# サービスの生成
ng generate service my-service

# その他の生成コマンド
ng generate directive my-directive
ng generate pipe my-pipe
ng generate class my-class
ng generate interface my-interface
ng generate enum my-enum
```

##### 開発サーバー起動（ng serve）

```bash
# 基本的な起動
ng serve

# ポート指定
ng serve --port 4201

# ホスト指定（他のデバイスからアクセス可能に）
ng serve --host 0.0.0.0

# 自動的にブラウザを開く
ng serve --open
```

#### 1.2.3 プロジェクト作成と起動

##### プロジェクト構造の説明

典型的なAngularプロジェクトの構造：

```
my-app/
├── src/
│   ├── app/
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   ├── app.component.scss
│   │   └── app.module.ts
│   ├── assets/
│   ├── environments/
│   ├── index.html
│   └── main.ts
├── angular.json
├── package.json
├── tsconfig.json
└── README.md
```

主要なファイルとディレクトリ：
- `src/app/`: アプリケーションのメインコード
- `src/assets/`: 画像やその他の静的ファイル
- `src/environments/`: 環境設定
- `angular.json`: Angularプロジェクトの設定
- `tsconfig.json`: TypeScriptの設定

##### 設定ファイルの役割

**angular.json**:
```json
{
  "projects": {
    "my-app": {
      "architect": {
        "build": {
          "options": {
            "outputPath": "dist/my-app",
            "index": "src/index.html",
            "main": "src/main.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "tsconfig.json"
          }
        }
      }
    }
  }
}
```

**tsconfig.json**:
```json
{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "module": "es2020",
    "moduleResolution": "node",
    "experimentalDecorators": true,
    "target": "es2020",
    "typeRoots": [
      "node_modules/@types"
    ],
    "lib": [
      "es2020",
      "dom"
    ]
  }
}
```

##### 開発サーバーの使い方

1. サーバーの起動：
```bash
ng serve
```

2. 開発中の便利な機能：
   - ホットリロード（自動更新）
   - エラー表示
   - コンソールログ

3. よくあるエラーと解決方法：

| エラー | 解決方法 |
|--------|----------|
| ポートが使用中 | 別のポートを指定（`ng serve --port 4201`） |
| モジュールが見つからない | `npm install`を実行 |
| コンパイルエラー | エラーメッセージを確認し、該当箇所を修正 |

---

次のパートでは、JavaScript基礎について解説していきます。 

## Part 2: JavaScript基礎（Angular開発の文脈で）

### 2.1 変数とデータ型

#### 2.1.1 変数の基本

##### 変数とは

変数は、データを格納するためのコンテナ（入れ物）です。Angularアプリケーションでは、コンポーネントのプロパティやサービスの状態管理などで頻繁に使用します。

**なぜ変数が必要か**:
- データの一時的な保存
- 値の再利用
- 状態の管理

##### 変数の命名規則

```javascript
// 良い例
let userName = "John";
let isLoggedIn = true;
let userAge = 25;

// 悪い例
let u = "John";      // 意味が不明確
let USER_NAME = "John";  // 定数でない場合は大文字は不適切
let user_name = "John";  // キャメルケースを使用すべき
```

Angularでの実践的な命名例：
```typescript
// コンポーネントでの変数命名
export class UserProfileComponent {
  currentUser: User;          // ユーザー情報
  isLoading = false;         // 読み込み状態
  errorMessage = '';         // エラーメッセージ
  private userService: UserService;  // サービスのインスタンス
}
```

#### 2.1.2 変数の宣言（var, let, const）

##### それぞれの違いと使い分け

```javascript
// var - 関数スコープ（非推奨）
var message = "Hello";
var message = "Hi";  // 再宣言可能（バグの原因になりやすい）

// let - ブロックスコープ（推奨）
let count = 1;
count = 2;  // 再代入可能
// let count = 3;  // エラー: 再宣言不可

// const - 定数（推奨）
const API_URL = "https://api.example.com";
// API_URL = "https://new-api.example.com";  // エラー: 再代入不可
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-list',
  template: `
    <div *ngFor="let user of users">
      {{ user.name }}
    </div>
  `
})
export class UserListComponent {
  // 定数の使用例
  private readonly API_ENDPOINT = '/api/users';
  
  // 変更可能な状態
  let currentPage = 1;
  
  // サービスのインジェクション（定数として扱う）
  constructor(private readonly userService: UserService) {}
}
```

##### スコープの概念

```javascript
function example() {
  let x = 1;  // 関数スコープ内
  
  if (true) {
    let y = 2;  // ブロックスコープ内
    console.log(x);  // 1 - 外側のスコープにアクセス可能
  }
  
  // console.log(y);  // エラー - yはブロックスコープ外
}
```

Angularでのスコープ例：
```typescript
@Component({
  template: `
    <div *ngIf="isLoggedIn">
      {{ userName }}  // テンプレート内でのスコープ
    </div>
  `
})
export class AuthComponent {
  private isLoggedIn = false;  // クラススコープ
  
  login() {
    const token = 'xxx';  // 関数スコープ
    this.isLoggedIn = true;
  }
}
```

##### ホイスティングとは

```javascript
// ホイスティングの例
console.log(x);  // undefined
var x = 5;

// 上記は実際には以下のように解釈される
var x;
console.log(x);
x = 5;

// letとconstはホイスティングされるが、TDZ（Temporal Dead Zone）により
// 初期化前のアクセスでエラーになる
// console.log(y);  // エラー
let y = 5;
```

#### 2.1.3 基本的なデータ型

##### プリミティブ型

```typescript
// 数値型（number）
let age: number = 25;
let price: number = 99.99;
let discount: number = 0.1;

// 文字列型（string）
let name: string = "John";
let greeting: string = `Hello, ${name}!`;  // テンプレートリテラル

// 真偽値型（boolean）
let isActive: boolean = true;
let isLoading: boolean = false;

// null と undefined
let nullValue: null = null;
let undefinedValue: undefined = undefined;

// シンボル型（symbol）
const uniqueKey = Symbol('description');
```

Angularでの使用例：
```typescript
interface User {
  id: number;
  name: string;
  isAdmin: boolean;
  lastLogin: Date | null;
  preferences?: {
    theme: string;
    notifications: boolean;
  };
}

@Component({
  selector: 'app-user-profile',
  template: `
    <div *ngIf="user">
      <h2>{{ user.name }}</h2>
      <p>Admin: {{ user.isAdmin }}</p>
      <p>Last Login: {{ user.lastLogin | date }}</p>
    </div>
  `
})
export class UserProfileComponent {
  user: User = {
    id: 1,
    name: "John Doe",
    isAdmin: false,
    lastLogin: new Date(),
    preferences: {
      theme: "dark",
      notifications: true
    }
  };
}
```

#### 2.1.4 テンプレート文字列

##### バッククォート記法の使い方

```typescript
// 基本的な使用法
const name = "John";
const age = 30;
const message = `Hello, ${name}! You are ${age} years old.`;

// 複数行の文字列
const template = `
  <div>
    <h1>Welcome</h1>
    <p>This is a multiline string</p>
  </div>
`;

// 式の埋め込み
const a = 5;
const b = 10;
const result = `The sum is ${a + b}`;
```

Angularでの実践的な使用例：
```typescript
@Component({
  selector: 'app-greeting',
  template: `
    <div class="greeting ${isSpecial ? 'special' : ''}">
      <h1>Welcome, ${userName}!</h1>
      ${
        isLoggedIn 
          ? `<p>Last login: ${lastLoginDate}</p>`
          : `<p>Please log in</p>`
      }
    </div>
  `
})
export class GreetingComponent {
  userName = "John";
  isSpecial = true;
  isLoggedIn = true;
  lastLoginDate = new Date().toLocaleDateString();
}
```

#### 2.1.5 型変換

##### 暗黙的な型変換

```javascript
// 文字列への変換
let num = 5;
let str = "The number is: " + num;  // 数値が文字列に変換される

// 数値への変換
let str2 = "5";
let num2 = str2 * 1;  // 文字列が数値に変換される

// 真偽値への変換
if ("hello") {  // 空でない文字列はtrueとして評価
  console.log("This will be printed");
}

if (0) {  // 0はfalseとして評価
  console.log("This won't be printed");
}
```

##### 明示的な型変換

```typescript
// 文字列への変換
let num = 5;
let str1 = String(num);
let str2 = num.toString();

// 数値への変換
let str = "5.5";
let num1 = Number(str);
let num2 = parseInt(str);    // 整数部分のみ
let num3 = parseFloat(str);  // 小数点も含む

// 真偽値への変換
let value = "true";
let bool1 = Boolean(value);
let bool2 = !!value;
```

Angularでの型変換の実践例：
```typescript
@Component({
  selector: 'app-form-example',
  template: `
    <input type="number" [value]="quantity" (input)="updateQuantity($event)">
    <p>Total: {{ calculateTotal() }}</p>
  `
})
export class FormExampleComponent {
  quantity = 0;
  price = 9.99;

  updateQuantity(event: Event) {
    // input要素の値を数値に変換
    const input = event.target as HTMLInputElement;
    this.quantity = Number(input.value);
  }

  calculateTotal(): string {
    // 計算結果を2桁の小数点付き文字列に変換
    return (this.quantity * this.price).toFixed(2);
  }
}
```

##### よくあるバグと対処法

```typescript
// 問題: 数値の加算が文字列連結になってしまう
let value1 = "5";
let value2 = "10";
console.log(value1 + value2);  // "510"

// 解決策: 明示的な型変換を行う
console.log(Number(value1) + Number(value2));  // 15

// 問題: NaNの扱い
let result = parseInt("not a number");
console.log(result);  // NaN

// 解決策: isNaN関数で確認
if (isNaN(result)) {
  console.log("Invalid number");
}

// より安全な方法: Number.isNaN
if (Number.isNaN(result)) {
  console.log("Invalid number");
}
```

Angularでのバグ対策例：
```typescript
@Component({
  selector: 'app-calculator',
  template: `
    <input type="text" [value]="input1" (input)="updateInput1($event)">
    <input type="text" [value]="input2" (input)="updateInput2($event)">
    <p>Result: {{ calculateResult() }}</p>
  `
})
export class CalculatorComponent {
  input1 = '';
  input2 = '';

  updateInput1(event: Event) {
    const input = event.target as HTMLInputElement;
    this.input1 = input.value;
  }

  updateInput2(event: Event) {
    const input = event.target as HTMLInputElement;
    this.input2 = input.value;
  }

  calculateResult(): string {
    // 入力値を数値に変換し、有効性をチェック
    const num1 = Number(this.input1);
    const num2 = Number(this.input2);

    if (Number.isNaN(num1) || Number.isNaN(num2)) {
      return 'Invalid input';
    }

    return String(num1 + num2);
  }
}
```

### 2.2 演算子と制御構文

#### 2.2.1 演算子

##### 算術演算子

```typescript
// 基本的な算術演算子
let a = 5;
let b = 3;

let sum = a + b;      // 加算: 8
let diff = a - b;     // 減算: 2
let product = a * b;  // 乗算: 15
let quotient = a / b; // 除算: 1.6666...
let remainder = a % b;// 剰余: 2

// インクリメント/デクリメント
let count = 0;
count++;  // 後置インクリメント
++count;  // 前置インクリメント
count--;  // 後置デクリメント
--count;  // 前置デクリメント
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-counter',
  template: `
    <button (click)="increment()">+</button>
    <span>{{ count }}</span>
    <button (click)="decrement()">-</button>
    <p>Total: {{ calculateTotal() }}</p>
  `
})
export class CounterComponent {
  count = 0;
  price = 10;

  increment() {
    this.count++;
  }

  decrement() {
    if (this.count > 0) {
      this.count--;
    }
  }

  calculateTotal(): number {
    return this.count * this.price;
  }
}
```

##### 比較演算子

```typescript
let x = 5;
let y = "5";

// 等価性の比較
console.log(x == y);   // true  (型変換あり)
console.log(x === y);  // false (厳密な比較)
console.log(x != y);   // false (型変換あり)
console.log(x !== y);  // true  (厳密な比較)

// 大小の比較
console.log(x > 3);    // true
console.log(x >= 5);   // true
console.log(x < 10);   // true
console.log(x <= 4);   // false
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-status',
  template: `
    <div [class.premium]="isPremiumUser">
      <p>Status: {{ getUserStatus() }}</p>
      <p *ngIf="score >= 100">Achievement unlocked!</p>
    </div>
  `
})
export class UserStatusComponent {
  userType = 'premium';
  score = 150;

  get isPremiumUser(): boolean {
    return this.userType === 'premium';
  }

  getUserStatus(): string {
    if (this.score >= 100) {
      return 'Gold';
    } else if (this.score >= 50) {
      return 'Silver';
    }
    return 'Bronze';
  }
}
```

##### 論理演算子

```typescript
// AND演算子 (&&)
let isAdult = age >= 18 && hasId;

// OR演算子 (||)
let canAccess = isPremiumUser || hasFreePass;

// NOT演算子 (!)
let isNotLoggedIn = !isLoggedIn;

// 短絡評価
let user = null;
let userName = user && user.name;  // null
let defaultName = userName || 'Guest';  // 'Guest'

// Nullish合体演算子 (??)
let value = null;
let result = value ?? 'default';  // 'default'
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-content',
  template: `
    <div *ngIf="isLoggedIn && hasPermission">
      <h1>Welcome {{ userName || 'Guest' }}</h1>
      <div *ngIf="isAdmin || isModerator">
        <button (click)="deleteItem()">Delete</button>
      </div>
    </div>
  `
})
export class ContentComponent {
  isLoggedIn = true;
  hasPermission = true;
  userName: string | null = null;
  isAdmin = false;
  isModerator = true;

  get canDeleteItem(): boolean {
    return this.isLoggedIn && (this.isAdmin || this.isModerator);
  }

  deleteItem() {
    if (!this.canDeleteItem) {
      return;
    }
    // 削除処理
  }
}
```

#### 2.2.2 条件分岐

##### if文の基本

```typescript
// 基本的なif文
let age = 20;

if (age >= 18) {
  console.log('Adult');
}

// if-else文
if (age >= 18) {
  console.log('Adult');
} else {
  console.log('Minor');
}

// else-if文
if (age >= 65) {
  console.log('Senior');
} else if (age >= 18) {
  console.log('Adult');
} else {
  console.log('Minor');
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-message',
  template: `
    <div [ngClass]="getMessageClass()">
      {{ getMessage() }}
    </div>
  `
})
export class UserMessageComponent {
  userStatus = 'active';
  lastLoginDays = 5;

  getMessage(): string {
    if (this.userStatus === 'blocked') {
      return 'Your account has been blocked';
    } else if (this.lastLoginDays > 30) {
      return 'Welcome back! Long time no see';
    } else if (this.lastLoginDays > 7) {
      return 'Welcome back!';
    } else {
      return 'Welcome!';
    }
  }

  getMessageClass(): string {
    if (this.userStatus === 'blocked') {
      return 'error-message';
    } else if (this.lastLoginDays > 30) {
      return 'warning-message';
    }
    return 'normal-message';
  }
}
```

##### switch文

```typescript
let dayOfWeek = 1;
let dayName: string;

switch (dayOfWeek) {
  case 1:
    dayName = 'Monday';
    break;
  case 2:
    dayName = 'Tuesday';
    break;
  // ... 他の曜日
  default:
    dayName = 'Unknown';
}

// break忘れによるフォールスルー
let response = 'OK';
let statusCode: number;

switch (response) {
  case 'OK':
    statusCode = 200;
    break;
  case 'Created':
    statusCode = 201;
    break;
  case 'Not Found':
    statusCode = 404;
    break;
  default:
    statusCode = 500;
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-status-display',
  template: `
    <div [class]="getStatusClass()">
      {{ getStatusMessage() }}
    </div>
  `
})
export class StatusDisplayComponent {
  status: 'success' | 'warning' | 'error' | 'info' = 'success';

  getStatusClass(): string {
    switch (this.status) {
      case 'success':
        return 'alert alert-success';
      case 'warning':
        return 'alert alert-warning';
      case 'error':
        return 'alert alert-danger';
      case 'info':
        return 'alert alert-info';
      default:
        return 'alert';
    }
  }

  getStatusMessage(): string {
    switch (this.status) {
      case 'success':
        return '操作が成功しました';
      case 'warning':
        return '注意が必要です';
      case 'error':
        return 'エラーが発生しました';
      case 'info':
        return '情報メッセージです';
      default:
        return '';
    }
  }
}
```

##### 三項演算子

```typescript
// 基本的な使用法
let age = 20;
let message = age >= 18 ? 'Adult' : 'Minor';

// ネストした三項演算子（避けるべき）
let status = age >= 65 ? 'Senior' : age >= 18 ? 'Adult' : 'Minor';

// 代わりにif文を使用する方が読みやすい
let status2: string;
if (age >= 65) {
  status2 = 'Senior';
} else if (age >= 18) {
  status2 = 'Adult';
} else {
  status2 = 'Minor';
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-display',
  template: `
    <div [class]="isActive ? 'active' : 'inactive'">
      {{ user ? user.name : 'Guest' }}
      <span [style.color]="isError ? 'red' : 'green'">
        {{ isError ? 'Error!' : 'Success!' }}
      </span>
    </div>
  `
})
export class UserDisplayComponent {
  isActive = true;
  user: User | null = null;
  isError = false;

  getMessage(): string {
    return this.user
      ? `Welcome back, ${this.user.name}!`
      : 'Please log in';
  }

  getButtonText(): string {
    return this.isActive
      ? 'Deactivate'
      : 'Activate';
  }
}
```

#### 2.2.3 ループ処理

##### for文の基本

```typescript
// 基本的なfor文
for (let i = 0; i < 5; i++) {
  console.log(i);  // 0, 1, 2, 3, 4
}

// 配列のループ
const numbers = [1, 2, 3, 4, 5];
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}

// for...of文（イテラブルなオブジェクトの反復）
const fruits = ['apple', 'banana', 'orange'];
for (const fruit of fruits) {
  console.log(fruit);
}

// for...in文（オブジェクトのプロパティ反復）
const user = {
  name: 'John',
  age: 30,
  city: 'Tokyo'
};
for (const key in user) {
  console.log(`${key}: ${user[key]}`);
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-list',
  template: `
    <ul>
      <li *ngFor="let user of users; let i = index; let isFirst = first">
        {{ i + 1 }}. {{ user.name }}
        <span *ngIf="isFirst">(First User!)</span>
      </li>
    </ul>
  `
})
export class UserListComponent {
  users = [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
    { id: 3, name: 'Bob' }
  ];

  processUsers() {
    // 従来のfor文
    for (let i = 0; i < this.users.length; i++) {
      console.log(`User ${i + 1}: ${this.users[i].name}`);
    }

    // for...of文
    for (const user of this.users) {
      console.log(`Processing user: ${user.name}`);
    }
  }
}
```

##### while文とdo-while文

```typescript
// while文
let count = 0;
while (count < 5) {
  console.log(count);
  count++;
}

// do-while文（最低1回は実行）
let num = 0;
do {
  console.log(num);
  num++;
} while (num < 3);

// 条件付きループ
let isLoading = true;
while (isLoading) {
  // データ読み込み処理
  isLoading = false;  // 条件を変更
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-retry-mechanism',
  template: `
    <div>
      Status: {{ status }}
      <button (click)="retryOperation()">Retry</button>
    </div>
  `
})
export class RetryMechanismComponent {
  private maxRetries = 3;
  private retryCount = 0;
  status = 'Ready';

  async retryOperation() {
    this.retryCount = 0;
    let success = false;

    while (this.retryCount < this.maxRetries && !success) {
      try {
        this.status = `Attempting operation (${this.retryCount + 1}/${this.maxRetries})`;
        await this.performOperation();
        success = true;
        this.status = 'Operation successful';
      } catch (error) {
        this.retryCount++;
        if (this.retryCount >= this.maxRetries) {
          this.status = 'Operation failed after max retries';
        }
      }
    }
  }

  private async performOperation(): Promise<void> {
    // 実際の非同期操作
    return new Promise((resolve, reject) => {
      // シミュレーション用のランダムな成功/失敗
      if (Math.random() > 0.5) {
        resolve();
      } else {
        reject(new Error('Operation failed'));
      }
    });
  }
}
```

##### break と continue

```typescript
// breakの使用例
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break;  // ループを完全に抜ける
  }
  console.log(i);  // 0, 1, 2, 3, 4
}

// continueの使用例
for (let i = 0; i < 5; i++) {
  if (i === 2) {
    continue;  // 現在の反復をスキップ
  }
  console.log(i);  // 0, 1, 3, 4
}

// ネストしたループでのbreak
outer: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    if (i === 1 && j === 1) {
      break outer;  // 外側のループも抜ける
    }
    console.log(`${i},${j}`);
  }
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-data-processor',
  template: `
    <div>
      Processed Items: {{ processedCount }}
      <button (click)="processData()">Process</button>
    </div>
  `
})
export class DataProcessorComponent {
  private data = [
    { id: 1, value: 'valid' },
    { id: 2, value: 'invalid' },
    { id: 3, value: 'valid' },
    { id: 4, value: 'error' },
    { id: 5, value: 'valid' }
  ];
  processedCount = 0;

  processData() {
    this.processedCount = 0;

    for (const item of this.data) {
      // エラーの場合は処理を完全に停止
      if (item.value === 'error') {
        console.error('Error encountered, stopping process');
        break;
      }

      // 無効なデータはスキップ
      if (item.value === 'invalid') {
        console.warn('Skipping invalid item');
        continue;
      }

      // 有効なデータの処理
      this.processItem(item);
      this.processedCount++;
    }
  }

  private processItem(item: any) {
    // アイテムの処理ロジック
    console.log(`Processing item ${item.id}`);
  }
}
```

### 2.3 関数

#### 2.3.1 関数の基本概念

##### 関数の定義と呼び出し

```typescript
// 基本的な関数定義
function greet(name: string): string {
  return `Hello, ${name}!`;
}

// 関数の呼び出し
console.log(greet('John'));  // "Hello, John!"

// 戻り値のない関数（void）
function logMessage(message: string): void {
  console.log(message);
}

// オプショナルパラメータ
function createUser(name: string, age?: number): object {
  return {
    name,
    age: age || null
  };
}

// デフォルトパラメータ
function configure(options: object = {}): void {
  console.log('Configuring with:', options);
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-greeting',
  template: `
    <div>
      <h1>{{ getGreeting() }}</h1>
      <button (click)="handleClick('Hello')">Click me</button>
    </div>
  `
})
export class GreetingComponent {
  userName = 'John';

  // テンプレートで使用する関数
  getGreeting(): string {
    return this.formatGreeting(this.userName);
  }

  // イベントハンドラ
  handleClick(message: string): void {
    this.showMessage(message);
  }

  // プライベート関数
  private formatGreeting(name: string): string {
    return `Welcome, ${name}!`;
  }

  private showMessage(message: string): void {
    console.log(message);
  }
}
```

#### 2.3.2 アロー関数

```typescript
// 基本的なアロー関数
const add = (a: number, b: number): number => a + b;

// 複数行の処理
const calculate = (x: number): number => {
  const multiplied = x * 2;
  const added = multiplied + 1;
  return added;
};

// コールバックでのアロー関数
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(n => n * 2);

// this のバインディング
class Traditional {
  value = 42;
  
  regularMethod() {
    setTimeout(function() {
      console.log(this.value);  // undefined
    }, 1000);
  }

  arrowMethod() {
    setTimeout(() => {
      console.log(this.value);  // 42
    }, 1000);
  }
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-list',
  template: `
    <ul>
      <li *ngFor="let user of filteredUsers">
        {{ user.name }}
      </li>
    </ul>
  `
})
export class UserListComponent implements OnInit {
  users: User[] = [];
  
  // アロー関数を使用したフィルター
  filterUsers = (status: string): User[] => 
    this.users.filter(user => user.status === status);

  // 計算プロパティ
  get filteredUsers(): User[] {
    return this.users.filter(user => !user.isDeleted);
  }

  // HTTPリクエストの処理
  fetchUsers(): Observable<User[]> {
    return this.http.get<User[]>('/api/users')
      .pipe(
        map(users => users.map(user => ({
          ...user,
          fullName: `${user.firstName} ${user.lastName}`
        }))),
        catchError(error => {
          console.error('Error fetching users:', error);
          return of([]);
        })
      );
  }

  ngOnInit(): void {
    // イベントリスナーでのアロー関数
    window.addEventListener('resize', () => {
      this.updateLayout();
    });
  }

  private updateLayout(): void {
    // レイアウトの更新処理
  }
}
```

#### 2.3.3 関数のパラメータ

##### パラメータの型定義

```typescript
// 基本的なパラメータ
function add(x: number, y: number): number {
  return x + y;
}

// オプショナルパラメータ
function createUser(name: string, age?: number, email?: string) {
  return {
    name,
    age: age ?? null,
    email: email ?? undefined
  };
}

// デフォルト値
function greet(name: string = 'Guest'): string {
  return `Hello, ${name}!`;
}

// レストパラメータ
function sum(...numbers: number[]): number {
  return numbers.reduce((total, n) => total + n, 0);
}

// オブジェクトパラメータ
interface Config {
  name: string;
  options?: {
    color?: string;
    size?: number;
  };
}

function initialize(config: Config): void {
  console.log(`Initializing ${config.name}`);
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-form',
  template: `
    <form (ngSubmit)="submitForm(userData)">
      <!-- フォームの内容 -->
    </form>
  `
})
export class UserFormComponent {
  // インターフェース定義
  interface UserData {
    name: string;
    email: string;
    preferences?: {
      newsletter?: boolean;
      theme?: string;
    };
  }

  // オブジェクトパラメータを使用するメソッド
  submitForm(data: UserData): void {
    this.validateAndSave(data);
  }

  // 複数のオプショナルパラメータ
  updateUser(
    id: number,
    name?: string,
    email?: string,
    preferences?: object
  ): Observable<User> {
    const updates = {
      ...(name && { name }),
      ...(email && { email }),
      ...(preferences && { preferences })
    };
    return this.userService.update(id, updates);
  }

  // レストパラメータの使用
  logActions(...actions: string[]): void {
    actions.forEach(action => {
      this.logger.log(`User action: ${action}`);
    });
  }

  // デフォルト値とオプショナルパラメータの組み合わせ
  configure(
    options: object = {},
    callback?: () => void
  ): void {
    this.applyConfiguration(options);
    if (callback) {
      callback();
    }
  }
}
```

#### 2.3.4 スコープとクロージャ

##### スコープの理解

```typescript
// グローバルスコープ
const globalVar = 'I am global';

function outer() {
  // 関数スコープ
  const outerVar = 'I am from outer';
  
  function inner() {
    // 内部関数のスコープ
    const innerVar = 'I am from inner';
    console.log(globalVar);    // アクセス可能
    console.log(outerVar);     // アクセス可能
    console.log(innerVar);     // アクセス可能
  }
  
  inner();
  // console.log(innerVar);    // エラー: innerVarは未定義
}

// console.log(outerVar);      // エラー: outerVarは未定義
```

##### クロージャの活用

```typescript
// カウンタークロージャ
function createCounter(initialValue: number = 0) {
  let count = initialValue;
  
  return {
    increment: () => ++count,
    decrement: () => --count,
    getCount: () => count
  };
}

const counter = createCounter(10);
console.log(counter.getCount());  // 10
counter.increment();
console.log(counter.getCount());  // 11

// プライベート変数の実現
function createWallet(initialBalance: number) {
  let balance = initialBalance;  // プライベート変数
  
  return {
    getBalance: () => balance,
    deposit: (amount: number) => {
      if (amount > 0) {
        balance += amount;
        return true;
      }
      return false;
    },
    withdraw: (amount: number) => {
      if (amount > 0 && amount <= balance) {
        balance -= amount;
        return true;
      }
      return false;
    }
  };
}
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class StateManagerService {
  private createState<T>(initialState: T) {
    let state = initialState;
    const subscribers = new Set<(state: T) => void>();

    return {
      getState: () => state,
      setState: (newState: T) => {
        state = newState;
        subscribers.forEach(subscriber => subscriber(state));
      },
      subscribe: (callback: (state: T) => void) => {
        subscribers.add(callback);
        return () => subscribers.delete(callback);
      }
    };
  }

  // 状態管理の実装例
  private userState = this.createState<User | null>(null);

  getUserState() {
    return this.userState.getState();
  }

  updateUser(user: User) {
    this.userState.setState(user);
  }

  subscribeToUser(callback: (user: User | null) => void) {
    return this.userState.subscribe(callback);
  }
}

@Component({
  selector: 'app-user-profile',
  template: `
    <div *ngIf="user$ | async as user">
      {{ user.name }}
    </div>
  `
})
export class UserProfileComponent implements OnInit, OnDestroy {
  private stateManager = inject(StateManagerService);
  private destroy$ = new Subject<void>();
  user$ = new BehaviorSubject<User | null>(null);

  ngOnInit() {
    // クロージャを使用したサブスクリプション管理
    const unsubscribe = this.stateManager.subscribeToUser(user => {
      this.user$.next(user);
    });

    // コンポーネントの破棄時にクリーンアップ
    this.destroy$.pipe(
      take(1)
    ).subscribe(() => {
      unsubscribe();
    });
  }

  ngOnDestroy() {
    this.destroy$.next();
    this.destroy$.complete();
  }
}
```

#### 2.3.5 コールバック関数

##### 基本的なコールバック

```typescript
// シンプルなコールバック
function fetchData(callback: (data: any) => void): void {
  // 非同期処理のシミュレーション
  setTimeout(() => {
    const data = { id: 1, name: 'John' };
    callback(data);
  }, 1000);
}

fetchData((data) => {
  console.log('Data received:', data);
});

// エラーハンドリング付きコールバック
function processData(
  data: any,
  onSuccess: (result: any) => void,
  onError: (error: Error) => void
): void {
  try {
    const result = data.value * 2;
    onSuccess(result);
  } catch (error) {
    onError(error as Error);
  }
}
```

##### イベントハンドリング

```typescript
// DOM イベントのハンドリング
document.addEventListener('click', (event) => {
  console.log('Clicked at:', event.clientX, event.clientY);
});

// カスタムイベントハンドラ
class EventEmitter {
  private listeners: { [key: string]: Function[] } = {};

  on(event: string, callback: Function): void {
    if (!this.listeners[event]) {
      this.listeners[event] = [];
    }
    this.listeners[event].push(callback);
  }

  emit(event: string, data?: any): void {
    if (this.listeners[event]) {
      this.listeners[event].forEach(callback => callback(data));
    }
  }
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-data-list',
  template: `
    <div>
      <button (click)="loadData()">Load Data</button>
      <ul>
        <li *ngFor="let item of items">
          {{ item.name }}
          <button (click)="handleItemClick(item)">Select</button>
        </li>
      </ul>
    </div>
  `
})
export class DataListComponent {
  items: any[] = [];
  @Output() itemSelected = new EventEmitter<any>();

  constructor(private dataService: DataService) {}

  // イベントハンドラ
  handleItemClick(item: any): void {
    this.itemSelected.emit(item);
  }

  // コールバックを使用したデータ取得
  loadData(): void {
    this.dataService.fetchData(
      // 成功時のコールバック
      (data: any[]) => {
        this.items = data;
        this.processItems();
      },
      // エラー時のコールバック
      (error: Error) => {
        console.error('Failed to load data:', error);
        this.handleError(error);
      }
    );
  }

  // 複数のコールバックを受け取るメソッド
  processItems(
    beforeProcess?: () => void,
    afterProcess?: () => void
  ): void {
    if (beforeProcess) beforeProcess();

    this.items.forEach(item => {
      item.processed = true;
    });

    if (afterProcess) afterProcess();
  }

  // RxJSを使用したコールバックの代替
  loadDataWithRxJS(): void {
    this.dataService.fetchData$().pipe(
      tap(data => this.items = data),
      catchError(error => {
        this.handleError(error);
        return EMPTY;
      })
    ).subscribe();
  }

  private handleError(error: Error): void {
    // エラー処理
  }
}

// サービスでのコールバック実装
@Injectable({
  providedIn: 'root'
})
export class DataService {
  fetchData(
    onSuccess: (data: any[]) => void,
    onError: (error: Error) => void
  ): void {
    this.http.get<any[]>('/api/data').subscribe({
      next: data => onSuccess(data),
      error: error => onError(error)
    });
  }

  // RxJSを使用した現代的な実装
  fetchData$(): Observable<any[]> {
    return this.http.get<any[]>('/api/data');
  }
}
```

### 2.4 オブジェクトと配列

#### 2.4.1 オブジェクトの基本

##### オブジェクトの作成と操作

```typescript
// オブジェクトリテラル
const user = {
  id: 1,
  name: 'John',
  age: 30,
  email: 'john@example.com'
};

// プロパティへのアクセス
console.log(user.name);      // ドット記法
console.log(user['email']);  // ブラケット記法

// プロパティの追加
user.address = 'Tokyo';
user['phone'] = '123-456-789';

// プロパティの削除
delete user.age;

// プロパティの存在確認
console.log('name' in user);              // true
console.log(user.hasOwnProperty('age'));  // false

// オブジェクトのマージ
const defaults = { theme: 'light', language: 'en' };
const userPreferences = { theme: 'dark' };
const settings = { ...defaults, ...userPreferences };
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-profile',
  template: `
    <div class="user-profile">
      <h2>{{ user.name }}</h2>
      <div *ngFor="let key of displayProperties">
        <strong>{{ key }}:</strong> {{ user[key] }}
      </div>
      <button (click)="updateUser(userUpdates)">Update</button>
    </div>
  `
})
export class UserProfileComponent {
  user = {
    id: 1,
    name: 'John Doe',
    email: 'john@example.com',
    role: 'user'
  };

  displayProperties = ['email', 'role'];

  userUpdates = {
    name: 'John Updated',
    role: 'admin'
  };

  updateUser(updates: Partial<typeof this.user>) {
    // オブジェクトのマージ
    this.user = { ...this.user, ...updates };
  }

  // オブジェクトの動的なプロパティアクセス
  getProperty(key: keyof typeof this.user) {
    return this.user[key];
  }
}
```

##### オブジェクトのメソッド

```typescript
// メソッドを持つオブジェクト
const calculator = {
  value: 0,
  add(n: number): void {
    this.value += n;
  },
  subtract(n: number): void {
    this.value -= n;
  },
  getValue(): number {
    return this.value;
  }
};

// メソッドチェーン
const builder = {
  value: '',
  append(str: string) {
    this.value += str;
    return this;
  },
  prepend(str: string) {
    this.value = str + this.value;
    return this;
  },
  toString() {
    return this.value;
  }
};

builder.append('World').prepend('Hello ').append('!');
console.log(builder.toString());  // "Hello World!"
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class UserService {
  private user = {
    data: {
      name: '',
      preferences: {}
    },
    
    // メソッド
    setName(name: string) {
      this.data.name = name;
      return this;  // メソッドチェーン用
    },
    
    setPreference(key: string, value: any) {
      this.data.preferences[key] = value;
      return this;  // メソッドチェーン用
    },
    
    getData() {
      return { ...this.data };  // イミュータブルな複製を返す
    }
  };

  // サービスメソッド
  updateUser() {
    this.user
      .setName('John')
      .setPreference('theme', 'dark')
      .setPreference('notifications', true);
      
    return this.user.getData();
  }
}
```

#### 2.4.2 配列の基本

##### 配列の作成と操作

```typescript
// 配列の作成
const numbers = [1, 2, 3, 4, 5];
const fruits = ['apple', 'banana', 'orange'];
const mixed: (number | string)[] = [1, 'two', 3, 'four'];

// 配列の要素へのアクセス
console.log(numbers[0]);     // 1
console.log(fruits[1]);      // 'banana'
console.log(numbers[10]);    // undefined

// 配列の長さ
console.log(numbers.length); // 5

// 配列の末尾に追加
numbers.push(6);

// 配列の先頭に追加
numbers.unshift(0);

// 配列の末尾から削除
const last = numbers.pop();

// 配列の先頭から削除
const first = numbers.shift();

// 配列の一部を取得
const slice = numbers.slice(1, 4);  // インデックス1から3まで

// 配列の一部を削除/置換
numbers.splice(1, 2);  // インデックス1から2つの要素を削除
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-todo-list',
  template: `
    <div class="todo-list">
      <div *ngFor="let todo of todos; let i = index">
        {{ i + 1 }}. {{ todo.title }}
        <button (click)="removeTodo(i)">Delete</button>
      </div>
      <button (click)="addTodo('New Task')">Add Task</button>
    </div>
  `
})
export class TodoListComponent {
  todos: Todo[] = [
    { id: 1, title: 'Learn Angular', completed: false },
    { id: 2, title: 'Create App', completed: false }
  ];

  addTodo(title: string) {
    const newTodo = {
      id: this.todos.length + 1,
      title,
      completed: false
    };
    this.todos.push(newTodo);
  }

  removeTodo(index: number) {
    this.todos.splice(index, 1);
  }

  // 配列の操作メソッドの例
  getActiveTodos(): Todo[] {
    return this.todos.filter(todo => !todo.completed);
  }

  getCompletedTodos(): Todo[] {
    return this.todos.filter(todo => todo.completed);
  }
}
```

##### 配列のメソッド

```typescript
// map: 各要素を変換
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(n => n * 2);  // [2, 4, 6, 8, 10]

// filter: 条件に合う要素を抽出
const evens = numbers.filter(n => n % 2 === 0);  // [2, 4]

// reduce: 要素を集約
const sum = numbers.reduce((acc, n) => acc + n, 0);  // 15

// find: 条件に合う最初の要素を検索
const found = numbers.find(n => n > 3);  // 4

// some: 条件に合う要素が存在するか確認
const hasEven = numbers.some(n => n % 2 === 0);  // true

// every: すべての要素が条件を満たすか確認
const allPositive = numbers.every(n => n > 0);  // true

// includes: 要素が含まれているか確認
const hasThree = numbers.includes(3);  // true

// join: 配列を文字列に結合
const joined = numbers.join(', ');  // "1, 2, 3, 4, 5"
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-list',
  template: `
    <div class="user-list">
      <div class="filters">
        <button (click)="filterByRole('admin')">Admins</button>
        <button (click)="filterByRole('user')">Users</button>
      </div>
      <div *ngFor="let user of filteredUsers">
        {{ user.name }} ({{ user.role }})
      </div>
      <div class="summary">
        <p>Total Users: {{ getTotalUsers() }}</p>
        <p>Active Users: {{ getActiveUsersCount() }}</p>
      </div>
    </div>
  `
})
export class UserListComponent implements OnInit {
  users: User[] = [];
  filteredUsers: User[] = [];

  ngOnInit() {
    this.loadUsers();
  }

  // 配列メソッドを使用したデータ処理
  filterByRole(role: string) {
    this.filteredUsers = this.users.filter(user => user.role === role);
  }

  getTotalUsers(): number {
    return this.users.length;
  }

  getActiveUsersCount(): number {
    return this.users.filter(user => user.isActive).length;
  }

  getUserNames(): string {
    return this.users
      .map(user => user.name)
      .join(', ');
  }

  // 複雑なデータ処理
  getUserStatistics() {
    return this.users.reduce((stats, user) => {
      stats[user.role] = (stats[user.role] || 0) + 1;
      return stats;
    }, {} as Record<string, number>);
  }

  // 検索機能
  searchUsers(query: string): User[] {
    return this.users.filter(user =>
      user.name.toLowerCase().includes(query.toLowerCase()) ||
      user.email.toLowerCase().includes(query.toLowerCase())
    );
  }

  // ソート機能
  sortUsersByName(ascending: boolean = true) {
    this.filteredUsers.sort((a, b) => {
      const comparison = a.name.localeCompare(b.name);
      return ascending ? comparison : -comparison;
    });
  }
}

// サービスでの配列操作
@Injectable({
  providedIn: 'root'
})
export class UserService {
  private users: User[] = [];

  addUser(user: User) {
    // 重複チェック
    if (!this.users.some(u => u.id === user.id)) {
      this.users.push(user);
    }
  }

  removeUser(id: number) {
    const index = this.users.findIndex(user => user.id === id);
    if (index !== -1) {
      this.users.splice(index, 1);
    }
  }

  updateUser(updatedUser: User) {
    const index = this.users.findIndex(user => user.id === updatedUser.id);
    if (index !== -1) {
      // イミュータブルな更新
      this.users = [
        ...this.users.slice(0, index),
        updatedUser,
        ...this.users.slice(index + 1)
      ];
    }
  }

  // バッチ処理
  processBatch(userBatch: User[]) {
    const results = userBatch.map(user => {
      try {
        this.validateUser(user);
        return { user, success: true };
      } catch (error) {
        return { user, success: false, error };
      }
    });

    const successfulUsers = results
      .filter(result => result.success)
      .map(result => result.user);

    return {
      successful: successfulUsers,
      failed: results.filter(result => !result.success)
    };
  }
}
```

#### 2.4.3 分割代入とスプレッド構文

##### 分割代入

```typescript
// オブジェクトの分割代入
const user = {
  name: 'John',
  age: 30,
  address: {
    city: 'Tokyo',
    country: 'Japan'
  }
};

const { name, age } = user;
const { city, country } = user.address;

// デフォルト値
const { role = 'user' } = user;

// 変数名の変更
const { name: userName } = user;

// 配列の分割代入
const numbers = [1, 2, 3, 4, 5];
const [first, second, ...rest] = numbers;

// 値の交換
let a = 1;
let b = 2;
[a, b] = [b, a];
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-user-card',
  template: `
    <div class="user-card">
      <h2>{{ name }}</h2>
      <p>Age: {{ age }}</p>
      <p>Location: {{ city }}, {{ country }}</p>
    </div>
  `
})
export class UserCardComponent implements OnInit {
  @Input() user!: User;
  
  // コンポーネントのプロパティ
  name!: string;
  age!: number;
  city!: string;
  country!: string;

  ngOnInit() {
    // オブジェクトの分割代入
    const { name, age, address: { city, country } } = this.user;
    
    // プロパティに代入
    this.name = name;
    this.age = age;
    this.city = city;
    this.country = country;
  }

  // メソッドパラメータでの分割代入
  updateUser({ name, age }: Partial<User>) {
    if (name) this.name = name;
    if (age) this.age = age;
  }
}

// サービスでの使用例
@Injectable({
  providedIn: 'root'
})
export class DataService {
  processUserData(response: ApiResponse) {
    // レスポンスの分割代入
    const { data: { users }, metadata } = response;
    
    // 配列の処理
    return users.map(({ id, name, email }) => ({
      id,
      name,
      email,
      isProcessed: true
    }));
  }
}
```

##### スプレッド構文

```typescript
// 配列のスプレッド
const numbers = [1, 2, 3];
const moreNumbers = [...numbers, 4, 5];  // [1, 2, 3, 4, 5]

// 配列の結合
const array1 = [1, 2];
const array2 = [3, 4];
const combined = [...array1, ...array2];  // [1, 2, 3, 4]

// オブジェクトのスプレッド
const baseObject = { id: 1, name: 'John' };
const extendedObject = {
  ...baseObject,
  age: 30,
  name: 'John Doe'  // プロパティの上書き
};

// 関数の引数
function sum(...numbers: number[]): number {
  return numbers.reduce((total, n) => total + n, 0);
}
```

Angularでの使用例：
```typescript
@Component({
  selector: 'app-form',
  template: `
    <form (ngSubmit)="submitForm()">
      <input [(ngModel)]="formData.name" name="name">
      <input [(ngModel)]="formData.email" name="email">
      <button type="submit">Submit</button>
    </form>
  `
})
export class FormComponent {
  // 初期状態
  private initialState = {
    name: '',
    email: '',
    timestamp: new Date()
  };

  // フォームデータ
  formData = { ...this.initialState };

  // フォームのリセット
  resetForm() {
    this.formData = { ...this.initialState };
  }

  // フォームの送信
  submitForm() {
    const submitData = {
      ...this.formData,
      timestamp: new Date()
    };
    this.saveData(submitData);
  }

  // 部分的な更新
  updateForm(updates: Partial<typeof this.formData>) {
    this.formData = {
      ...this.formData,
      ...updates
    };
  }
}

// ステート管理での使用例
@Injectable({
  providedIn: 'root'
})
export class StateService {
  private state = {
    users: [],
    settings: {},
    metadata: {}
  };

  // イミュータブルな状態更新
  updateUsers(newUsers: User[]) {
    this.state = {
      ...this.state,
      users: [...newUsers]
    };
  }

  // ネストされた状態の更新
  updateSettings(path: string[], value: any) {
    const settings = { ...this.state.settings };
    let current = settings;
    
    path.slice(0, -1).forEach(key => {
      current[key] = { ...current[key] };
      current = current[key];
    });
    
    current[path[path.length - 1]] = value;
    
    this.state = {
      ...this.state,
      settings
    };
  }
}
```

### 2.5 非同期処理

#### 2.5.1 Promise

##### Promiseの基本

```typescript
// Promise の作成
const promise = new Promise<string>((resolve, reject) => {
  // 非同期処理
  setTimeout(() => {
    const success = true;
    if (success) {
      resolve('Operation completed');
    } else {
      reject(new Error('Operation failed'));
    }
  }, 1000);
});

// Promise の使用
promise
  .then(result => {
    console.log('Success:', result);
  })
  .catch(error => {
    console.error('Error:', error);
  })
  .finally(() => {
    console.log('Cleanup');
  });

// Promise チェーン
function fetchUserData(userId: number): Promise<User> {
  return fetch(`/api/users/${userId}`)
    .then(response => {
      if (!response.ok) {
        throw new Error('User not found');
      }
      return response.json();
    })
    .then(user => {
      return processUserData(user);
    });
}

// 複数のPromiseを扱う
const promise1 = Promise.resolve(1);
const promise2 = Promise.resolve(2);
const promise3 = Promise.resolve(3);

// すべてのPromiseが完了するのを待つ
Promise.all([promise1, promise2, promise3])
  .then(values => {
    console.log(values);  // [1, 2, 3]
  });

// 最初に完了したPromiseを取得
Promise.race([promise1, promise2, promise3])
  .then(value => {
    console.log('First completed:', value);
  });
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class DataService {
  // Promise を返すメソッド
  fetchData(): Promise<any> {
    return fetch('/api/data')
      .then(response => response.json())
      .then(data => this.processData(data))
      .catch(error => {
        console.error('Error fetching data:', error);
        return Promise.reject(error);
      });
  }

  // 複数の非同期処理を順次実行
  async initializeApp(): Promise<void> {
    try {
      const config = await this.loadConfig();
      const user = await this.authenticateUser(config);
      const data = await this.loadUserData(user);
      
      return this.setupApplication(data);
    } catch (error) {
      this.handleError(error);
      return Promise.reject(error);
    }
  }

  // 並列実行
  loadAllData(): Promise<[Config, User, Settings]> {
    return Promise.all([
      this.loadConfig(),
      this.loadUser(),
      this.loadSettings()
    ]);
  }
}

@Component({
  selector: 'app-data-display',
  template: `
    <div *ngIf="!loading">
      <div *ngIf="data">{{ data | json }}</div>
      <div *ngIf="error" class="error">{{ error }}</div>
    </div>
    <div *ngIf="loading">Loading...</div>
  `
})
export class DataDisplayComponent implements OnInit {
  data: any = null;
  error: string = '';
  loading = false;

  constructor(private dataService: DataService) {}

  async ngOnInit() {
    this.loading = true;
    try {
      this.data = await this.dataService.fetchData();
    } catch (error) {
      this.error = error.message;
    } finally {
      this.loading = false;
    }
  }
}
```

#### 2.5.2 async/await

##### 基本的な使い方

```typescript
// async 関数の定義
async function fetchUser(id: number): Promise<User> {
  try {
    const response = await fetch(`/api/users/${id}`);
    if (!response.ok) {
      throw new Error('User not found');
    }
    const user = await response.json();
    return user;
  } catch (error) {
    console.error('Error fetching user:', error);
    throw error;
  }
}

// 並列処理
async function fetchMultipleUsers(ids: number[]): Promise<User[]> {
  // Promise.all と組み合わせて並列実行
  const promises = ids.map(id => fetchUser(id));
  const users = await Promise.all(promises);
  return users;
}

// エラーハンドリング
async function safeOperation(): Promise<void> {
  try {
    await riskyOperation();
    await anotherRiskyOperation();
  } catch (error) {
    // エラー処理
    handleError(error);
  } finally {
    // クリーンアップ
    cleanup();
  }
}
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class UserService {
  constructor(private http: HttpClient) {}

  // HTTP リクエストの処理
  async getUser(id: number): Promise<User> {
    try {
      const user = await this.http.get<User>(`/api/users/${id}`).toPromise();
      return this.enrichUserData(user);
    } catch (error) {
      this.logError('Failed to fetch user', error);
      throw error;
    }
  }

  // 複数の非同期操作
  async updateUserProfile(userId: number, data: Partial<User>): Promise<User> {
    try {
      // 現在のユーザーデータを取得
      const currentUser = await this.getUser(userId);
      
      // バリデーション
      await this.validateUserData(data);
      
      // 更新を実行
      const updatedUser = await this.http
        .put<User>(`/api/users/${userId}`, { ...currentUser, ...data })
        .toPromise();
      
      // キャッシュを更新
      await this.updateCache(updatedUser);
      
      return updatedUser;
    } catch (error) {
      this.handleUpdateError(error);
      throw error;
    }
  }
}

@Component({
  selector: 'app-user-profile',
  template: `
    <div *ngIf="user$ | async as user; else loading">
      <form [formGroup]="profileForm" (ngSubmit)="onSubmit()">
        <input formControlName="name">
        <input formControlName="email">
        <button type="submit" [disabled]="saving">Save</button>
      </form>
    </div>
    <ng-template #loading>Loading...</ng-template>
  `
})
export class UserProfileComponent implements OnInit {
  profileForm: FormGroup;
  user$ = new BehaviorSubject<User | null>(null);
  saving = false;

  constructor(
    private userService: UserService,
    private fb: FormBuilder
  ) {
    this.profileForm = this.fb.group({
      name: [''],
      email: ['']
    });
  }

  async ngOnInit() {
    try {
      const user = await this.userService.getUser(1);
      this.user$.next(user);
      this.profileForm.patchValue(user);
    } catch (error) {
      this.handleError(error);
    }
  }

  async onSubmit() {
    if (this.profileForm.invalid) return;

    this.saving = true;
    try {
      const updates = this.profileForm.value;
      const updatedUser = await this.userService.updateUserProfile(1, updates);
      this.user$.next(updatedUser);
      this.showSuccess('Profile updated successfully');
    } catch (error) {
      this.showError('Failed to update profile');
    } finally {
      this.saving = false;
    }
  }
}
```

#### 2.5.3 Observable

##### Observableの基本

```typescript
import { Observable, of, from, interval } from 'rxjs';
import { map, filter, tap, catchError } from 'rxjs/operators';

// Observable の作成
const numbers$ = of(1, 2, 3, 4, 5);
const array$ = from([1, 2, 3, 4, 5]);
const interval$ = interval(1000);  // 1秒ごとに値を発行

// 基本的な購読
numbers$.subscribe({
  next: value => console.log(value),
  error: error => console.error(error),
  complete: () => console.log('Complete')
});

// パイプラインの作成
const transformed$ = numbers$.pipe(
  map(n => n * 2),
  filter(n => n > 5),
  tap(n => console.log('Value:', n))
);

// エラーハンドリング
const safe$ = numbers$.pipe(
  map(n => {
    if (n === 0) throw new Error('Zero!');
    return 10 / n;
  }),
  catchError(error => {
    console.error('Error caught:', error);
    return of(0);  // フォールバック値
  })
);
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class DataService {
  private refreshSubject = new BehaviorSubject<void>(undefined);
  private dataCache = new Map<string, any>();

  // データの取得と自動リフレッシュ
  getData(id: string): Observable<any> {
    return this.refreshSubject.pipe(
      // リフレッシュトリガーごとにデータを再取得
      switchMap(() => {
        // キャッシュチェック
        const cached = this.dataCache.get(id);
        if (cached) {
          return of(cached);
        }

        // APIリクエスト
        return this.http.get<any>(`/api/data/${id}`).pipe(
          tap(data => this.dataCache.set(id, data)),
          catchError(error => {
            console.error('Error fetching data:', error);
            return of(null);
          })
        );
      })
    );
  }

  // 手動リフレッシュ
  refresh(): void {
    this.refreshSubject.next();
  }
}

@Component({
  selector: 'app-data-viewer',
  template: `
    <div class="data-viewer">
      <div *ngIf="data$ | async as data; else loading">
        {{ data | json }}
      </div>
      <ng-template #loading>
        <app-spinner></app-spinner>
      </ng-template>
      
      <div class="error" *ngIf="error$ | async as error">
        {{ error }}
      </div>
      
      <button (click)="refresh()">Refresh</button>
    </div>
  `
})
export class DataViewerComponent implements OnInit, OnDestroy {
  private destroy$ = new Subject<void>();
  private errorSubject = new BehaviorSubject<string>('');
  
  data$: Observable<any>;
  error$ = this.errorSubject.asObservable();

  constructor(private dataService: DataService) {
    // データストリームの設定
    this.data$ = this.dataService.getData('123').pipe(
      // エラーハンドリング
      catchError(error => {
        this.errorSubject.next(error.message);
        return EMPTY;
      }),
      // コンポーネントの破棄時に購読を解除
      takeUntil(this.destroy$)
    );
  }

  ngOnInit() {
    // 自動更新の設定
    interval(30000).pipe(
      takeUntil(this.destroy$)
    ).subscribe(() => {
      this.refresh();
    });
  }

  refresh() {
    this.dataService.refresh();
  }

  ngOnDestroy() {
    this.destroy$.next();
    this.destroy$.complete();
  }
}

// 複雑なデータフローの例
@Component({
  selector: 'app-search',
  template: `
    <input [formControl]="searchControl">
    <div *ngFor="let result of results$ | async">
      {{ result.name }}
    </div>
  `
})
export class SearchComponent implements OnInit {
  searchControl = new FormControl('');
  results$: Observable<SearchResult[]>;

  constructor(private searchService: SearchService) {
    // 検索ロジックの実装
    this.results$ = this.searchControl.valueChanges.pipe(
      // 入力値の正規化
      map(term => term.trim()),
      // 短すぎる検索語をスキップ
      filter(term => term.length > 2),
      // タイピング中のリクエストを防ぐ
      debounceTime(300),
      // 同じ値での重複リクエストを防ぐ
      distinctUntilChanged(),
      // 新しい検索語が入力されたら前のリクエストをキャンセル
      switchMap(term => this.searchService.search(term).pipe(
        // エラーハンドリング
        catchError(error => {
          console.error('Search error:', error);
          return of([]);
        })
      )),
      // 結果をキャッシュ
      shareReplay(1)
    );
  }
}

// 状態管理の例
@Injectable({
  providedIn: 'root'
})
export class StateService {
  private state = new BehaviorSubject<AppState>({
    user: null,
    settings: {},
    data: []
  });

  // 状態の監視
  select<T>(selector: (state: AppState) => T): Observable<T> {
    return this.state.pipe(
      map(selector),
      distinctUntilChanged()
    );
  }

  // 状態の更新
  update(updateFn: (state: AppState) => AppState) {
    const currentState = this.state.value;
    const newState = updateFn(currentState);
    this.state.next(newState);
  }

  // 特定の状態の監視
  selectUser() {
    return this.select(state => state.user);
  }

  selectSettings() {
    return this.select(state => state.settings);
  }

  // 状態の更新例
  updateUser(user: User) {
    this.update(state => ({
      ...state,
      user
    }));
  }
}
```

### 2.6 エラーハンドリングとデバッグ

#### 2.6.1 基本的なエラーハンドリング

##### try-catch文

```typescript
// 基本的なtry-catch
try {
  // エラーが発生する可能性のあるコード
  const result = someRiskyOperation();
  processResult(result);
} catch (error) {
  // エラーハンドリング
  console.error('エラーが発生しました:', error);
  // エラーの種類に応じた処理
  if (error instanceof TypeError) {
    handleTypeError(error);
  } else if (error instanceof NetworkError) {
    handleNetworkError(error);
  } else {
    handleGenericError(error);
  }
} finally {
  // 必ず実行される処理
  cleanup();
}

// カスタムエラー
class ValidationError extends Error {
  constructor(message: string) {
    super(message);
    this.name = 'ValidationError';
  }
}

// エラーのスロー
function validateUser(user: User) {
  if (!user.name) {
    throw new ValidationError('名前は必須です');
  }
  if (user.age < 0) {
    throw new ValidationError('年齢は0以上である必要があります');
  }
}
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class ErrorHandlingService {
  // グローバルエラーハンドラー
  handleError(error: any): void {
    if (error instanceof HttpErrorResponse) {
      this.handleHttpError(error);
    } else if (error instanceof ValidationError) {
      this.handleValidationError(error);
    } else {
      this.handleGenericError(error);
    }
  }

  private handleHttpError(error: HttpErrorResponse): void {
    switch (error.status) {
      case 401:
        this.handleUnauthorized();
        break;
      case 403:
        this.handleForbidden();
        break;
      case 404:
        this.handleNotFound();
        break;
      case 500:
        this.handleServerError();
        break;
      default:
        this.handleGenericError(error);
    }
  }

  private handleValidationError(error: ValidationError): void {
    this.notificationService.showError(error.message);
  }

  private handleGenericError(error: any): void {
    console.error('予期せぬエラーが発生しました:', error);
    this.notificationService.showError('システムエラーが発生しました');
  }
}

@Component({
  selector: 'app-user-form',
  template: `
    <form [formGroup]="userForm" (ngSubmit)="onSubmit()">
      <input formControlName="name" placeholder="名前">
      <input formControlName="age" type="number" placeholder="年齢">
      <button type="submit">保存</button>
      
      <div *ngIf="error" class="error-message">
        {{ error }}
      </div>
    </form>
  `
})
export class UserFormComponent {
  userForm: FormGroup;
  error: string = '';

  constructor(
    private fb: FormBuilder,
    private userService: UserService,
    private errorHandler: ErrorHandlingService
  ) {
    this.userForm = this.fb.group({
      name: ['', Validators.required],
      age: [null, [Validators.required, Validators.min(0)]]
    });
  }

  async onSubmit() {
    if (this.userForm.invalid) {
      this.error = '入力内容を確認してください';
      return;
    }

    try {
      const userData = this.userForm.value;
      // バリデーション
      validateUser(userData);
      
      // データ保存
      await this.userService.saveUser(userData);
      this.notificationService.showSuccess('保存しました');
      
    } catch (error) {
      if (error instanceof ValidationError) {
        this.error = error.message;
      } else {
        this.errorHandler.handleError(error);
      }
    }
  }
}
```

#### 2.6.2 非同期エラーハンドリング

##### Promiseのエラーハンドリング

```typescript
// Promise チェーンでのエラーハンドリング
fetchData()
  .then(data => processData(data))
  .then(result => saveResult(result))
  .catch(error => {
    console.error('エラーが発生しました:', error);
    return fallbackData;  // フォールバック値を返す
  })
  .finally(() => {
    cleanup();
  });

// async/await でのエラーハンドリング
async function processUserData() {
  try {
    const data = await fetchData();
    const processed = await processData(data);
    return await saveResult(processed);
  } catch (error) {
    console.error('データ処理中にエラーが発生しました:', error);
    return fallbackData;
  } finally {
    await cleanup();
  }
}
```

##### Observableのエラーハンドリング

```typescript
// RxJSのエラーハンドリング
const data$ = this.http.get('/api/data').pipe(
  // エラーを変換
  map(response => {
    if (!response.success) {
      throw new Error('Invalid response');
    }
    return response.data;
  }),
  // エラーを処理
  catchError(error => {
    console.error('APIエラー:', error);
    return of(null);  // フォールバック値
  }),
  // 再試行
  retry(3),
  // 完了処理
  finalize(() => {
    console.log('処理完了');
  })
);
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class DataService {
  constructor(
    private http: HttpClient,
    private errorHandler: ErrorHandlingService
  ) {}

  // HTTP リクエストのエラーハンドリング
  getData(): Observable<any> {
    return this.http.get('/api/data').pipe(
      // レスポンスの検証
      map(response => {
        if (!this.isValidResponse(response)) {
          throw new ValidationError('Invalid response format');
        }
        return response;
      }),
      // エラー変換
      catchError(error => {
        if (error instanceof HttpErrorResponse) {
          // HTTPエラーの処理
          return this.handleHttpError(error);
        }
        // その他のエラー
        return this.handleGenericError(error);
      }),
      // 再試行ロジック
      retryWhen(errors => 
        errors.pipe(
          // エラーの種類を確認
          mergeMap(error => {
            if (error.status === 503) {
              // サービス一時停止の場合は再試行
              return timer(1000);  // 1秒待機
            }
            // その他のエラーは即座に失敗
            return throwError(error);
          }),
          // 最大3回まで再試行
          take(3)
        )
      )
    );
  }

  // 複数の非同期処理のエラーハンドリング
  processMultipleRequests(): Observable<any[]> {
    const requests = [
      this.getData(),
      this.getConfig(),
      this.getUserProfile()
    ];

    return forkJoin(requests).pipe(
      // すべての結果を処理
      map(results => {
        return results.map(this.validateResult);
      }),
      // エラーハンドリング
      catchError(error => {
        this.errorHandler.handleError(error);
        return of([]);  // フォールバック
      })
    );
  }
}

@Component({
  selector: 'app-data-display',
  template: `
    <ng-container *ngIf="data$ | async as data; else loading">
      <div *ngIf="!error; else errorTpl">
        {{ data | json }}
      </div>
    </ng-container>

    <ng-template #loading>
      <app-spinner></app-spinner>
    </ng-template>

    <ng-template #errorTpl>
      <div class="error-container">
        <p>{{ error }}</p>
        <button (click)="retry()">再試行</button>
      </div>
    </ng-template>
  `
})
export class DataDisplayComponent implements OnInit {
  data$: Observable<any>;
  error: string = '';

  constructor(private dataService: DataService) {
    this.setupDataStream();
  }

  private setupDataStream() {
    this.data$ = this.dataService.getData().pipe(
      // エラー処理
      catchError(error => {
        this.error = this.getErrorMessage(error);
        return EMPTY;
      }),
      // 自動再接続
      retryWhen(errors => 
        errors.pipe(
          // エラーごとに待機時間を増やす
          scan((retryCount, error) => {
            if (retryCount >= 3) {
              throw error;
            }
            return retryCount + 1;
          }, 0),
          // 待機時間を計算
          mergeMap(retryCount => {
            const waitTime = Math.pow(2, retryCount) * 1000;
            return timer(waitTime);
          })
        )
      )
    );
  }

  retry() {
    this.error = '';
    this.setupDataStream();
  }

  private getErrorMessage(error: any): string {
    if (error instanceof HttpErrorResponse) {
      switch (error.status) {
        case 404:
          return 'データが見つかりません';
        case 403:
          return 'アクセスが拒否されました';
        case 500:
          return 'サーバーエラーが発生しました';
        default:
          return `エラーが発生しました (${error.status})`;
      }
    }
    return 'システムエラーが発生しました';
  }
}
```

#### 2.6.3 デバッグ技術

##### console メソッド

```typescript
// 基本的なログ出力
console.log('通常のログ');
console.info('情報ログ');
console.warn('警告ログ');
console.error('エラーログ');

// オブジェクトの詳細表示
console.dir(object, { depth: null, colors: true });

// テーブル形式での表示
console.table([
  { id: 1, name: 'John' },
  { id: 2, name: 'Jane' }
]);

// グループ化
console.group('ユーザー処理');
console.log('ユーザーデータを取得中...');
console.log('ユーザーデータを処理中...');
console.groupEnd();

// パフォーマンス計測
console.time('処理時間');
someOperation();
console.timeEnd('処理時間');

// スタックトレース
console.trace('スタックトレースを表示');
```

##### デバッガーの使用

```typescript
// デバッガーステートメント
function complexCalculation(data: any) {
  debugger;  // ここで実行が一時停止
  // 処理内容
}

// 条件付きブレークポイント
function processUsers(users: User[]) {
  users.forEach(user => {
    if (user.id === 123) {
      debugger;  // 特定のユーザーの時のみ停止
    }
    // 処理内容
  });
}
```

Angularでの使用例：
```typescript
@Injectable({
  providedIn: 'root'
})
export class DebugService {
  private isDebugMode = environment.debug;
  private logHistory: any[] = [];

  log(message: string, data?: any) {
    if (this.isDebugMode) {
      console.log(`[DEBUG] ${message}`, data);
      this.logHistory.push({
        timestamp: new Date(),
        message,
        data
      });
    }
  }

  error(message: string, error: any) {
    console.error(`[ERROR] ${message}`, error);
    if (this.isDebugMode) {
      console.trace('エラー発生箇所:');
    }
  }

  getLogHistory() {
    return [...this.logHistory];
  }
}

@Component({
  selector: 'app-debug-example',
  template: `
    <div *ngIf="debugMode">
      <h3>デバッグ情報</h3>
      <pre>{{ debugInfo | json }}</pre>
    </div>
  `
})
export class DebugExampleComponent implements OnInit {
  debugMode = environment.debug;
  debugInfo: any = {};

  constructor(
    private debugService: DebugService,
    private zone: NgZone
  ) {}

  ngOnInit() {
    this.setupDebugging();
  }

  private setupDebugging() {
    if (this.debugMode) {
      // コンポーネントの状態を監視
      this.zone.onUnstable.subscribe(() => {
        this.debugService.log('変更検知開始');
      });

      this.zone.onStable.subscribe(() => {
        this.debugService.log('変更検知完了');
      });

      // パフォーマンス監視
      this.monitorPerformance();
    }
  }

  private monitorPerformance() {
    const startTime = performance.now();
    
    // 重い処理の前後でマーク
    performance.mark('startProcess');
    this.heavyOperation();
    performance.mark('endProcess');

    // 処理時間の計測
    performance.measure(
      'processTime',
      'startProcess',
      'endProcess'
    );

    const endTime = performance.now();
    this.debugService.log(
      '処理時間',
      `${endTime - startTime}ms`
    );
  }

  private heavyOperation() {
    console.time('heavyOperation');
    // 重い処理
    console.timeEnd('heavyOperation');
  }
}

// デバッグ用のHTTPインターセプター
@Injectable()
export class DebugHttpInterceptor implements HttpInterceptor {
  constructor(private debugService: DebugService) {}

  intercept(
    req: HttpRequest<any>,
    next: HttpHandler
  ): Observable<HttpEvent<any>> {
    const startTime = Date.now();
    this.debugService.log(`HTTP ${req.method} ${req.url}開始`);

    return next.handle(req).pipe(
      tap({
        next: (event) => {
          if (event instanceof HttpResponse) {
            const endTime = Date.now();
            this.debugService.log(
              `HTTP ${req.method} ${req.url}完了`,
              {
                duration: endTime - startTime,
                status: event.status,
                body: event.body
              }
            );
          }
        },
        error: (error) => {
          const endTime = Date.now();
          this.debugService.error(
            `HTTP ${req.method} ${req.url}エラー`,
            {
              duration: endTime - startTime,
              error
            }
          );
        }
      })
    );
  }
}
```

[... 続く ...] 