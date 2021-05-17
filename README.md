# Organization

## Programing Language

### Go
- Dokcerなど先進のOSSで多く利用されている
- bitcoinなどFinTech分野では定番
- 標準ライブラリが秀逸
- go-routineによる並列並行処理のスループットが高い

### TypeScript
- JavaScriptに型付けを行い、堅牢でメンテナンス性も向上

### Deno
- node.jsの反省から作られたTypeScriptの処理系
- 非同期IOなので、一般的にJavaよりスループットが高い

## Front End
### stencil
- ReactをTypeScript化したもの風だが、中身は全く別物
- Reactより遥かに小さく高速なものを、効率よく実装できる
- SSG(Static Site Generator)でSEO対策も問題なし
- SSGでありながらSPAとして動く

## DB
### MongoDB
- 従来のRDBにはない機能が豊富
- index付けにより大規模なデータにも対応
- isolation levelをもつtransactionも可能
- 冗長構成は、Replication(垂直)、Sharding(水平)が可能

### etcd
- 高速なKVSで、CoreOSの冗長構成用に使用されている
- 信頼性の高い冗長構成を組める(Redisは信頼性ナシ)

### InfluxDB
- Time Series DB
- TICK Stackで高度な構成を組める
- Logの収集と分析に適しており、サイズも小さくなる

## Cloud
### Mongo Cloud
### InfluxDB Clound

## OS
### Fedora CoreOS

[index](./index.md)
