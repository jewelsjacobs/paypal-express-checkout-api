# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build


The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```PodFile``` file that comes with the SDK. 
To resolve these dependencies, we use the Cocoapods package manager.
Visit https://guides.cocoapods.org/using/getting-started.html to setup Cocoapods on your system.
Open command prompt and type ```pod --version```. This should display the current version of Cocoapods installed if the installation was successful.

Using command line, navigate to the directory containing the generated files (including ```PodFile```) for the SDK. 
Run the command ```pod install```. This should install all the required dependencies and create the ```pods``` directory in your project directory.

![Installing dependencies using Cocoapods](https://apidocs.io/illustration/objc?step=AddDependencies&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Open the project workspace using the (PayPalExpressCheckout.xcworkspace) file. Invoke the build process using `Command(⌘)+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Xcode](https://apidocs.io/illustration/objc?step=BuildSDK&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)


## How to Use

The generated code is a Cocoa Touch Static Library which can be used in any iOS project. The support for these generated libraries go all the way back to iOS 6.

The following section explains how to use the PayPalExpressCheckout library in a new iOS project.     
### 1. Starting a new project
To start a new project, left-click on the ```Create a new Xcode project```.
![Create Test Project - Step 1](https://apidocs.io/illustration/objc?step=Test1&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Next, choose **Single View Application** and click ```Next```.
![Create Test Project - Step 2](https://apidocs.io/illustration/objc?step=Test2&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Provide **Test-Project** as the product name click ```Next```.
![Create Test Project - Step 3](https://apidocs.io/illustration/objc?step=Test3&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Choose the desired location of your project folder and click ```Create```.
![Create Test Project - Step 4](https://apidocs.io/illustration/objc?step=Test4&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

### 2. Adding the static library dependency
To add this dependency open a terminal and navigate to your project folder. Next, input ```pod init``` and press enter.
![Add dependency - Step 1](https://apidocs.io/illustration/objc?step=Add0&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Next, open the newly created ```PodFile``` in your favourite text editor. Add the following line : pod 'PayPalExpressCheckout', :path => 'Vendor/PayPalExpressCheckout'
![Add dependency - Step 2](https://apidocs.io/illustration/objc?step=Add1&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)

Execute `pod install` from terminal to install the dependecy in your project. This would add the dependency to the newly created test project.
![Add dependency - Step 3](https://apidocs.io/illustration/objc?step=Add2&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)


## How to Test

Unit tests in this SDK can be run using Xcode. 

First build the SDK as shown in the steps above and naivgate to the project directory and open the PayPalExpressCheckout.xcworkspace file.

Go to the test explorer in Xcode as shown in the picture below and click on `run tests` from the menu. 
![Run tests](https://apidocs.io/illustration/objc?step=RunTests&workspaceFolder=PayPal%20Express%20Checkout-ObjC&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout&rootNamespace=PayPalExpressCheckout)


## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



Configuration variables can be set as following.
```Objc
// Configuration parameters and credentials
Configuration_ClientId = "AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"; // client id
Configuration_ClientSecret = "EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"; // client secret
Configuration_OAuthAccessToken = "Configuration_OAuthAccessToken"; // OAuth 2.0 Access Token

```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get singleton instance
```objc
Payment* payment = [[Payment alloc]init] ;
```

### <a name="create_execute_async_with_create_execute_input"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.createExecuteAsyncWithCreateExecuteInput") createExecuteAsyncWithCreateExecuteInput

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```objc
function createExecuteAsyncWithCreateExecuteInput:(CreateExecuteInput*) input
                completionBlock:(CompletedPostExecute) onCompleted(input)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |





#### Example Usage

```objc
    // Parameters for the API call
    CreateExecuteInput *input = [[CreateExecuteInput alloc]init];
    input.body = [[ExecuteRequestModel alloc]init];
    input.paymentId = @"payment_id";

    [self.payment createExecuteAsyncWithCreateExecuteInput: input completionBlock:^(BOOL success, HttpContext* context, ExecuteResponseModel* response, NSError* error) { 
       //Add code here
    }];
```


### <a name="create_async_with_body"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.createAsyncWithBody") createAsyncWithBody

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```objc
function createAsyncWithBody:(PaymentRequestModel*) body
                completionBlock:(CompletedPostCreate) onCompleted(body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |





#### Example Usage

```objc
    // Parameters for the API call
    PaymentRequestModel* body = [[PaymentRequestModel alloc]init];

    [self.payment createAsyncWithBody: body  completionBlock:^(BOOL success, HttpContext* context, PaymentResponseModel* response, NSError* error) { 
       //Add code here
    }];
```


[Back to List of Controllers](#list_of_controllers)



