FROM golang:1.22

RUN apt-get update && \
    apt-get install -y protobuf-compiler make && \
    rm -rf /var/lib/apt/lists/*

RUN go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.36.6 && \
    go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.5.1

WORKDIR /app

COPY Makefile .
COPY proto ./proto

CMD ["make", "gen-proto"]