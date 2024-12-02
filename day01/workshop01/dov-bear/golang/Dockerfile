FROM golang:1.23-alpine3.20 AS gobuilder

WORKDIR /src

COPY go.* .
COPY main.go .

RUN go build -o main main.go

FROM alpine:3.20

WORKDIR /app

# copy from gobuilder/src/main into our current directory
COPY --from=gobuilder /src/main /app/main
COPY public public
COPY templates templates

ENV PORT=3000

EXPOSE ${PORT}

ENTRYPOINT [ "/app/main" ]

CMD []
