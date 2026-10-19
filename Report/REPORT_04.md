# 第4回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## `const`と`let`の宣言・再代入に使用したコード
```
const courseName = "Web Engineering"
let retryCount = 1

courseName = "foo"

retryCount = 2

console.log(`これはテンプレートリテラルです。${courseName}、${retryCount}`)
```
## VSCodeと`pnpm run check`に表示されたエラー番号・メッセージ
```
@4724214 ➜ /workspaces/web-eng-typescript (main) $ pnpm run check
$ tsc --noEmit
src/index.ts:22:1 - error TS2588: Cannot assign to 'courseName' because it is a constant.

22 courseName = "foo"
   ~~~~~~~~~~


Found 1 error in src/index.ts:22

[ELIFECYCLE] Command failed with exit code 2.
```
## 修正後の実行結果と`const`・`let`の違いの説明
```
const courseName = "Web Engineering"
let retryCount = 1

// courseName = "foo"

retryCount = 2

console.log(`これはテンプレートリテラルです。${courseName}、${retryCount}`)
```

```
@4724214 ➜ /workspaces/web-eng-typescript (main) $ pnpm run check
$ tsc --noEmit
@4724214 ➜ /workspaces/web-eng-typescript (main) $ pnpm run start
$ tsx src/index.ts
これはテンプレートリテラルです。Web Engineering、2
```

constとletの違いは、constは再代入不可（定数）でletは再代入可能
