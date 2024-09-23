FROM golang:1.20-alpine AS builder
WORKDIR /app
COPY . .
RUN go mod init my-go-app
RUN go build -o main .

FROM alpine:latest
COPY --from=builder /app/main /main
ENTRYPOINT ["/main"]