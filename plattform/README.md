---
sidebar: auto
---

# Getting started

Our JSON API is organized around REST with predictable resource-oriented URLs, accepts form-encoded request bodies, returns JSON-encoded responses, and uses standard HTTP response codes, authentication, and verbs.

[API-Reference](api-reference)

#### Base URL
```
 /api/v1
```

## Authentication

We use Access Tokens to authenticate requests. You can view and manage your Personal Access Tokens in your Dashboard.
Your Personal Access Token carry many privileges, so be sure to keep them secure! Do not share your secret Tokens in publicly accessible areas such as GitHub, client-side code, and so forth.
All API requests must be made over HTTPS. Calls made over plain HTTP will fail. API requests without authentication will also fail.

``` BASH
curl https://plattformneun.com/api/v1/me \
  -H "Authorization: Bearer YOUR_PERSONAL_ACCESS_TOKEN"
```

## Customers

The API allows you to delete, and update your customers. You can retrieve individual customers as well as a list of all your customers.

### Get a list of all customers
__REQUEST__ `GET` / customers
``` BASH
curl https://plattformneun.com/api/v1/customers
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": [
        {
            "id": 12345,
            "name": {
                "first": "John",
                "last": "Doe"
            },
            "email": "johndoe@example.com",
            "verified_at": "2019-07-04 12:45:09",
            "created_at": "2019-06-24 10:42:02",
            "updated_at": "2019-07-04 12:45:09",
            "company": {
                "name": "Gretas Hof",
                "legal_form": "GmbH",
                "address": {
                    "street": "Am alten Pfad",
                    "house": "9",
                    "post_code": "10997",
                    "city": "Berlin-Kreuzberg",
                    "country": "Deutschland"
                },
                "vat_id": "DE123456789",
                "user_type": "customer"
            }
        },

        { ... }
    ]
}
```

### Retrieve a customer
__REQUEST__  __`GET`__ `/customers/{id}`

``` BASH
curl https://plattformneun.com/api/v1/customers/12345
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 12345,
        "name": {
            "first": "John",
            "last": "Doe"
        },
        "email": "johndoe@example.com",
        "verified_at": "2019-07-04 12:45:09",
        "created_at": "2019-06-24 10:42:02",
        "updated_at": "2019-07-04 12:45:09",
        "company": {
            "name": "Gretas Hof",
            "legal_form": "GmbH",
            "address": {
                "street": "Am alten Pfad",
                "house": "9",
                "post_code": "10997",
                "city": "Berlin-Kreuzberg",
                "country": "Deutschland"
            },
            "vat_id": "DE123456789",
            "user_type": "customer"
        }
    }
}
```

### Update a customer
__REQUEST__  __`PATCH`__ `/customers/{id}`

``` BASH
curl https://plattformneun.com/api/v1/customers/12345 \
    -d street="Neue Straße" \
    -d house="112-114" \
    -d post_code=10997 \
    -d city="Berlin"
```
::: warning Available body parameters
- company_name `String(255)`
- legal_form `String(255)`
- street `String(255)`
- house `String(16)`
- post_code `Integer(8)`
- city `String(255)`
- country `String(255)`
- vat_id `String(11)`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 12345,
        "name": {
            "first": "John",
            "last": "Doe"
        },
        "email": "johndoe@example.com",
        "verified_at": "2019-07-04 12:45:09",
        "created_at": "2019-06-24 10:42:02",
        "updated_at": "2019-07-04 12:45:09",
        "company": {
            "name": "Gretas Hof",
            "legal_form": "GmbH",
            "address": {
                "street": "Neue Straße",
                "house": "112-114",
                "post_code": "10997",
                "city": "Berlin",
                "country": "Deutschland"
            },
            "vat_id": "DE123456789",
            "user_type": "customer"
        }
    }
}
```


## Producers

The API allows you to delete, and update your producers. You can retrieve individual producers as well as a list of all your producers.

### Get a list of all producers
__REQUEST__ `GET` / producers
``` BASH
curl https://plattformneun.com/api/v1/producers
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": [
        {
            "id": 12345,
            "name": {
                "first": "John",
                "last": "Doe"
            },
            "email": "johndoe@example.com",
            "verified_at": "2019-07-04 12:45:09",
            "created_at": "2019-06-24 10:42:02",
            "updated_at": "2019-07-04 12:45:09",
            "company": {
                "name": "Gretas Hof",
                "legal_form": "GmbH",
                "address": {
                    "street": "Am alten Pfad",
                    "house": "9",
                    "post_code": "10997",
                    "city": "Berlin-Kreuzberg",
                    "country": "Deutschland"
                },
                "vat_id": "DE123456789",
                "user_type": "producer"
            }
        },

        { ... }
    ]
}
```

### Retrieve a producer
__REQUEST__  __`GET`__ `/producers/{id}`

``` BASH
curl https://plattformneun.com/api/v1/producers/12345
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 12345,
        "name": {
            "first": "John",
            "last": "Doe"
        },
        "email": "johndoe@example.com",
        "verified_at": "2019-07-04 12:45:09",
        "created_at": "2019-06-24 10:42:02",
        "updated_at": "2019-07-04 12:45:09",
        "company": {
            "name": "Gretas Hof",
            "legal_form": "GmbH",
            "address": {
                "street": "Am alten Pfad",
                "house": "9",
                "post_code": "10997",
                "city": "Berlin-Kreuzberg",
                "country": "Deutschland"
            },
            "vat_id": "DE123456789",
            "user_type": "producer"
        }
    }
}
```

### Update a producer
__REQUEST__  __`PATCH`__ `/producers/{id}`

``` BASH
curl https://plattformneun.com/api/v1/producers/12345 \
    -d street="Neue Straße" \
    -d house="112-114" \
    -d post_code=10997 \
    -d city="Berlin"
```
::: warning Available body parameters
- username `slug, unique` 
- company_name `String(255)`
- legal_form `String(255)`
- street `String(255)`
- house `String(16)`
- post_code `Integer(8)`
- city `String(255)`
- country `String(255)`
- vat_id `String(11)`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 12345,
        "name": {
            "first": "John",
            "last": "Doe"
        },
        "email": "johndoe@example.com",
        "verified_at": "2019-07-04 12:45:09",
        "created_at": "2019-06-24 10:42:02",
        "updated_at": "2019-07-04 12:45:09",
        "company": {
            "name": "Gretas Hof",
            "legal_form": "GmbH",
            "address": {
                "street": "Neue Straße",
                "house": "112-114",
                "post_code": "10997",
                "city": "Berlin",
                "country": "Deutschland"
            },
            "vat_id": "DE123456789",
            "user_type": "producer"
        }
    }
}
```

## Products

The API allows you to delete, and update products. You can retrieve individual products as well as a collection of products.

### Get a collection of products
__REQUEST__ `GET` / products
``` BASH
curl https://plattformneun.com/api/v1/products?producer_id=12345
```

::: warning Available query parameters
- producer_id `Integer` 
- username `String, Slug`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": [
        {
            "id": 84683,
            "producer_id": 12345,
            "visibillity": true,
            "title": "Potatoes",
            "unit": "kg",
            "volume": {
                "amount": 1,
                "unit": "kg"
            },
            "price": {
                "amount": 1500,
                "unit": "kg"
            },
            "vat": 7,
            "lead_time": 2,
            "updated_at": "2019-07-19 10:20:54",
            "created_at": "2019-07-19 10:20:54"
        },

        { ... }
    ]
}
```

### Retrieve a product
__REQUEST__  __`GET`__ `/products/{id}`

``` BASH
curl https://plattformneun.com/api/v1/products/84683
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 84683,
        "producer_id": 12345,
        "visibillity": false,
        "title": "Potatoes",
        "unit": "kg",
        "volume": {
            "amount": 1,
            "unit": "kg"
        },
        "price": {
            "amount": 1500,
            "unit": "kg"
        },
        "vat": 7,
        "lead_time": 2,
        "updated_at": "2019-07-19 10:20:54",
        "created_at": "2019-07-19 10:20:54"
    }
}
```

### Create a product
__REQUEST__  __`POST`__ `/products`

``` BASH
curl https://plattformneun.com/api/v1/products \
    -d visibillity="false" \
    -d title="Potatoes" \
    -d unit="kg" \
    -d volume="1" \
    -d volume_unit="kg" \
    -d price="1500" \
    -d price_unit="kg" \
    -d vat="7" \
    -d lead_time="2"
```

::: warning Available body parameters
- visibillity `Boolean` 
- title `String(255)`
- unit `String(2)`
- volume `Integer, Unsigned`
- volume_unit `String(2)`
- price `Integer, Unsigned`
- price_unit `String(2)`
- price `TinyInteger, Unsigned`
- lead_time `TinyInteger, Unsigned`
:::

__RESPONSE__ `StatusCode` 201
``` JSON
{
    "status": {
        "code": 201,
        "message": "Entity created."
    }
}
```

### Update an individual product
__REQUEST__  __`PATCH`__ `/products/84683`

``` BASH
curl https://plattformneun.com/api/v1/products/84683 \
    -d visibillity="true" 
```
::: warning Available body parameters
- visibillity `Boolean` 
- title `String(255)`
- unit `String(2)`
- volume `Integer, Unsigned`
- volume_unit `String(2)`
- price `Integer, Unsigned`
- price_unit `String(2)`
- price `TinyInteger, Unsigned`
- lead_time `TinyInteger, Unsigned`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 84683,
        "producer_id": 12345,
        "visibillity": true,
        "title": "Potatoes",
        "unit": "kg",
        "volume": {
            "amount": 1,
            "unit": "kg"
        },
        "price": {
            "amount": 1500,
            "unit": "kg"
        },
        "vat": 7,
        "lead_time": 2,
        "updated_at": "2019-07-19 10:20:54",
        "created_at": "2019-07-19 10:20:54"
    }
}
```

## Orders

The API allows you to fetch orders. You can retrieve individual orders as well as a collection of orders.

### Get a collection of orders
__REQUEST__ `GET` / orders
``` BASH
curl https://plattformneun.com/api/v1/orders?offset=1564313229 \
```

::: warning Available query parameters
- customer_id `Integer` 
- offset `Unix Timestamp`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": [
        {
            "id": 98732,
            "producer_id": 5678,
            "customer_id": 1234,
            "price": {
                "subtotal": 4000,
                "total": 4280,
                "vat": [
                    {
                        "factor": 7,
                        "amount": 280
                    }
                ]
            },
            "items": [
                {
                    "quantity": 10,
                    "price": 250,
                    "vat": 7,
                    "product": {
                        "id": 84683,
                        "producer_id": 5678,
                        "title": "Potatoes",
                        "unit": "kg",
                        "volume": {
                            "amount": 1,
                            "unit": "kg"
                        },
                        "price": {
                            "amount": 1500,
                            "unit": "kg"
                        },
                        "vat": 7,
                    }
                },

                { ... }
            ],
            "updated_at": "2019-07-19 10:22:54",
            "created_at": "2019-07-19 10:20:54",
        },

        { ... }
    ]
}
```

### Retrieve an individual order
__REQUEST__  __`GET`__ `/orders/{id}`

``` BASH
curl https://plattformneun.com/api/v1/orders/98732
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 98732,
        "producer_id": 5678,
        "customer_id": 1234,
        "price": {
            "subtotal": 4000,
            "total": 4280,
            "vat": [
                {
                    "factor": 7,
                    "amount": 280
                }
            ]
        },
        "items": [
            {
                "quantity": 10,
                "price": 250,
                "vat": 7,
                "product": {
                    "id": 84683,
                    "producer_id": 5678,
                    "title": "Potatoes",
                    "unit": "kg",
                    "volume": {
                        "amount": 1,
                        "unit": "kg"
                    },
                    "price": {
                        "amount": 1500,
                        "unit": "kg"
                    },
                    "vat": 7,
                }
            },

            { ... }
        ],
        "updated_at": "2019-07-19 10:22:54",
        "created_at": "2019-07-19 10:20:54",
    },
}
```

## Deliveries

The API allows you to fetch deliveries. A Delivery is a collection of orders. You can retrieve an individual delivery as well as a collection of deliveries.

### Get a collection of deliveries
__REQUEST__  __`GET`__ `/deliveries`
``` BASH
curl https://plattformneun.com/api/v1/deliveries?offset=1564313229 \
```

::: warning Available query parameters
- customer_id `Integer` 
- supplier_id `Integer` 
- offset `Unix Timestamp`
:::

__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": [
        {
            "id": 98732,
            "customer_id": 5678,
            "supplier_id": 1234,
            "price": {
                "shipping": 2000,
                "subtotal": 4000,
                "total": 6660,
                "vat": [
                    {
                        "factor": 7,
                        "amount": 280
                    },
                    {
                        "factor": 19,
                        "amount": 380
                    }
                ]
            },
            "items": [
                {
                    "quantity": 10,
                    "price": 250,
                    "vat": 7,
                    "product": {
                        "id": 84683,
                        "producer_id": 5678,
                        "title": "Potatoes",
                        "unit": "kg",
                        "volume": {
                            "amount": 1,
                            "unit": "kg"
                        },
                        "price": {
                            "amount": 1500,
                            "unit": "kg"
                        },
                        "vat": 7,
                    }
                },

                { ... }
            ],
            "delivery_address": {
                "recipient": "Gretas Hof GmbH",
                "street": "Am alten Pfad",
                "house": "9",
                "post_code": "10997",
                "city": "Berlin-Kreuzberg",
                "country": "Deutschland"
            },
            "updated_at": "2019-07-19 10:22:54",
            "created_at": "2019-07-19 10:20:54",
            "delivery_at": "2019-07-23 12:00:00"
        },

        { ... }
    ]
}
```

### Retrieve an individual delivery
__REQUEST__  __`GET`__ `/deliveries/{id}`

``` BASH
curl https://plattformneun.com/api/v1/deliveries/98732
```
__RESPONSE__ `StatusCode` 200
``` JSON
{
    "data": {
        "id": 98732,
        "customer_id": 5678,
        "supplier_id": 1234,
        "price": {
            "shipping": 2000,
            "subtotal": 4000,
            "total": 6660,
            "vat": [
                {
                    "factor": 7,
                    "amount": 280
                },
                {
                    "factor": 19,
                    "amount": 380
                }
            ]
        },
        "items": [
            {
                "quantity": 10,
                "price": 250,
                "vat": 7,
                "product": {
                    "id": 84683,
                    "producer_id": 5678,
                    "title": "Potatoes",
                    "unit": "kg",
                    "volume": {
                        "amount": 1,
                        "unit": "kg"
                    },
                    "price": {
                        "amount": 1500,
                        "unit": "kg"
                    },
                    "vat": 7,
                }
            },

            { ... }
        ],
        "delivery_address": {
            "recipient": "Gretas Hof GmbH",
            "street": "Am alten Pfad",
            "house": "9",
            "post_code": "10997",
            "city": "Berlin-Kreuzberg",
            "country": "Deutschland"
        },
        "updated_at": "2019-07-19 10:22:54",
        "created_at": "2019-07-19 10:20:54",
        "delivery_at": "2019-07-23 12:00:00"
    }
}
```
