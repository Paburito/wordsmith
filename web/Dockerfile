FROM golang:alpine as builder

COPY . .

RUN go build dispatcher.go

FROM alpine

COPY --from=builder /go/dispatcher .

COPY --from=builder /go/static ./static

CMD ["./dispatcher"]