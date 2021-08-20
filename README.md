# Construindo um projeto com arquitetura baseada em microsserviços usando Spring Cloud - bootcamp-dio-experts

Exercício prático do funcionamento de uma arquitetura de software baseada em microsserviços, service discovery 
que em conjunto com outras ferramentas possibilita gerenciamento dinâmico e escalabilidade para as aplicações.

## Atividades que serão desenvolvidas e abordadas:

* Setup inicial de projeto com o Spring Boot Initialzr
* Arquitetura de microsserviços
* Elasticsearch
* Redis
* Spring Cloud
* Eureka
* Server Config

## Comandos úteis PowerShell:

Observação os bancos utilizados estão em um servidor externo*

Para executar um POST no product-catalog

```
$Body = @{
    id = 1
    name = 'TV'
    amount = 100
} 
$JsonBody = $Body | ConvertTo-Json
$Params = @{
     Method = "Post"
     Uri = "http://localhost:8081/product"
     Body = $JsonBody
     ContentType = "application/json"
 }
 Invoke-RestMethod @Params
```
Para executar um GET diretamente do Elasticsearch*

```
(Invoke-WebRequest http://192.168.0.115:9200/product/catalog/1).Content | ConvertFrom-Json
```
Para executar um GET no product-catalog
```
Invoke-RestMethod -Uri "http://localhost:8080/product/1"
```

Para executar um POST no shopping-cart

```
$Body = @{
    productid  = 1
    amount = 1
} 
$JsonBody = $Body | ConvertTo-Json
$Params = @{
     Method = "Post"
     Uri = "http://localhost:8082/cart/1"
     Body = $JsonBody
     ContentType = "application/json"
 }
Invoke-RestMethod @Params
```
Para executar um GET no shopping-cart
```
Invoke-RestMethod -Uri "http://localhost:8080/product/1"
```