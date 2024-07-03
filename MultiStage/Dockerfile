FROM golang:1.21 as Build
WORKDIR /src
COPY <<EOF ./main.go
package main

import "fmt"

func main() {
  fmt.Println("hello, world")
}
EOF
RUN go build -o /bin/hello ./main.go

FROM scratch as B
COPY --from=Build /bin/hello /bin/hello

FROM scratch as C
COPY --from=B /bin/hello /bin/hello
CMD ["/bin/hello"]