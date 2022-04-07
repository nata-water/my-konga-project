```shell
$ git clone https://github.com/nata-water/my-konga-project konga
$ cd konga
$ docker-compose up -d
```

### nvm もしくは nvm-windows をインストール

- Windows の場合
  - https://github.com/coreybutler/nvm-windows
- それ以外の場合
  - https://github.com/nvm-sh/nvm

### KONGA のセットアップ

```shell
$ nvm install v12.16.0
$ nvm use v12.16.0
$ npm i bower gulp sails
$ npm i
```

### .env ファイルを作成

- ポイント：NODE_ENV を`production`から`development`に変更しないと、`ERROR: relation "public.konga_users" does not exist at `で落ちる
- production モードだと、konga 用のテーブルが作成されない
- この post(https://github.com/pantsel/konga/issues/35#issuecomment-383559241)に感謝。

```env
PORT=1337
NODE_ENV=development
KONGA_HOOK_TIMEOUT=120000
DB_ADAPTER=postgres
DB_URI=postgresql://kong:kong@127.0.0.1:5432/kong
KONGA_LOG_LEVEL=warn
```

### KONGA を起動

```shell
$ npm start
```

### http://localhost:1337 にアクセス
