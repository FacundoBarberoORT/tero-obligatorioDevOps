# Stage 1: compilar
FROM golang:1.24-alpine AS build
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 go build -o catalog .

# Stage 2: ejecutar
FROM alpine:3.20
WORKDIR /app
RUN addgroup -S app && adduser -S app -G app
COPY --from=build /app/catalog .
USER app
EXPOSE 8080
CMD ["./catalog"]
