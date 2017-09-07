# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/).
If any of your models have `Date` or `Datetime` type fields or your endpoints have `Date`/`Datetime` type response, you will need to download and link [angular-moment](https://cdnjs.cloudflare.com/ajax/libs/angular-moment/1.0.1/angular-moment.min.js) and [moment.js](https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.17.1/moment.min.js) with your project.

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have a `scripts` folder, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `PayPalExpressCheckoutLib` folder inside the scripts folder.
+ If any of the Custom Types in your API have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will need to download angular-moment and moment.js. Move these 2 files into the `scripts` folder as well.

![folder-structure-image](https://apidocs.io/illustration/angularjs?step=folderStructure&workspaceFolder=PayPal%20Express%20Checkout-Angular&projectName=PayPalExpressCheckoutLib)

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![open-folder-image](https://apidocs.io/illustration/angularjs?step=openFolder&workspaceFolder=PayPal%20Express%20Checkout-Angular)

### 3. Create an Angular Application
Since Angular JS is used for client-side web development, in order to use the generated library, you will have to develop an application first.
If you already have an angular application, [skip to Step 6](#6-include-sdk-references-in-html-file). Otherwise, follow these steps to create one:

+ In the IDE, click on `File` and choose `New File` to create a new file.
+ Add the following starting code in the file:
```js
var app = angular.module('myApp', []);
app.controller('testController', function($scope) 
{

});
```
+ Save it with the name `app.js` in the `scripts` folder.


### 4. Create HTML File
Skip to the next step if you are working with an existing project and already have an html file. Otherwise follow the steps to create one:
+ Inside the IDE, right click on the project folder name and select the `New File` option to create a new test file.
+ Save it with an appropriate name such as `index.html` in the root of your project folder.
`index.html` should look like this:
```html
<!DOCTYPE html>
<html>
<head>
	<title>Angular Project</title>
	<script></script>
</head>

<body>
</body>

</html>
```

![initial-html-code-image](https://apidocs.io/illustration/angularjs?step=initialCode&workspaceFolder=PayPal%20Express%20Checkout-Angular)

### 5. Including links to Angular in HTML file
Your HTML file needs to have a link to `angular.min.js` file to use Angular-JS. Add the link using `script` tags inside the `head` section of `index.html` like:
```html
<script src="scripts/angular.min.js" ></script>
```
If any of the Custom Types that you have defined have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will also need to link to angular-moment and moment.js like:
```html
<script src="scripts/angular.min.js" ></script>
<script src="scripts/moment.min.js" ></script>
<script src="scripts/angular-moment.min.js" ></script>
```

### 6. Include SDK references in HTML file
Import the reference to the generated SDK files inside your html file like:
```html
<head>
    ...
    <!-- Helper files -->
    <script src="scripts/PayPalExpressCheckoutLib/Module.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Configuration.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/ModelFactory.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/ObjectMapper.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/APIHelper.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Http/Client/HttpContext.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Http/Client/RequestClient.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Http/Response/HttpResponse.js"></script>

    <!-- API Controllers -->
    <script src="scripts/PayPalExpressCheckoutLib/Controllers/BaseController.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Controllers/PaymentController.js"></script>


    <!-- Models -->
    <script src="scripts/PayPalExpressCheckoutLib/Models/BaseModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/AmountModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/LinkModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ItemList16Model.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PaymentOptions15Model.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/RedirectUrlsModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ItemListModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/RelatedResourceModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ExecuteRequestModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PaymentOptionsModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/Amount12Model.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PayerModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PaymentRequestModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/TransactionModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/DetailsModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ItemModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PaymentResponseModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/Transaction12Model.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/Item17Model.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/PayerInfoModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ExecuteResponseModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/ShippingAddressModel.js"></script>
    <script src="scripts/PayPalExpressCheckoutLib/Models/OrderModel.js"></script>

    ...
</head>
```
> The `Module.js` file should be imported before the other files. After `Module.js`, `Configuration.js` should be imported.
> The `ModelFactory.js` file is needed by `ObjectMapper.js` file. The `ObjectMapper` in turn, is needed by `BaseController.js`.

### 7. Including link to `app.js` in HTML file
Link your `app.js` file to your `index.html` file like:
```html
<head>
	...
	<script src="scripts/app.js"></script>
</head>
```
> The link to app.js needs to be included at the very end of the head tag, after the SDK references have been added

### 8. Initializing the Angular App
You need to initialize your app and the controller associated with your view inside your `index.html` file. Do so like:
+ Add ng-app directive to initialize your app inside the `body` tag.
```html
<body ng-app="myApp">
```
+ Add ng-controller directive to initialize your controller and bind it with your view (`index.html` file).
```html
...
<body ng-app="myApp">
	<div ng-controller="testController">
		...
	</div>
	...
</body>
...
```

### 9. Consuming the SDK 
In order to use the generated SDK's modules, controllers and factories, the project needs to be added as a dependency in your angular app's module. This will be done inside the `app.js` file.
Add the dependency like this:

```js
var app = angular.module('myApp', ['PayPalExpressCheckoutLib']);
```
At this point, the SDK has been successfully included in your project. Further steps include using a service/factory from the generated SDK. To see working example of this, please head on [over here](#list-of-controllers) and choose any class to see its functions and example usage.  

### 10. Running The App
To run the app, simply open up the `index.html` file in a browser.

![app-running](https://apidocs.io/illustration/angularjs?step=appRunning)

## Initialization


The Angular Application can be initialized as following:
```JavaScript
var app = angular.module('myApp', [PayPalExpressCheckoutLib]);
// now controllers/services can be created which import
// the factories provided by the sdk
```
### Authentication
In order to setup authentication and initialization of the Angular App, you need the following information.

| Parameter | Description |
|-----------|-------------|
| clientId | client id |
| clientSecret | client secret |
| oAuthAccessToken | OAuth 2.0 Access Token |



```JavaScript
var app = angular.module('myApp', [PayPalExpressCheckoutLib]);
app.factory('config', function($scope, Configuration) 
{
    return {
        setConfigVars: function() {
            // Configuration parameters and credentials
            Configuration.clientId = 'AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9'; // client id
            Configuration.clientSecret = 'EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd'; // client secret
            Configuration.oAuthAccessToken = 'oAuthAccessToken'; // OAuth 2.0 Access Token
            
        }
    };
});
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get singleton instance

The singleton instance of the ``` PaymentController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, PaymentController, ExecuteResponseModel, PaymentResponseModel){
	});
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.createExecute") createExecute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.


```javascript
function createExecute(input)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |



#### Example Usage

```javascript


	app.controller("testController", function($scope, PaymentController, ExecuteResponseModel){
        var input = [];
        input['body'] = new ExecuteRequestModel({"key":"value"});
        input['paymentId'] = payment_id;


		var result = PaymentController.createExecute(input);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create") create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.


```javascript
function create(body)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |



#### Example Usage

```javascript


	app.controller("testController", function($scope, PaymentController, PaymentResponseModel){
        var body = new PaymentRequestModel({"key":"value"});


		var result = PaymentController.create(body);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)



