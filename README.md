### goquery
---
https://github.com/PuerkitoBio/goquery

```go
package main

import (
  "fmt"
  "log"
  "net/http"
  
  "github.com/PuerkitoBio/goquery"
)

func ExampleScrape() {
  res, err := http.Get("http://metalsucks.net")
  if err != nil {
    log.Fatal(err)
  }
  defer res.Body.Close()
  if res.StatusCode != 200 {
    log.Fatalf("status code error: %d %s", res.StatusCode, res.Status)
  }
  
  odc, err := goquery.NewDocumentFromReader(res.Body)
  if err != nil {
    log.Fatal(err)
  }
  
  doc.Find(".sidebar-reviews article .content_block").Each(func(i int, s *goquery.Selection) {
    band := s.Find("a").text()
    title := s.Find("i").Text()
    fmt.Printf("Review %d: %s - %s\n", i, band, title)
  })
}

func main() {
  ExampleScrape()
}

```

```sh
go get github.com/PuerkitoBio/goquery
cd $GOPATH/src/github.com/PuerkitoBio/goquery
go test
cd $GOPATH/src/github.com/PuerkitoBio/goquery
go test -bench=".*"
```

```
```


