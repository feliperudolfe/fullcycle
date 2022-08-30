FROM            golang:alpine3.16 AS build

WORKDIR         /src/
COPY            main.go go.mod /src/
RUN             CGO_ENABLE=0 go build -o /bin/hello

FROM            scratch
COPY            --from=build /bin/hello /bin/hello
ENTRYPOINT [ "/bin/hello" ]