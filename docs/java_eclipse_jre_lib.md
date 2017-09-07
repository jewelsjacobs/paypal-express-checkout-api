# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated code uses a few Maven dependencies e.g., Jackson, UniRest,
and Apache HttpClient. The reference to these dependencies is already
added in the pom.xml file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Eclipse click on ``` File -> Import ```.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/java?step=import0&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

* In the import dialog, select ``` Existing Java Project ``` and click ``` Next ```.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/java?step=import1&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

* Browse to locate the folder containing the source code. Select the detected location of the project and click ``` Finish ```.

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/java?step=import2&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

* Upon successful import, the project will be automatically built by Eclipse after automatically resolving the dependencies.

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/java?step=import3&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

## How to Use

The following section explains how to use the PayPalExpressCheckout library in a new console project.

### 1. Starting a new project

For starting a new project, click the menu command ``` File > New > Project ```.

![Add a new project in Eclipse](https://apidocs.io/illustration/java?step=createNewProject0&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Next, choose ``` Maven > Maven Project ```and click ``` Next ```.

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/java?step=createNewProject1&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Here, make sure to use the current workspace by choosing ``` Use default Workspace location ```, as shown in the picture below and click ``` Next ```.

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/java?step=createNewProject2&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Following this, select the *quick start* project type to create a simple project with an existing class and a ``` main ``` method. To do this, choose ``` maven-archetype-quickstart ``` item from the list and click ``` Next ```.

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/java?step=createNewProject3&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

In the last step, provide a ``` Group Id ``` and ``` Artifact Id ``` as shown in the picture below and click ``` Finish ```.

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/java?step=createNewProject4&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

### 2. Add reference of the library project

The created Maven project manages its dependencies using its ``` pom.xml ``` file. In order to add a dependency on the *PayPalExpressCheckoutLib* client library, double click on the ``` pom.xml ``` file in the ``` Package Explorer ```. Opening the ``` pom.xml ``` file will render a graphical view on the cavas. Here, switch to the ``` Dependencies ``` tab and click the ``` Add ``` button as shown in the picture below.

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/java?step=testProject0&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Clicking the ``` Add ``` button will open a dialog where you need to specify PayPalExpressCheckout in ``` Group Id ``` and PayPalExpressCheckoutLib in the ``` Artifact Id ``` fields. Once added click ``` OK ```. Save the ``` pom.xml ``` file.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/java?step=testProject1&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

### 3. Write sample code

Once the ``` SimpleConsoleApp ``` is created, a file named ``` App.java ``` will be visible in the *Package Explorer* with a ``` main ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/java?step=testProject2&workspaceFolder=PayPal%20Express%20Checkout-Java&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Eclipse, for running the tests do the following:

1. Select the project *PayPalExpressCheckoutLib* from the package explorer.
2. Select "Run -> Run as -> JUnit Test" or use "Alt + Shift + X" followed by "T" to run the Tests.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following.

```java
// Configuration parameters and credentials
String clientId = "AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"; // client id
String clientSecret = "EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"; // client secret
String oAuthAccessToken = "oAuthAccessToken"; // OAuth 2.0 Access Token

PayPalExpressCheckoutClient client = new PayPalExpressCheckoutClient(clientId, clientSecret, oAuthAccessToken);
```


# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.paypal.sandbox.api.controllers.PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed from the API Client.

```java
PaymentController payment = client.getPayment();
```

### <a name="create_execute_async"></a>![Method: ](https://apidocs.io/img/method.png "com.paypal.sandbox.api.controllers.PaymentController.createExecuteAsync") createExecuteAsync

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```java
void createExecuteAsync(
        final CreateExecuteInput input,
        final APICallBack<ExecuteResponseModel> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |


#### Example Usage

```java
try {
CreateExecuteInput collect = new CreateExecuteInput();

    ExecuteRequestModel body = new ExecuteRequestModel();
collect.setBody(body);

    String paymentId = "payment_id";
collect.setPaymentId(paymentId);

    // Invoking the API call with sample inputs
    payment.createExecuteAsync(collect, new APICallBack<ExecuteResponseModel>() {
        public void onSuccess(HttpContext context, ExecuteResponseModel response) {
            // TODO success callback handler
        }
        public void onFailure(HttpContext context, Throwable error) {
            // TODO failure callback handler
        }
    }
);
} catch(JsonProcessingException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}
```


### <a name="create_async"></a>![Method: ](https://apidocs.io/img/method.png "com.paypal.sandbox.api.controllers.PaymentController.createAsync") createAsync

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```java
void createAsync(
        final PaymentRequestModel body,
        final APICallBack<PaymentResponseModel> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |


#### Example Usage

```java
try {
    PaymentRequestModel body = new PaymentRequestModel();
    // Invoking the API call with sample inputs
    payment.createAsync(body, new APICallBack<PaymentResponseModel>() {
        public void onSuccess(HttpContext context, PaymentResponseModel response) {
            // TODO success callback handler
        }
        public void onFailure(HttpContext context, Throwable error) {
            // TODO failure callback handler
        }
    });
} catch(JsonProcessingException e) {
    // TODO Auto-generated catch block
    e.printStackTrace();
}
```


[Back to List of Controllers](#list_of_controllers)



