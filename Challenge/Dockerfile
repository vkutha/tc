# build stage
FROM golang:alpine AS builder
ADD . /src
WORKDIR /src
RUN CGO_ENABLED=0 GOOS=linux go build -o main .

# final stage
FROM alpine:latest as final
COPY --from=builder /src .
EXPOSE 3000
ENTRYPOINT ./main

