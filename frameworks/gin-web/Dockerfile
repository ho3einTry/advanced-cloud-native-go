FROM golang:1.19-alpine

RUN apk update && apk upgrade && apk add --no-cache bash git
RUN go env -w GO111MODULE=off
RUN go get github.com/gin-gonic/gin

ENV SOURCES /home/hossein/go/src/github/ho3eintry/advanced-cloud-native-go/frameworks/gin-web
COPY . ${SOURCES}

RUN cd ${SOURCES} && CGO_ENABLED=0 go build

WORKDIR ${SOURCES}
#EXPOSE 8080
#CMD ${SOURCES}gin-web
#RUN cd ${SOURCES}
ENTRYPOINT ./gin-web
