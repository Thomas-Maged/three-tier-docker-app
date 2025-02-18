FROM golang:1.23 AS builder

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum  ./
RUN go mod download

COPY . ./
RUN go build -o app .


FROM debian:bookworm-slim
WORKDIR /
COPY --from=builder /usr/src/app/run/ /run/
COPY --from=builder /usr/src/app/app /app
CMD ["/app"] 



