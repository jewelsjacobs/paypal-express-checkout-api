# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated code uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

* Browse to locate the folder containing the source code. Select the location of the PayPalExpressCheckout gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

## How to Use

The following section explains how to use the PayPalExpressCheckout library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Following this, select the `Phone and Tablet` option as shown in the illustration below and click `Next`.

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

In the following step naigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line ```compile project(path: ':PayPalExpressCheckout')``` to the dependencies section as shown in the illustration below.

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=PayPal%20Express%20Checkout&workspaceName=PayPalExpressCheckout&projectName=PayPalExpressCheckoutLib&rootNamespace=com.paypal.sandbox.api)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > PayPalExpressCheckoutLib > androidTest > java)* from the project explorer.
2. Select "Run All Tests" or use "Ctrl + Shift + F10" to run the Tests.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



API client can be initialized as following. The `appContext` being passed is the Android application [`Context`](https://developer.android.com/reference/android/content/Context.html).

```java
// Configuration parameters and credentials
String clientId = "AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9"; // client id
String clientSecret = "EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd"; // client secret
String oAuthAccessToken = "oAuthAccessToken"; // OAuth 2.0 Access Token

com.paypal.sandbox.api.Configuration.initialize(appContext);
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



