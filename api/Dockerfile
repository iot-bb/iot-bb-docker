# STEP 1 build executable binary
FROM golang:alpine as builder
COPY ./iot-bb-api/main.go $GOPATH
WORKDIR $GOPATH
#get dependancies
#you can also use dep
RUN apk add --no-cache git
RUN go get -d -v
#build the binary
RUN go build -o /go/bin/api
RUN apk del git
# STEP 2 build a small image
# start from scratch
FROM alpine
# Copy our static executable
RUN adduser -S -D -H -h /app appuser
USER appuser
COPY --from=builder /go/bin/api /app/
ENTRYPOINT [ "/app/api" ]