# Jest でテストを書こう[^1]

> Jest は JavaScript のテストフレームワークです。TypeScript でテストを書くこともできます。Jest は、フロントエンドライブラリの React や Vue などのテストだけでなく、Node.js 向けのパッケージのテストも行えます。要するに、JavaScript や TypeScript で書かれたコードであれば、そのほとんどは Jest でテストが行えます。

## Jest をインストールする

```bash
yarn add -D jest@^28.0.0 ts-jest@^28.0.0 @types/jest@^28.0.0
```

### jest

> Jest 本体です。JavaScript だけのプロジェクトであれば、このパッケージを入れるだけでテストが始められます。

### ts-jest

> Jest を TypeScript に対応させるためのものです。

### @types/jest

> Jest の API の型定義ファイルです。TypeScript の型情報を付与されるので、テストコードの型チェックが行えるようになります。

## Jest の設定ファイルを作る

> 次のコマンドを実行すると、Jest の設定ファイル`jest.config.js`が生成されます。

```bash
yarn ts-jest config:init
```

▼ jest.config.js

```js
/** @type {import("ts-jest/dist/types").InitialOptionsTsJest} */
module.exports = {
  preset: "ts-jest",
  testEnvironment: "node",
};
```

> この@type のコメントはエディターに型情報を与えるためのものです。これを書いておくことで、エディター上で入力補完が効くようになります。

```sh
├── jest.config.js ... Jestの設定ファイル
├── node_modules ... jestやtypescriptがインストールされたフォルダ
├── package.json
├── tsconfig.json ... TypeScriptの設定ファイル
└── yarn.lock
```

## Jest が動くかを確認する

> Jest で実行できるテストファイルには命名規則があります。ファイル名が`.test.ts`または`.spec.ts`で終わるものが、テストファイルになります。

動作確認用のファイルとして、`check.test.ts` を作って`yarn jest`で確認</br>
=> 問題なく実行されていることが確認できたら、`check.test.ts` は削除。

```sh
touch check.test.ts
```

▼ check.test.ts の内容は次のようにします。

```ts
test("check", () => {
  console.log("OK");
});
```

テストの書き方は[こちら](https://typescriptbook.jp/tutorials/jest)で確認

> [^1]: https://typescriptbook.jp/tutorials/jest
