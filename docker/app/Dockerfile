# Build environment
# -----------------
FROM golang:1.13-alpine
WORKDIR /ateneo

RUN apk update && apk add --no-cache gcc musl-dev git bash

COPY . .
RUN go build -ldflags '-w -s' -a -o ./bin/app ./cmd/app

# Deployment environment
# ----------------------
FROM alpine

RUN apk update && apk add --no-cache bash
COPY --from=build-env /ateneo/bin/app /ateneo/

CMD ["/ateneo/bin/app"]
EXPOSE 8080