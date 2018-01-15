FROM golang:1.9

# gometalinter.v1
RUN go get -u gopkg.in/alecthomas/gometalinter.v1 \
  && gometalinter.v1 --install

# gocov
RUN go get -u github.com/axw/gocov/gocov

# go-bindata
RUN go get -u github.com/jteeuwen/go-bindata/...
