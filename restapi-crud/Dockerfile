FROM golang:1.12.0-alpine3.9 AS dev_golang_autocompile

#Esta variable de ambiente da problemas con el autocompile
#ENV GO111MODULE=on

RUN apk update && apk add bash ca-certificates git gcc g++ libc-dev

RUN mkdir /app

WORKDIR /app

#Al declar libreria de persistencia, el contenido no se copia
#Por lo que no es necesario, es preferible copiar archivo en libreria de persistencia
#ADD ./app /app

RUN go get -u github.com/gorilla/mux
RUN go get github.com/githubnemo/CompileDaemon

#comando para compilar el binario queda con el nombre app
#CMD go build

#comandos para recompilar y llamar al binario, el app toma el nombre de la carpeta
#se debe verificar
#CMD CompileDaemon
CMD CompileDaemon -command="./app"

#CMD ["bash", "pwd"]