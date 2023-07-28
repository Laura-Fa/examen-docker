# Exercice 7
FROM golang:1.20 AS build
WORKDIR /app
COPY ["go.mod", "go.sum", "/app/"]
RUN go mod download
COPY . .
RUN go build -o geek-life
# Second stage : run
FROM ubuntu:23.10
COPY --from=build ./app/geek-life ./geek-life
ENTRYPOINT ["./geek-life"]
