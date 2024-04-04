FROM golang:1.19-alpine AS builder
WORKDIR /app
copy main.go
ENV GOOs=windows GOARCH=amd64

RUN go build -o main

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/main /app/main

EXPOSE 8080

CMD ["/app/main"]