FROM golang:1.21-alpine
MAINTAINER K4Security <contact@k4-security.com>

# env variables
ENV GO111MODULE=auto

WORKDIR /app/kschain
COPY go.mod .
COPY go.sum .
RUN go mod download
COPY . .

RUN go build -o kschain-registrar *.go
RUN chmod +x kschain-registrar

EXPOSE 9080
CMD ["./kschain-registrar"]
