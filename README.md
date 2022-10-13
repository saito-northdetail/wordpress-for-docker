# WordPress For Docker

## 概要
- Dockerを用いてWordPressローカル環境を構築

## デフォルトの仕様 ※verやポートについてはdocker-compose.ymlを適宜変更
- Webサーバー
  - Apache
- DBサーバー
  - MySQL：5.7
- WordPress
  - 6.x
- その他
  - phpMyAdmin

## 開発環境作成
### 開発環境セットアップ
- .env(環境設定)ファイルの修正
```
$ cp .env.sample .env
$ vi .env
〜以後適宜修正 エディタでも可〜
```

- コンテナを起動する
```
$ docker-compose up
```

- 各ページにアクセス
  - WordPress
    - http://localhost:8000/
  - phpMyAdmin
    - http://localhost:3000/

- WordPressの設定
  - 通常通り設定 ※注意点のみ記載
    - メールアドレスについては、githubのnoreplyアドレス(`<username>@users.noreply.github.com`)が望ましい
      - メールサーバーを用意していないため迷惑メールとなる可能性が高いため
        - [noreplyアドレスの確認方法](https://docs.github.com/ja/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address)

### テーマを開発を行う場合(テーマがGit管理されている場合)
- テーマディレクトリに移動
```
$ cd wp-content/themes/
```

- テーマをcloneする
```
$ git clone <リポジトリのURL> 

※ 例：twentynineteenテーマの場合
$ git clone https://github.com/WordPress/twentynineteen.git
```

- VSCodeで開く
```
$ code <テーマのディレクトリ名> 

※ 例：twentynineteenテーマの場合
$ code twentynineteen/
```

- WordPressの外観からクローンしてきたテーマを有効化

