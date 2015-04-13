# Fluent::Plugin::Json::Serializer

## 概要

* httpリクエストに対して、ステータスコード200を返すだけのプラグインです
* データとしては何も受け取らないし、送らないです
* TD-agent v0.10以降で動作します

## plugin詳細

* HTTPリクエストに対してステータスコード200を返答します
* ロードバランサーにヘルスチェックさせたいときに使うといいんじゃないかなと思います
* デフォルトでインストールされている、in_httpプラグインをサブクラス化してるだけです
* つまりin_httpで使えるオプションはそのまま使えます

## Install
td-agent 0.10.0 以上

```
$ cd /usr/local/src
$ git clone ssh://git@stash.gu3.jp:7999/error-handling/fluent-plugin-json-serializer.git
$ cd ./fluent-plugin-json-serializer
$ /usr/lib64/fluent/ruby/bin/rake build
$ /opt/td-agent/embedded/bin/fluent-gem install pkg/fluent-plugin-json-serializer
```


## Usage

```
<match **>
  type http_healthcheck
  port 8888
  bind 0.0.0.0
</match>
```

動作確認してみる

```
# curl http://localhost:8888
:) < Hello!
```

## ToDo

* 特になし

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
