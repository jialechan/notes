### main.go
```go
package main

import (
	"fmt"
	"net/http"
)

func main() {

	server := &http.Server{
		Addr:    ":8444",
		Handler: http.DefaultServeMux,
	}

	http.HandleFunc("/", func (w http.ResponseWriter, r *http.Request) {
		fmt.Fprintf(w, "Welcome to my website!")
	})

	http.HandleFunc("/stop", func (w http.ResponseWriter, r *http.Request) {
		fmt.Fprintf(w, "Go to stop!")
		server.Close()
	})

	server.ListenAndServe()

}
```
### main_test.go
```go
package main

import (
	"testing"
)

func TestSystem(t *testing.T) {
	main()
}
```
### build test app
```shell
go test -c -coverpkg ./...
```
### run test app
```shell
./http-demo.test -test.coverprofile coverage.cov
```
### run auto test 
```bash
curl -v "http://localhost:8444/"
curl -v "http://localhost:8444/stop"
```
### output
```shell
# ./http-demo.test  -test.coverprofile coverage.cov
PASS
coverage: 100.0% of statements in ./...
#
```
