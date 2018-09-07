FROM kamermans/jq:latest as jq

FROM golang:1.9

# gometalinter.v1
RUN go get -u gopkg.in/alecthomas/gometalinter.v1 \
  && gometalinter.v1 --install

# gocov
RUN go get -u github.com/axw/gocov/gocov

# go-bindata
RUN go get -u github.com/jteeuwen/go-bindata/...

# jq
COPY --from=jq /usr/local/bin/jq-1.5 /usr/local/bin

# moq
RUN go get github.com/matryer/moq

# wire
RUN go get -u github.com/google/go-cloud/wire/cmd/wire