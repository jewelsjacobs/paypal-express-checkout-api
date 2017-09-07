# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```composer.json``` file that comes with the SDK. 
To resolve these dependencies, we use the Composer package manager which requires PHP greater than 5.3.2 installed in your system. 
Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. 
Open command prompt and type ```composer --version```. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including ```composer.json```) for the SDK. 
* Run the command ```composer install```. This should install all the required dependencies and create the ```vendor``` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?step=installDependencies&workspaceFolder=PayPal%20Express%20Checkout-PHP)

### [For Windows Users Only] Configuring CURL Certificate Path in php.ini

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```ini
[curl]
; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
;curl.cainfo =
```

## How to Use

The following section explains how to use the PayPalExpressCheckout library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=openIDE&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Click on ```Open``` in PhpStorm to browse to your generated SDK directory and then click ```OK```.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=openProject0&workspaceFolder=PayPal%20Express%20Checkout-PHP)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=createDirectory&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Name the directory as "test"

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=nameDirectory&workspaceFolder=PayPal%20Express%20Checkout-PHP)
   
Add a PHP file to this project

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?step=createFile&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Name it "testSDK"

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=nameFile&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```PHP
require_once "../vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file ```autoload.php``` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=projectFiles&workspaceFolder=PayPal%20Express%20Checkout-PHP)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open ```Settings``` from ```File``` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?step=openSettings&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Select ```PHP``` from within ```Languages & Frameworks```

![Run Test Project - Step 2](https://apidocs.io/illustration/php?step=setInterpreter0&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Browse for Interpreters near the ```Interpreter``` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?step=setInterpreter1&workspaceFolder=PayPal%20Express%20Checkout-PHP)

Once the interpreter is selected, click ```OK```

![Run Test Project - Step 4](https://apidocs.io/illustration/php?step=setInterpreter2&workspaceFolder=PayPal%20Express%20Checkout-PHP)

To run your project, right click on your PHP file inside your Test project and click on ```Run```

![Run Test Project - Step 5](https://apidocs.io/illustration/php?step=runProject&workspaceFolder=PayPal%20Express%20Checkout-PHP)

## How to Test

Unit tests in this SDK can be run using PHPUnit. 

1. First install the dependencies using composer including the `require-dev` dependencies.
2. Run `vendor\bin\phpunit --verbose` from commandline to execute tests. If you have 
   installed PHPUnit globally, run tests using `phpunit --verbose` instead.

You can change the PHPUnit test configuration in the `phpunit.xml` file.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following.

```php
$clientId = 'AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9'; // client id
$clientSecret = 'EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd'; // client secret
$oAuthAccessToken = 'oAuthAccessToken'; // OAuth 2.0 Access Token

$client = new PayPalExpressCheckoutLib\PayPalExpressCheckoutClient($clientId, $clientSecret, $oAuthAccessToken);
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed from the API Client.

```php
$payment = $client->getPayment();
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.createExecute") createExecute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```php
function createExecute($options)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |



#### Example Usage

```php
$body = new ExecuteRequestModel();
$collect['body'] = $body;

$paymentId = 'payment_id';
$collect['paymentId'] = $paymentId;


$result = $payment->createExecute($collect);

```


### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create") create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```php
function create($body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |



#### Example Usage

```php
$body = new PaymentRequestModel();

$result = $payment->create($body);

```


[Back to List of Controllers](#list_of_controllers)



