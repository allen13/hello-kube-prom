# https://docs.docker.com/engine/reference/builder/

# step 1 - build image
FROM golang:1.15.1-alpine AS builder

RUN apk update && apk add git
RUN go get -v github.com/prometheus/client_golang/prometheus/promhttp

WORKDIR /go/src

COPY . .

RUN go build -o hello-http ./hello-http.go

# step 2 - run image
FROM alpine:3.12.0 AS runner
# Copy our static executable.
COPY --from=builder /go/src/hello-http /usr/bin/hello-http

CMD ["/usr/bin/hello-http"]