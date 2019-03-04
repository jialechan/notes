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
### 上传分析到sonar
```shell
$ /path_to_sonar/bin/sonar-scanner -Dsonar.host.url=http://xxx \
-Dsonar.login=xxx \
-Dsonar.go.coverage.reportPaths=/Users/jialechan/GolandProjects/http-demo/coverage.out \
-Dsonar.projectKey=jiale:http-demo \
-Dsonar.sources=/Users/jialechan/GolandProjects/http-demo/ \
-Dsonar.coverage.exclusions=**/*_test.go \
-Dsonar.scm.disabled=true
```

### 参考资料
https://www.cnblogs.com/zhaoxd07/p/8028847.html  
https://www.elastic.co/blog/code-coverage-for-your-golang-system-tests   
https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner   
https://docs.sonarqube.org/latest/analysis/analysis-parameters/
