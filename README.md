## 概要
JavaScriptの静的解析ツール。エラーの種類によっては自動修正機能もある。
チェックルールはひとつずつ設定もできるし、プリセットで一括設定もできる。

## 導入
```
yarn add -D eslint
```

## 初期化
```
npx eslint --init
```
設定ファイル（.eslintrc.js）が生成される。

## .eslintrc.js
```
module.exports = {
  "extends": "eslint:recommended",  // プリセットを継承
  "parser": "@typescript-eslint/parser",  // パーサはデフォルトで"Espree"。他のパーサを使用したい場合に指定。
  "parserOptions": {
    "ecmaVersion": 11, // 使用したいECMAScriptのバージョン
    "sourceType": "module",  // "script" or "module"
    "ecmaFeatures": {  // その他追加で使用したい言語機能
      "jsx": true
    }
  },
  "plugins": [],  // プラグインを指定。プラグインで定義されたプリセットを利用できる。"eslint-plugin-"の接頭辞は省略可。
  "processor": "",  // リントの前処理を行えるプロセッサを指定
  "overrides": [  // 特定のファイルに対してのみプロセッサを適用する場合は"processor"の代わりに"overrides"で指定
    {
      "files": [*.md],
      "processor": ""
    }
  ]
  "rules": {
    // write some rules
    "semi": ["error", "always"],  // "error" or "warn" or "off"
  }
}
```
