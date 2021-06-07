FROM golang:1.13-alpine
WORKDIR /ateneo
RUN apk update && apk add --no-cache gcc musl-dev git bash
COPY . .
RUN go build -ldflags '-w -s' -a -o ./bin/app ./cmd/app
CMD ["/ateneo/bin/app"]
EXPOSE 8080