# Introdução ao Apache Kafka
 
Neste repositório apenas algumas ações introdutórias ao uso Apache Kafka como plataforma distribuída de streaming de eventos.

## Docker Compose

No diretório raiz temos um `docker-compose` com todo os serviços utilizados: **MySQL**, **Zookeeper**, **Apache Kafka**, **Kafka Connect**, **Confluent Control Center**, **MongoDB** e o **Mongo Express**.

  
## Testando produtor e consumidor

Temos um app em GoLang que simula um `producer` enviando a mensagem `xml-data` para o tópico `nfe-xml-data` toda vez que é executado

    go run cmd/producer/main.go

Outro app, também em Go Lang que simula um `consumer` participante do grupo `xml-data-group` e que lê as mensagens no tópico `nfe-xml-data`

    go run cmd/consumer/main.go

> O ambiente Go foi utilizado a partir do container definido no **Dockerfile** localizado no raiz do repositório e, para tanto, quando subir o ambiente a primeira vez considere acrescentar a opção `--build` no comando do `docker-compose up -d` para que a imagem seja construída.
