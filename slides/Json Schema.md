---
title: JSON Schema
paginate: true
_paginate: false
marp: true
headingDivider: 2
---
# JSON Schema

## The Schema Metadata

The JSON schema can start with metadata

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://example.com/product.schema.json",
  "title": "Product",
  "description": "A product from Acme's catalog",
}
```


## Describing Object Properties

Specifying object properties can include **type** and **description**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://example.com/product.schema.json",
  "type": "object",
  "properties": {
    "productId": {
      "description": "The unique identifier for a product",
      "type": "integer"
    },
    "productName": {
      "description": "Name of the product",
      "type": "string"
    }
  }
}
```


## Arrays

We can make sure the items are unique or the arrays are not empty

```json
{
  ...
  "type": "object",
  "properties": {
    ...
    "tags": {
      "description": "Tags for the product",
      "type": "array",
      "items": {
        "type": "string"
      },
      "minItems": 1,
      "uniqueItems": true
    }
  },
}
```


## Defining Types

We can define something by **type** of
* `null`
* `object`, `array`
* `boolean`, `number`, `integer`, `string`

or by **enum**, which defines a list of possible values

or by a **const** which defines a single possible value


## Validation Keywords for Numeric Instances

The types of **number** and **integer** can be validated with:

* multipleOf
* maximum
* exclusiveMaximum
* minimum
* exclusiveMinimum


## Validation Keywords for Strings

The type of **string** can be validated with:

* maxLength
* minLength
* pattern
* format

The **format** can be `email`, `date`, `date-time`, `duration` and others.


## Validation Keywords for Arrays

The type of **array** can be validated with. The **contains** keyword describes the type of the items.

* maxItems
* minItems
* uniqueItems
* maxContains
* minContains


## Validation Keywords for Objects

The type of **object** can be validated with:

* maxProperties
* minProperties
* required
* dependentRequired

The **dependentRequired** specifies properties that are required if a specific other property is present. 

## Refenreces to Definitions

We can reference definitions within the current file and also in outside schemas.




## Resources

The best place to learn about the JSON Schema is:

https://www.learnjsonschema.com/



## Q & A

* We cab use JSON to describe and validate JSON
* There is good support within editors and libraries