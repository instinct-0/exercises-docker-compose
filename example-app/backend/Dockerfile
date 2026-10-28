FROM golang:1.16

WORKDIR /app/backend
COPY 1_13 .

EXPOSE 8080
ENV PORT=8080
ENV REQUEST_ORIGIN=http://localhost:5001

RUN go build
RUN go test ./...

CMD ["./server"]
