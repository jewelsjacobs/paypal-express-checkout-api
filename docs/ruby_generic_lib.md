# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

This client library is a Ruby gem which can be compiled and used in your Ruby and Ruby on Rails project. This library requires a few gems from the RubyGems repository.

1. Open the command line interface or the terminal and navigate to the folder containing the source code.
2. Run ``` gem build pay_pal_express_checkout.gemspec ``` to build the gem.
3. Once built, the gem can be installed on the current work environment using ``` gem install pay_pal_express_checkout-1.0.0.gem ```

![Building Gem](https://apidocs.io/illustration/ruby?step=buildSDK&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPal%20Express%20Checkout-Ruby&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

## How to Use

The following section explains how to use the PayPalExpressCheckout Ruby Gem in a new Rails project using RubyMine&trade;. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

### 1. Starting a new project

Close any existing projects in RubyMine&trade; by selecting ``` File -> Close Project ```. Next, click on ``` Create New Project ``` to create a new project from scratch.

![Create a new project in RubyMine](https://apidocs.io/illustration/ruby?step=createNewProject0&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

Next, provide ``` TestApp ``` as the project name, choose ``` Rails Application ``` as the project type, and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 1](https://apidocs.io/illustration/ruby?step=createNewProject1&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

In the next dialog make sure that correct *Ruby SDK* is being used (minimum 2.0.0) and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 2](https://apidocs.io/illustration/ruby?step=createNewProject2&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

This will create a new Rails Application project with an existing set of files and folder.

### 2. Add reference of the gem

In order to use the PayPalExpressCheckout gem in the new project we must add a gem reference. Locate the ```Gemfile``` in the *Project Explorer* window under the ``` TestApp ``` project node. The file contains references to all gems being used in the project. Here, add the reference to the library gem by adding the following line: ``` gem 'pay_pal_express_checkout', '~> 1.0.0' ```

![Add references of the Gemfile](https://apidocs.io/illustration/ruby?step=addReference&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

### 3. Adding a new Rails Controller

Once the ``` TestApp ``` project is created, a folder named ``` controllers ``` will be visible in the *Project Explorer* under the following path: ``` TestApp > app > controllers ```. Right click on this folder and select ``` New -> Run Rails Generator... ```.

![Run Rails Generator on Controllers Folder](https://apidocs.io/illustration/ruby?step=addCode0&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

Selecting the said option will popup a small window where the generator names are displayed. Here, select the ``` controller ``` template.

![Create a new Controller](https://apidocs.io/illustration/ruby?step=addCode1&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

Next, a popup window will ask you for a Controller name and included Actions. For controller name provide ``` Hello ``` and include an action named ``` Index ``` and click ``` OK ```.

![Add a new Controller](https://apidocs.io/illustration/ruby?step=addCode2&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

A new controller class anmed ``` HelloController ``` will be created in a file named ``` hello_controller.rb ``` containing a method named ``` Index ```. In this method, add code for initialization and a sample for its usage.

![Initialize the library](https://apidocs.io/illustration/ruby?step=addCode3&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0)

## How to Test

You can test the generated SDK and the server with automatically generated test
cases as follows:

  1. From terminal/cmd navigate to the root directory of the SDK.
  2. Invoke: `bundle exec rake`

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| client_id | client id |
| client_secret | client secret |
| o_auth_access_token | OAuth 2.0 Access Token |



API client can be initialized as following.

```ruby
# Configuration parameters and credentials
client_id = 'AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9' # client id
client_secret = 'EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd' # client secret
o_auth_access_token = 'o_auth_access_token' # OAuth 2.0 Access Token

client = PayPalExpressCheckout::PayPalExpressCheckoutClient.new(
  client_id: client_id,
  client_secret: client_secret,
  o_auth_access_token: o_auth_access_token
)
```

The added initlization code can be debugged by putting a breakpoint in the ``` Index ``` method and running the project in debug mode by selecting ``` Run -> Debug 'Development: TestApp' ```.

![Debug the TestApp](https://apidocs.io/illustration/ruby?step=addCode4&workspaceFolder=PayPal%20Express%20Checkout-Ruby&workspaceName=PayPalExpressCheckout&projectName=pay_pal_express_checkout&gemName=pay_pal_express_checkout&gemVer=1.0.0&initLine=client%2520%253D%2520PayPalExpressCheckoutClient.new%2528%2527client_id%2527%252C%2520%2527client_secret%2527%252C%2520%2527o_auth_access_token%2527%2529)



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed from the API Client.

```ruby
payment = client.payment
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create_execute") create_execute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```ruby
def create_execute(options = Hash.new); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| payment_id |  ``` Required ```  | The ID of the payment to execute. |


#### Example Usage

```ruby
collect = Hash.new

body = ExecuteRequestModel.new
collect['body'] = body

payment_id = 'payment_id'
collect['payment_id'] = payment_id


result = payment.create_execute(collect)

```


### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create") create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```ruby
def create(body); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |


#### Example Usage

```ruby
body = PaymentRequestModel.new

result = payment.create(body)

```


[Back to List of Controllers](#list_of_controllers)



