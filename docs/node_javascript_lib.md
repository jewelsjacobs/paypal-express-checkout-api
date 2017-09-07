# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated SDK relies on [Node Package Manager](https://www.npmjs.com/) (NPM) being available to resolve dependencies. If you don't already have NPM installed, please go ahead and follow instructions to install NPM from [here](https://nodejs.org/en/download/).
The SDK also requires Node to be installed. If Node isn't already installed, please install it from [here](https://nodejs.org/en/download/)
> NPM is installed by default when Node is installed

To check if node and npm have been successfully installed, write the following commands in command prompt:

* `node --version`
* `npm -version`

![Version Check](https://apidocs.io/illustration/nodejs?step=versionCheck&workspaceFolder=PayPal%20Express%20Checkout-Node)

Now use npm to resolve all dependencies by running the following command in the root directory (of the SDK folder):

```bash
npm install
```

![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency1&workspaceFolder=PayPal%20Express%20Checkout-Node)

![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency2)

This will install all dependencies in the `node_modules` folder.

Once dependencies are resolved, you will need to move the folder `PayPalExpressCheckoutLib ` in to your `node_modules` folder.

## How to Use

The following section explains how to use the library in a new project.

### 1. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

Click on `File` and select `Open Folder`.

![Open Folder](https://apidocs.io/illustration/nodejs?step=openFolder)

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![Open Project](https://apidocs.io/illustration/nodejs?step=openProject&workspaceFolder=PayPal%20Express%20Checkout-Node)

### 2. Creating a Test File

Now right click on the folder name and select the `New File` option to create a new test file. Save it as `index.js` Now import the generated NodeJS library using the following lines of code:

```js
var lib = require('lib');
```

Save changes.

![Create new file](https://apidocs.io/illustration/nodejs?step=createNewFile&workspaceFolder=PayPal%20Express%20Checkout-Node)

![Save new file](https://apidocs.io/illustration/nodejs?step=saveNewFile&workspaceFolder=PayPal%20Express%20Checkout-Node)

### 3. Running The Test File

To run the `index.js` file, open up the command prompt and navigate to the Path where the SDK folder resides. Type the following command to run the file:

```
node index.js
```

![Run file](https://apidocs.io/illustration/nodejs?step=runProject&workspaceFolder=PayPal%20Express%20Checkout-Node)


## How to Test

These tests use Mocha framework for testing, coupled with Chai for assertions. These dependencies need to be installed for tests to run.
Tests can be run in a number of ways:

### Method 1 (Run all tests)

1. Navigate to the root directory of the SDK folder from command prompt.
2. Type `mocha --recursive` to run all the tests.

### Method 2 (Run all tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha *` to run all the tests.

### Method 3 (Run specific controller's tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha  PayPal Express CheckoutController`  to run all the tests in that controller file.

> To increase mocha's default timeout, you can change the `TEST_TIMEOUT` parameter's value in `TestBootstrap.js`.

![Run Tests](https://apidocs.io/illustration/nodejs?step=runTests&controllerName=PayPal%20Express%20CheckoutController)

## Initialization

### Authentication
In order to setup authentication in the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following:

```JavaScript
const lib = require('lib');

// Configuration parameters and credentials
lib.Configuration.clientId = "AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"; // client id
lib.Configuration.clientSecret = "EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"; // client secret
lib.Configuration.oAuthAccessToken = "oAuthAccessToken"; // OAuth 2.0 Access Token

```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed from the API Client.

```javascript
var controller = lib.PaymentController;
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.createExecute") createExecute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```javascript
function createExecute(input, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |



#### Example Usage

```javascript

    var input = [];
        input['body'] = new ExecuteRequestModel({"key":"value"});
        input['paymentId'] = payment_id;

    controller.createExecute(input, function(error, response, context) {

    
    });
```



### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create") create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```javascript
function create(body, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |



#### Example Usage

```javascript

    var body = new PaymentRequestModel({"key":"value"});

    controller.create(body, function(error, response, context) {

    
    });
```



[Back to List of Controllers](#list_of_controllers)



