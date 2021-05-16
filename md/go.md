# [Go](https://golang.org)

- 標準[package](https://golang.org/pkg/)が充実
- 豊富な[Examples](https://golang.org/pkg/net/http/#pkg-examples)
- 高いスループットの実現するgoroutine

## わずかなコードで実現 ***Http Server***

```go
package main

import (
	"log"
	"net/http"
)

func main() {
	// Simple static webserver:
	log.Fatal(http.ListenAndServe(":8080", http.FileServer(http.Dir("/usr/share/doc"))))
}
```

## 非同期IOでのBenchmark
	CSP (Communication Sequential Processes)

	Multi ThreadのServletではNode.jsに及ばない
	よって、Javaは高性能で知られるWildflyの非同期IOで実装

### Producer → WebServer → Client
	ProducerからWebServerへ大量のデータをTCPで送信し、WebServerはWebSocketで同時接続しているClientに送信
	ProducerとClientをGoで作成し、WebServerをNode.js, Java, Goで比較

### 同時接続数: 遅延, メモリ消費

| 接続数 | Node.js | Java | Go |
|:-|:-|:-|:-|
| 50 | 0.39sec, 79m | 0.2sec, 396m | 0.29sec, 16m |
| 100 | error | 4.2sec, 980m |0.2sec, 19m|
| 150 |-| 75sec, 1.5g | 0.2sec, 21m |
| 200 |-|-| 0.54sec, 25m |
| 250 |-|-| 0.51sec, 29m |
| 300 |-|-| error |
||||

- Javaは同時100接続で4.2秒もの遅延が発生、メモリ消費は1G弱
- Goは同時250接続でも問題なし、メモリ消費は30M弱
- GoはJava比で、2.5倍以上の同時接続を1/30のメモリーで実現

[readme](../README.md)
