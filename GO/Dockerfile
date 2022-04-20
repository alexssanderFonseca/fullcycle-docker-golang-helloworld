FROM  golang:alpine3.15 AS build

WORKDIR /app

COPY ./helloworld/go.mod ./
COPY ./helloworld/*.go ./

RUN go mod download


RUN go build -o /hello

FROM scratch

WORKDIR /

COPY --from=build /hello /hello

ENTRYPOINT [ "/hello" ]

