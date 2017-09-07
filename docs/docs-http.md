# 

**`API Version:`** `1.0`

Set up the PayPal Express Checkout Server-Side REST product



## Server Configuration for Base URLs

This section provides details on the environments available and lists down the servers in each of the environment. The default environment for this API is set to `sandbox` while the default server is set to `Sandbox`.
### Environments

An environment consists of a set of servers with base URL values. The environment can be changed programatically allowing rapid switching between different environments e.g.the user can specify a Production and Testing Environment.The available environments for this API are: 

#### production
This environment comprises of the following servers: 

| Name | Base URL | 
|-----------|-------------|
| Sandbox | https://api.sandbox.paypal.com/v1 |

#### sandbox
> Development

This environment comprises of the following servers: 

| Name | Base URL | 
|-----------|-------------|
| Sandbox | https://api.sandbox.paypal.com/v1 |




## Authentication
This API uses `OAuth v2.0` with `bearer token`.



### Additional Headers

Additional authentication headers that will be sent with your API requests are listed below:

| Parameter | Description | Example | 
|-----------|-------------| ------- |
| client_id | client id | `"AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"` | 
| client_secret | client secret | `"EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"` | 





# <a name="api_reference"></a>API Reference

* [Payment](#payment)

## <a name="payment"></a>![Endpoint Group: ](https://apidocs.io/img/class.png "Payment") Payment


### <a name="execute"></a>![Endpoint: ](https://apidocs.io/img/method.png "execute") execute


**`POST`** `/payments/payment/{payment_id}/execute`

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.




#### Path Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ----------------------------------- |
| payment_id | string |  ``` Required ```  | The ID of the payment to execute. | `"payment_id"` | 

#### Request Headers
>Content-Type=application/json;

#### Request Body
Raw 

|  Type | Tags | Description |
| ------| ---- |-------------| 
| [Execute Request](#execute_request) |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. | 

 *Example Body* 
``` 
Bearer A21AAHdZ73bsQUjOrlAzfucLwq2janvn7EKS0heMUHLsurdS0aZLLGJMB4LC2MHo6SuXp0oDilSM4z4xsGpUwASDBW16BUbfw
``` 

#### Responses
**200** 


 *Example Body* (**[Execute Response](#execute_response)**) 

```
{
  "id": "id",
  "create_time": "create_time",
  "update_time": "update_time",
  "state": "state",
  "intent": "intent",
  "payer": {
    "payment_method": "payment_method",
    "payer_info": "payer_info"
  },
  "transactions": [
    {
      "amount": {
        "total": "total",
        "currency": "currency",
        "details": {
          "subtotal": "subtotal",
          "tax": "tax",
          "shipping": "shipping",
          "handling_fee": "handling_fee",
          "shipping_discount": "shipping_discount",
          "insurance": "insurance"
        }
      },
      "description": "description",
      "custom": "custom",
      "invoice_number": "invoice_number",
      "payment_options": {
        "allowed_payment_method": "allowed_payment_method"
      },
      "soft_descriptor": "soft_descriptor",
      "item_list": {
        "items": [
          {
            "name": "name",
            "description": "description",
            "quantity": "quantity",
            "price": "price",
            "tax": "tax",
            "sku": "sku",
            "currency": "currency"
          }
        ],
        "shipping_address": {
          "line1": "line1",
          "line2": "line2",
          "city": "city",
          "state": "state",
          "postal_code": "postal_code",
          "country_code": "country_code",
          "phone": "phone",
          "recipient_name": "recipient_name"
        }
      }
    }
  ],
  "links": [
    {
      "href": "href",
      "rel": "rel",
      "method": "method"
    }
  ]
}
```


### <a name="create"></a>![Endpoint: ](https://apidocs.io/img/method.png "create") create


**`POST`** `/payments/payment`

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.




#### Request Headers
>Accept=application/json;
>Content-Type=application/json;

#### Request Body
Raw 

|  Type | Tags | Description |
| ------| ---- |-------------| 
| [Payment Request](#payment_request) |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request | 

 *Example Body* 
``` 
{
  "intent": "sale",
  "payer": {
    "payment_method": "paypal"
  },
  "transactions": [
    {
      "amount": {
        "total": "30.11",
        "currency": "USD",
        "details": {
          "subtotal": "30.00",
          "tax": "0.07",
          "shipping": "0.03",
          "handling_fee": "1.00",
          "shipping_discount": "-1.00",
          "insurance": "0.01"
        }
      },
      "description": "The payment transaction description.",
      "custom": "EBAY_EMS_90048630024435",
      "invoice_number": "48787589673",
      "payment_options": {
        "allowed_payment_method": "INSTANT_FUNDING_SOURCE"
      },
      "soft_descriptor": "ECHI5786786",
      "item_list": {
        "items": [
          {
            "name": "hat",
            "description": "Brown hat.",
            "quantity": "5",
            "price": "3",
            "tax": "0.01",
            "sku": "1",
            "currency": "USD"
          },
          {
            "name": "handbag",
            "description": "Black handbag.",
            "quantity": "1",
            "price": "15",
            "tax": "0.02",
            "sku": "product34",
            "currency": "USD"
          }
        ],
        "shipping_address": {
          "recipient_name": "Brian Robinson",
          "line1": "4th Floor",
          "line2": "Unit #34",
          "city": "San Jose",
          "country_code": "US",
          "postal_code": "95131",
          "phone": "011862212345678",
          "state": "CA"
        }
      }
    }
  ],
  "note_to_payer": "Contact us for any questions on your order.",
  "redirect_urls": {
    "return_url": "https://sandbox.paypal.com",
    "cancel_url": "https://sandbox.paypal.com"
  }
}
``` 

#### Responses
**200** 


 *Example Body* (**[Payment Response](#payment_response)**) 

```
{
  "id": "id",
  "intent": "intent",
  "state": "state",
  "payer": {
    "payment_method": "payment_method",
    "payer_info": "payer_info"
  },
  "transactions": [
    {
      "amount": {
        "total": "total",
        "currency": "currency",
        "details": {
          "subtotal": "subtotal",
          "tax": "tax",
          "shipping": "shipping",
          "handling_fee": "handling_fee",
          "shipping_discount": "shipping_discount",
          "insurance": "insurance"
        }
      },
      "description": "description",
      "custom": "custom",
      "invoice_number": "invoice_number",
      "soft_descriptor": "soft_descriptor",
      "payment_options": {
        "allowed_payment_method": "allowed_payment_method",
        "recurring_flag": false,
        "skip_fmf": false
      },
      "item_list": {
        "items": [
          {
            "name": "name",
            "sku": "sku",
            "description": "description",
            "price": "price",
            "currency": "currency",
            "tax": "tax",
            "quantity": 37
          }
        ],
        "shipping_address": {
          "line1": "line1",
          "line2": "line2",
          "city": "city",
          "state": "state",
          "postal_code": "postal_code",
          "country_code": "country_code",
          "phone": "phone",
          "recipient_name": "recipient_name"
        }
      },
      "related_resources": [
        "related_resources"
      ]
    }
  ],
  "note_to_payer": "note_to_payer",
  "create_time": "create_time",
  "links": [
    {
      "href": "href",
      "rel": "rel",
      "method": "method"
    }
  ]
}
```


[Back to API Reference](#api_reference)

# <a name="models"></a> Models

### List of Models

* [Amount](#amount)
* [Link](#link)
* [ItemList16](#item_list16)
* [PaymentOptions15](#payment_options15)
* [RedirectUrls](#redirect_urls)
* [ItemList](#item_list)
* [RelatedResource](#related_resource)
* [Execute Request](#execute_request)
* [PaymentOptions](#payment_options)
* [Amount12](#amount12)
* [Payer](#payer)
* [Payment Request](#payment_request)
* [Transaction](#transaction)
* [Details](#details)
* [Item](#item)
* [Payment Response](#payment_response)
* [Transaction12](#transaction12)
* [Item17](#item17)
* [PayerInfo](#payer_info)
* [Execute Response](#execute_response)
* [ShippingAddress](#shipping_address)
* [Order](#order)
## <a name="amount"></a>![Type: ](https://apidocs.io/img/method.png "Amount") Amount



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| total | string |  ``` Required ```  | TODO: Add a property description | 
| currency | string |  ``` Required ```  | TODO: Add a property description | 
| details | [Details](#details) |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "total": "total",
  "currency": "currency",
  "details": {
    "subtotal": "subtotal",
    "tax": "tax",
    "shipping": "shipping",
    "handling_fee": "handling_fee",
    "shipping_discount": "shipping_discount",
    "insurance": "insurance"
  }
}
```



## <a name="link"></a>![Type: ](https://apidocs.io/img/method.png "Link") Link



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| href | string |  ``` Required ```  | TODO: Add a property description | 
| rel | string |  ``` Required ```  | TODO: Add a property description | 
| method | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "href": "href",
  "rel": "rel",
  "method": "method"
}
```



## <a name="item_list16"></a>![Type: ](https://apidocs.io/img/method.png "ItemList16") ItemList16



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| items | [Item17](#item17) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 
| shipping_address | [ShippingAddress](#shipping_address) |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "items": [
    {
      "name": "name",
      "sku": "sku",
      "description": "description",
      "price": "price",
      "currency": "currency",
      "tax": "tax",
      "quantity": 201
    }
  ],
  "shipping_address": {
    "line1": "line1",
    "line2": "line2",
    "city": "city",
    "state": "state",
    "postal_code": "postal_code",
    "country_code": "country_code",
    "phone": "phone",
    "recipient_name": "recipient_name"
  }
}
```



## <a name="payment_options15"></a>![Type: ](https://apidocs.io/img/method.png "PaymentOptions15") PaymentOptions15



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| allowed_payment_method | string |  ``` Required ```  | TODO: Add a property description | 
| recurring_flag | boolean |  ``` Required ```  | TODO: Add a property description | 
| skip_fmf | boolean |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "allowed_payment_method": "allowed_payment_method",
  "recurring_flag": true,
  "skip_fmf": true
}
```



## <a name="redirect_urls"></a>![Type: ](https://apidocs.io/img/method.png "RedirectUrls") RedirectUrls



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| return_url | string |  ``` Required ```  | TODO: Add a property description | 
| cancel_url | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "return_url": "return_url",
  "cancel_url": "cancel_url"
}
```



## <a name="item_list"></a>![Type: ](https://apidocs.io/img/method.png "ItemList") ItemList



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| items | [Item](#item) |  ``` Required ```  ``` Collection ```  | The item details. | 
| shipping_address | [ShippingAddress](#shipping_address) |  ``` Required ```  | The shipping address. | 



#### Example
```
{
  "items": [
    {
      "name": "name",
      "description": "description",
      "quantity": "quantity",
      "price": "price",
      "tax": "tax",
      "sku": "sku",
      "currency": "currency"
    }
  ],
  "shipping_address": {
    "line1": "line1",
    "line2": "line2",
    "city": "city",
    "state": "state",
    "postal_code": "postal_code",
    "country_code": "country_code",
    "phone": "phone",
    "recipient_name": "recipient_name"
  }
}
```



## <a name="related_resource"></a>![Type: ](https://apidocs.io/img/method.png "RelatedResource") RelatedResource



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| order | [Order](#order) |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "order": {
    "id": "id",
    "create_time": "create_time",
    "update_time": "update_time",
    "state": "state",
    "amount": {
      "total": "total",
      "currency": "currency"
    },
    "parent_payment": "parent_payment",
    "links": [
      {
        "href": "href",
        "rel": "rel",
        "method": "method"
      }
    ]
  }
}
```



## <a name="execute_request"></a>![Type: ](https://apidocs.io/img/method.png "Execute Request") Execute Request



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| payer_id | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
Bearer A21AAHdZ73bsQUjOrlAzfucLwq2janvn7EKS0heMUHLsurdS0aZLLGJMB4LC2MHo6SuXp0oDilSM4z4xsGpUwASDBW16BUbfw
```



## <a name="payment_options"></a>![Type: ](https://apidocs.io/img/method.png "PaymentOptions") PaymentOptions



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| allowed_payment_method | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "allowed_payment_method": "allowed_payment_method"
}
```



## <a name="amount12"></a>![Type: ](https://apidocs.io/img/method.png "Amount12") Amount12



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| total | string |  ``` Required ```  | TODO: Add a property description | 
| currency | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "total": "total",
  "currency": "currency"
}
```



## <a name="payer"></a>![Type: ](https://apidocs.io/img/method.png "Payer") Payer



> The source of the funds for this payment. Payment method is PayPal Wallet payment, bank direct debit, or direct credit card.





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| payment_method | string |  ``` Required ```  | The payment method. Possible values: credit_card, paypal. | 
| payer_info | string |  ``` Required ```  | The payer-related information. If the payment_method is paypal, you must set the email address of the PayPal account that funds the transaction in the payer_info. | 



#### Example
```
{
  "payment_method": "payment_method",
  "payer_info": "payer_info"
}
```



## <a name="payment_request"></a>![Type: ](https://apidocs.io/img/method.png "Payment Request") Payment Request



> Creates a PayPal payment.





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| intent | string |  ``` Required ```  | The payment intent. | 
| payer | [Payer](#payer) |  ``` Required ```  | The source of the funds for this payment. Payment method is PayPal Wallet payment, bank direct debit, or direct credit card. | 
| transactions | [Transaction](#transaction) |  ``` Required ```  ``` Collection ```  | An array of payment-related transactions. A transaction defines what the payment is for and who fulfills the payment. | 
| note_to_payer | string |  ``` Required ```  | TODO: Add a property description | 
| redirect_urls | [RedirectUrls](#redirect_urls) |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "intent": "sale",
  "payer": {
    "payment_method": "paypal"
  },
  "transactions": [
    {
      "amount": {
        "total": "30.11",
        "currency": "USD",
        "details": {
          "subtotal": "30.00",
          "tax": "0.07",
          "shipping": "0.03",
          "handling_fee": "1.00",
          "shipping_discount": "-1.00",
          "insurance": "0.01"
        }
      },
      "description": "The payment transaction description.",
      "custom": "EBAY_EMS_90048630024435",
      "invoice_number": "48787589673",
      "payment_options": {
        "allowed_payment_method": "INSTANT_FUNDING_SOURCE"
      },
      "soft_descriptor": "ECHI5786786",
      "item_list": {
        "items": [
          {
            "name": "hat",
            "description": "Brown hat.",
            "quantity": "5",
            "price": "3",
            "tax": "0.01",
            "sku": "1",
            "currency": "USD"
          },
          {
            "name": "handbag",
            "description": "Black handbag.",
            "quantity": "1",
            "price": "15",
            "tax": "0.02",
            "sku": "product34",
            "currency": "USD"
          }
        ],
        "shipping_address": {
          "recipient_name": "Brian Robinson",
          "line1": "4th Floor",
          "line2": "Unit #34",
          "city": "San Jose",
          "country_code": "US",
          "postal_code": "95131",
          "phone": "011862212345678",
          "state": "CA"
        }
      }
    }
  ],
  "note_to_payer": "Contact us for any questions on your order.",
  "redirect_urls": {
    "return_url": "https://sandbox.paypal.com",
    "cancel_url": "https://sandbox.paypal.com"
  }
}
```



## <a name="transaction"></a>![Type: ](https://apidocs.io/img/method.png "Transaction") Transaction



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| amount | [Amount](#amount) |  ``` Required ```  | The amount to collect. | 
| description | string |  ``` Required ```  | The description of what is being paid for. | 
| custom | string |  ``` Required ```  | A free-form field for clients' use. | 
| invoice_number | string |  ``` Required ```  | The invoice number to track this payment. | 
| payment_options | [PaymentOptions](#payment_options) |  ``` Required ```  | The payment options requested for this transaction. | 
| soft_descriptor | string |  ``` Required ```  | The soft descriptor that is used when charging this funding source. If the string's length is greater than the maximum allowed length, the string is truncated. | 
| item_list | [ItemList](#item_list) |  ``` Required ```  | The list of items being paid for. | 



#### Example
```
{
  "amount": {
    "total": "total",
    "currency": "currency",
    "details": {
      "subtotal": "subtotal",
      "tax": "tax",
      "shipping": "shipping",
      "handling_fee": "handling_fee",
      "shipping_discount": "shipping_discount",
      "insurance": "insurance"
    }
  },
  "description": "description",
  "custom": "custom",
  "invoice_number": "invoice_number",
  "payment_options": {
    "allowed_payment_method": "allowed_payment_method"
  },
  "soft_descriptor": "soft_descriptor",
  "item_list": {
    "items": [
      {
        "name": "name",
        "description": "description",
        "quantity": "quantity",
        "price": "price",
        "tax": "tax",
        "sku": "sku",
        "currency": "currency"
      }
    ],
    "shipping_address": {
      "line1": "line1",
      "line2": "line2",
      "city": "city",
      "state": "state",
      "postal_code": "postal_code",
      "country_code": "country_code",
      "phone": "phone",
      "recipient_name": "recipient_name"
    }
  }
}
```



## <a name="details"></a>![Type: ](https://apidocs.io/img/method.png "Details") Details



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| subtotal | string |  ``` Required ```  | TODO: Add a property description | 
| tax | string |  ``` Required ```  | TODO: Add a property description | 
| shipping | string |  ``` Required ```  | TODO: Add a property description | 
| handling_fee | string |  ``` Required ```  | TODO: Add a property description | 
| shipping_discount | string |  ``` Required ```  | TODO: Add a property description | 
| insurance | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "subtotal": "subtotal",
  "tax": "tax",
  "shipping": "shipping",
  "handling_fee": "handling_fee",
  "shipping_discount": "shipping_discount",
  "insurance": "insurance"
}
```



## <a name="item"></a>![Type: ](https://apidocs.io/img/method.png "Item") Item



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| name | string |  ``` Required ```  | The item name. | 
| description | string |  ``` Required ```  | The item description. Supported for the PayPal payment method only. | 
| quantity | string |  ``` Required ```  | The item quantity. | 
| price | string |  ``` Required ```  | The item cost. | 
| tax | string |  ``` Required ```  | The item tax. Supported for the PayPal payment method only. | 
| sku | string |  ``` Required ```  | The stock keeping unit (SKU) for the item. | 
| currency | string |  ``` Required ```  | The three-character ISO-4217 currency code. | 



#### Example
```
{
  "name": "name",
  "description": "description",
  "quantity": "quantity",
  "price": "price",
  "tax": "tax",
  "sku": "sku",
  "currency": "currency"
}
```



## <a name="payment_response"></a>![Type: ](https://apidocs.io/img/method.png "Payment Response") Payment Response



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| id | string |  ``` Required ```  | TODO: Add a property description | 
| intent | string |  ``` Required ```  | TODO: Add a property description | 
| state | string |  ``` Required ```  | TODO: Add a property description | 
| payer | [Payer](#payer) |  ``` Required ```  | TODO: Add a property description | 
| transactions | [Transaction12](#transaction12) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 
| note_to_payer | string |  ``` Required ```  | TODO: Add a property description | 
| create_time | string |  ``` Required ```  | TODO: Add a property description | 
| links | [Link](#link) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 



#### Example
```
{
  "id": "id",
  "intent": "intent",
  "state": "state",
  "payer": {
    "payment_method": "payment_method",
    "payer_info": "payer_info"
  },
  "transactions": [
    {
      "amount": {
        "total": "total",
        "currency": "currency",
        "details": {
          "subtotal": "subtotal",
          "tax": "tax",
          "shipping": "shipping",
          "handling_fee": "handling_fee",
          "shipping_discount": "shipping_discount",
          "insurance": "insurance"
        }
      },
      "description": "description",
      "custom": "custom",
      "invoice_number": "invoice_number",
      "soft_descriptor": "soft_descriptor",
      "payment_options": {
        "allowed_payment_method": "allowed_payment_method",
        "recurring_flag": true,
        "skip_fmf": true
      },
      "item_list": {
        "items": [
          {
            "name": "name",
            "sku": "sku",
            "description": "description",
            "price": "price",
            "currency": "currency",
            "tax": "tax",
            "quantity": 201
          }
        ],
        "shipping_address": {
          "line1": "line1",
          "line2": "line2",
          "city": "city",
          "state": "state",
          "postal_code": "postal_code",
          "country_code": "country_code",
          "phone": "phone",
          "recipient_name": "recipient_name"
        }
      },
      "related_resources": [
        "related_resources"
      ]
    }
  ],
  "note_to_payer": "note_to_payer",
  "create_time": "create_time",
  "links": [
    {
      "href": "href",
      "rel": "rel",
      "method": "method"
    }
  ]
}
```



## <a name="transaction12"></a>![Type: ](https://apidocs.io/img/method.png "Transaction12") Transaction12



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| amount | [Amount](#amount) |  ``` Required ```  | TODO: Add a property description | 
| description | string |  ``` Required ```  | TODO: Add a property description | 
| custom | string |  ``` Required ```  | TODO: Add a property description | 
| invoice_number | string |  ``` Required ```  | TODO: Add a property description | 
| soft_descriptor | string |  ``` Required ```  | TODO: Add a property description | 
| payment_options | [PaymentOptions15](#payment_options15) |  ``` Required ```  | TODO: Add a property description | 
| item_list | [ItemList16](#item_list16) |  ``` Required ```  | TODO: Add a property description | 
| related_resources | string |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 



#### Example
```
{
  "amount": {
    "total": "total",
    "currency": "currency",
    "details": {
      "subtotal": "subtotal",
      "tax": "tax",
      "shipping": "shipping",
      "handling_fee": "handling_fee",
      "shipping_discount": "shipping_discount",
      "insurance": "insurance"
    }
  },
  "description": "description",
  "custom": "custom",
  "invoice_number": "invoice_number",
  "soft_descriptor": "soft_descriptor",
  "payment_options": {
    "allowed_payment_method": "allowed_payment_method",
    "recurring_flag": true,
    "skip_fmf": true
  },
  "item_list": {
    "items": [
      {
        "name": "name",
        "sku": "sku",
        "description": "description",
        "price": "price",
        "currency": "currency",
        "tax": "tax",
        "quantity": 201
      }
    ],
    "shipping_address": {
      "line1": "line1",
      "line2": "line2",
      "city": "city",
      "state": "state",
      "postal_code": "postal_code",
      "country_code": "country_code",
      "phone": "phone",
      "recipient_name": "recipient_name"
    }
  },
  "related_resources": [
    "related_resources"
  ]
}
```



## <a name="item17"></a>![Type: ](https://apidocs.io/img/method.png "Item17") Item17



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| name | string |  ``` Required ```  | TODO: Add a property description | 
| sku | string |  ``` Required ```  | TODO: Add a property description | 
| description | string |  ``` Required ```  | TODO: Add a property description | 
| price | string |  ``` Required ```  | TODO: Add a property description | 
| currency | string |  ``` Required ```  | TODO: Add a property description | 
| tax | string |  ``` Required ```  | TODO: Add a property description | 
| quantity | number |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "name": "name",
  "sku": "sku",
  "description": "description",
  "price": "price",
  "currency": "currency",
  "tax": "tax",
  "quantity": 201
}
```



## <a name="payer_info"></a>![Type: ](https://apidocs.io/img/method.png "PayerInfo") PayerInfo



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| email | string |  ``` Required ```  | TODO: Add a property description | 
| first_name | string |  ``` Required ```  | TODO: Add a property description | 
| last_name | string |  ``` Required ```  | TODO: Add a property description | 
| payer_id | string |  ``` Required ```  | TODO: Add a property description | 
| shipping_address | [ShippingAddress](#shipping_address) |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "email": "email",
  "first_name": "first_name",
  "last_name": "last_name",
  "payer_id": "payer_id",
  "shipping_address": {
    "line1": "line1",
    "line2": "line2",
    "city": "city",
    "state": "state",
    "postal_code": "postal_code",
    "country_code": "country_code",
    "phone": "phone",
    "recipient_name": "recipient_name"
  }
}
```



## <a name="execute_response"></a>![Type: ](https://apidocs.io/img/method.png "Execute Response") Execute Response



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| id | string |  ``` Required ```  | TODO: Add a property description | 
| create_time | string |  ``` Required ```  | TODO: Add a property description | 
| update_time | string |  ``` Required ```  | TODO: Add a property description | 
| state | string |  ``` Required ```  | TODO: Add a property description | 
| intent | string |  ``` Required ```  | TODO: Add a property description | 
| payer | [Payer](#payer) |  ``` Required ```  | TODO: Add a property description | 
| transactions | [Transaction](#transaction) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 
| links | [Link](#link) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 



#### Example
```
{
  "id": "id",
  "create_time": "create_time",
  "update_time": "update_time",
  "state": "state",
  "intent": "intent",
  "payer": {
    "payment_method": "payment_method",
    "payer_info": "payer_info"
  },
  "transactions": [
    {
      "amount": {
        "total": "total",
        "currency": "currency",
        "details": {
          "subtotal": "subtotal",
          "tax": "tax",
          "shipping": "shipping",
          "handling_fee": "handling_fee",
          "shipping_discount": "shipping_discount",
          "insurance": "insurance"
        }
      },
      "description": "description",
      "custom": "custom",
      "invoice_number": "invoice_number",
      "payment_options": {
        "allowed_payment_method": "allowed_payment_method"
      },
      "soft_descriptor": "soft_descriptor",
      "item_list": {
        "items": [
          {
            "name": "name",
            "description": "description",
            "quantity": "quantity",
            "price": "price",
            "tax": "tax",
            "sku": "sku",
            "currency": "currency"
          }
        ],
        "shipping_address": {
          "line1": "line1",
          "line2": "line2",
          "city": "city",
          "state": "state",
          "postal_code": "postal_code",
          "country_code": "country_code",
          "phone": "phone",
          "recipient_name": "recipient_name"
        }
      }
    }
  ],
  "links": [
    {
      "href": "href",
      "rel": "rel",
      "method": "method"
    }
  ]
}
```



## <a name="shipping_address"></a>![Type: ](https://apidocs.io/img/method.png "ShippingAddress") ShippingAddress



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| line1 | string |  ``` Required ```  | TODO: Add a property description | 
| line2 | string |  ``` Required ```  | TODO: Add a property description | 
| city | string |  ``` Required ```  | TODO: Add a property description | 
| state | string |  ``` Required ```  | TODO: Add a property description | 
| postal_code | string |  ``` Required ```  | TODO: Add a property description | 
| country_code | string |  ``` Required ```  | TODO: Add a property description | 
| phone | string |  ``` Required ```  | TODO: Add a property description | 
| recipient_name | string |  ``` Required ```  | TODO: Add a property description | 



#### Example
```
{
  "line1": "line1",
  "line2": "line2",
  "city": "city",
  "state": "state",
  "postal_code": "postal_code",
  "country_code": "country_code",
  "phone": "phone",
  "recipient_name": "recipient_name"
}
```



## <a name="order"></a>![Type: ](https://apidocs.io/img/method.png "Order") Order



> TODO: Add a model description





| Name | Type | Tags | Description |
|-----------|------| ---- |-------------| 
| id | string |  ``` Required ```  | TODO: Add a property description | 
| create_time | string |  ``` Required ```  | TODO: Add a property description | 
| update_time | string |  ``` Required ```  | TODO: Add a property description | 
| state | string |  ``` Required ```  | TODO: Add a property description | 
| amount | [Amount12](#amount12) |  ``` Required ```  | TODO: Add a property description | 
| parent_payment | string |  ``` Required ```  | TODO: Add a property description | 
| links | [Link](#link) |  ``` Required ```  ``` Collection ```  | TODO: Add a property description | 



#### Example
```
{
  "id": "id",
  "create_time": "create_time",
  "update_time": "update_time",
  "state": "state",
  "amount": {
    "total": "total",
    "currency": "currency"
  },
  "parent_payment": "parent_payment",
  "links": [
    {
      "href": "href",
      "rel": "rel",
      "method": "method"
    }
  ]
}
```




