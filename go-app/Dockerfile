
FROM golang:1.20 AS builder
COPY main.go  .
RUN  go build main.go
EXPOSE 8080
CMD ["./main"]
