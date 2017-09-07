# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated code uses the Newtonsoft Json.NET NuGet Package. If the automatic NuGet package restore
is enabled, these dependencies will be installed automatically. Therefore,
you will need internet access for build.

1. Open the solution (PayPalExpressCheckout.sln) file.
2. Invoke the build process using `Ctrl+Shift+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Visual Studio](https://apidocs.io/illustration/cs?step=buildSDK&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

## How to Use

The build process generates a portable class library, which can be used like a normal class library. The generated library is compatible with Windows Forms, Windows RT, Windows Phone 8,
Silverlight 5, Xamarin iOS, Xamarin Android and Mono. More information on how to use can be found at the [MSDN Portable Class Libraries documentation](http://msdn.microsoft.com/en-us/library/vstudio/gg597391%28v=vs.100%29.aspx).

The following section explains how to use the PayPalExpressCheckout library in a new console project.

### 1. Starting a new project

For starting a new project, right click on the current solution from the *solution explorer* and choose  ``` Add -> New Project ```.

![Add a new project in the existing solution using Visual Studio](https://apidocs.io/illustration/cs?step=addProject&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

Next, choose "Console Application", provide a ``` TestConsoleProject ``` as the project name and click ``` OK ```.

![Create a new console project using Visual Studio](https://apidocs.io/illustration/cs?step=createProject&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

### 2. Set as startup project

The new console project is the entry point for the eventual execution. This requires us to set the ``` TestConsoleProject ``` as the start-up project. To do this, right-click on the  ``` TestConsoleProject ``` and choose  ``` Set as StartUp Project ``` form the context menu.

![Set the new cosole project as the start up project](https://apidocs.io/illustration/cs?step=setStartup&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

### 3. Add reference of the library project

In order to use the PayPalExpressCheckout library in the new project, first we must add a projet reference to the ``` TestConsoleProject ```. First, right click on the ``` References ``` node in the *solution explorer* and click ``` Add Reference... ```.

![Open references of the TestConsoleProject](https://apidocs.io/illustration/cs?step=addReference&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

Next, a window will be displayed where we must set the ``` checkbox ``` on ``` PayPalExpressCheckout.PCL ``` and click ``` OK ```. By doing this, we have added a reference of the ```PayPalExpressCheckout.PCL``` project into the new ``` TestConsoleProject ```.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=createReference&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

### 4. Write sample code

Once the ``` TestConsoleProject ``` is created, a file named ``` Program.cs ``` will be visible in the *solution explorer* with an empty ``` Main ``` method. This is the entry point for the execution of the entire solution.
Here, you can add code to initialize the client library and acquire the instance of a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Add a reference to the TestConsoleProject](https://apidocs.io/illustration/cs?step=addCode&workspaceFolder=PayPal%20Express%20Checkout-CSharp&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckout.PCL)

## How to Test

The generated SDK also contain one or more Tests, which are contained in the Tests project.
In order to invoke these test cases, you will need *NUnit 3.0 Test Adapter Extension for Visual Studio*.
Once the SDK is complied, the test cases should appear in the Test Explorer window.
Here, you can click *Run All* to execute these test cases.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following.

```csharp
// Configuration parameters and credentials
string clientId = "AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"; // client id
string clientSecret = "EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"; // client secret
string oAuthAccessToken = "oAuthAccessToken"; // OAuth 2.0 Access Token

PayPalExpressCheckoutClient client = new PayPalExpressCheckoutClient(clientId, clientSecret, oAuthAccessToken);
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png "expresscheckout.Controllers.PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed from the API Client.

```csharp
IPaymentController payment = client.Payment;
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png "expresscheckout.Controllers.PaymentController.CreateExecute") CreateExecute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```csharp
Task<Models.ExecuteResponseModel> CreateExecute(Models.CreateExecuteInput input)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |


#### Example Usage

```csharp
CreateExecuteInput collect = new CreateExecuteInput();

var body = new Models.ExecuteRequestModel();
collect.Body = body;

string paymentId = "payment_id";
collect.PaymentId = paymentId;


Models.ExecuteResponseModel result = await payment.CreateExecute(collect);

```


### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png "expresscheckout.Controllers.PaymentController.Create") Create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```csharp
Task<Models.PaymentResponseModel> Create(Models.PaymentRequestModel body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |


#### Example Usage

```csharp
var body = new Models.PaymentRequestModel();

Models.PaymentResponseModel result = await payment.Create(body);

```


[Back to List of Controllers](#list_of_controllers)



