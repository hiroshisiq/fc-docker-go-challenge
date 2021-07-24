FROM golang:1.16 AS builder

WORKDIR /go/src/app

COPY . .

RUN go get -d -v ./...
RUN go install -v ./...


FROM busybox:1.33

COPY --from=builder /go/bin /usr/bin

CMD ["hello-fullcycle"]