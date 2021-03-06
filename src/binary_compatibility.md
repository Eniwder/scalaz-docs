# バイナリ互換とバージョン

## バイナリ互換

Scalazは、多くのScalaのライブラリの中でも、バイナリ互換のポリシーがしっかり決まっているライブラリです。

Scalazでは、バージョン`7.0.0`以降は、同じ規則でバイナリ互換のポリシーが定められています。[^oldz]

具体的には、

- `7.x.y` の `y` の部分のみが変わった場合はバイナリ互換がある
 - 例 `7.0.0` から `7.0.2`, `7.1.3` から `7.1.5` など
- `7.x.y` の `x` の部分が変わった場合はバイナリ互換はない

[Semantic Versioning](http://semver.org/) にはしたがっていないので注意してください。

また、release candidateやmilestoneのリリースは、上記の範囲外であり、バイナリ互換は保証されません。release candidateとmilestoneのversion番号の規則は、以下のようになっています。
- release candidateの場合は後ろに`-RC` と数字がつく
 - 例 `7.2.0-RC1`
- milestoneの場合は後ろに`-M` と数字がつく
 - 例 `7.2.0-M4`


バイナリ互換は、typesafe社がOSSで公開している [migration-manager](https://github.com/typesafehub/migration-manager) と呼ばれるツールで自動でチェックされています。
このmigration-managerは、Scala本体のライブラリ自体のバイナリ互換のチェックにも使われているものです。


## バージョン


### 6以前

- だいぶ古いので詳細は割愛します
- すでに全くメンテはされないので、使わないでください

### 7.0.x

- バージョン `7.0.0` は、2013年4月にリリースされました。  [リリースの際のgoogle groupのスレッド](https://groups.google.com/d/topic/scalaz/_QFqVn3jOPU/discussion)
- Scala 2.9.2, 2.9.3, 2.10.x, 2.11.xをサポートしています
- 執筆時点でのバージョン `7.0.x` 系統の最新は `7.0.8` です
- `7.0.x` 系統は、 `7.1.x` 系統がすでにだいぶ安定していたり `7.2.x` もfinalがリリースされたことにより、今後はほぼ更新されない予定です

### 7.1.x

- バージョン `7.1.0` は、2014年8月にリリースされました
- [リリースの際のgoogle groupのスレッド](https://groups.google.com/d/msg/scalaz/79x3Frhe0Hs/tcGACPaXND8J)
- Scala 2.9.3, 2.10.x, 2.11.x をサポートしています
- 執筆時点でのバージョン `7.1.x` 系統の最新は `7.1.5` です
- `7.1.x` は、まだ何回かは細かい機能追加やバグ修正のリリースの予定をしています

### 7.2.x

- バージョン `7.2.0` のfinalは、2015年12月5日にリリースされました
- [リリースの際のgoogle groupのスレッド](https://groups.google.com/d/topic/scalaz/BXW6BVxYEPE/discussion)
- 2015年12月現在の最新版は7.2.0です
- 7.2.0 final以降、7.2.1, 7.2.2という順番でリリースされる予定で、それらはバイナリ互換を保持する予定です
- Scala 2.10.x, 2.11.x をサポートしています
- Java 7以降をサポートしています
- 可能な限り、次のバージョンのScala 2.12.x などもサポートする予定です


### 7.3.x

- 7.2.0のfinalがリリースされたことにより、2015年12月頃からなんとなく開発がはじまりました
- いまのところ、次のversionは7.3の予定です
- 場合によっては7.3を飛ばして8になる可能性も有り得ますが、詳細未定です
- サポートするScalaのversionは未定です(Scala 2.10を切り捨てるか否か)
- [Java 7のサポートを打ち切って、Java 8以上必須にする予定です](https://github.com/scalaz/scalaz/pull/1063)

[^oldz]: Scalaz 6以前はこの規則にしたがっていません。migration-managerでもチェックされていません。
