FROM golang:1.20 AS builder

RUN mkdir -p /app

WORKDIR /app

COPY go.mod ./

COPY . .

RUN go build ./hello-fullcycle.go


FROM scratch
WORKDIR /app
COPY --from=builder /app .

ENTRYPOINT ["./hello-fullcycle"]