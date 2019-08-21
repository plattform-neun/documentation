---
sidebar: auto
prev: false
next: ../
---

# API Reference

**Version 1.0**

## [Customers](/plattform/#customers)
| HTTP method        | Endpoint           | Function                        |
| ------------------ | ------------------ | ------------------------------- |
| GET                | /customers         | List all customers              |
| GET                | /customers/{id}    | Retrieve an individual customer |
| PATCH              | /customers/{id}    | Update an individual customer   |

## [Deliveries](/plattform/#deliveries)
| HTTP method        | Endpoint           | Function                        |
| ------------------ | ------------------ | ------------------------------- |
| GET                | /deliveries        | Fetch a collection              |
| GET                | /deliveries/{id}   | Retrieve an individual delivery |

## [Orders](/plattform/#orders)
| HTTP method        | Endpoint           | Function                        |
| ------------------ | ------------------ | ------------------------------- |
| GET                | /orders            | Fetch a collection              |
| GET                | /orders/{id}       | Retrieve an individual order    |

## [Producers](/plattform/#producers)
| HTTP method        | Endpoint           | Function                        |
| ------------------ | ------------------ | ------------------------------- |
| GET                | /producers         | List all producers              |
| GET                | /producers/{id}    | Retrieve an individual producer |
| PATCH              | /producers/{id}    | Update an individual producer   |

## [Products](/plattform/#products)
| HTTP method        | Endpoint           | Function                        |
| ------------------ | ------------------ | ------------------------------- |
| GET                | /products          | Fetch a collection              |
| POST               | /products          | Create a new product            |
| GET                | /products/{id}     | Retrieve an individual product  |
| PATCH              | /products/{id}     | Update an individual product    |