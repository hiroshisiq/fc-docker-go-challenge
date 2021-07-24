FROM golang:1.16 AS builder

WORKDIR /go/src/app

COPY . .

RUN go get -d -v ./...
RUN go install -v ./...


FROM scratch

COPY --from=builder /go/bin/hello-fullcycle /usr/bin/hello-fullcycle

CMD ["hello-fullcycle"]