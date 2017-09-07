# Getting started

Set up the PayPal Express Checkout Server-Side REST product

## How to Build


You must have Python 2 >=2.7.9 or Python 3 >=3.4 installed on your system to install and run this SDK. This SDK package depends on other Python packages like nose, jsonpickle etc. 
These dependencies are defined in the ```requirements.txt``` file that comes with the SDK.
To resolve these dependencies, you can use the PIP Dependency manager. Install it by following steps at [https://pip.pypa.io/en/stable/installing/](https://pip.pypa.io/en/stable/installing/).

Python and PIP executables should be defined in your PATH. Open command prompt and type ```pip --version```.
This should display the version of the PIP Dependency Manager installed if your installation was successful and the paths are properly defined.

* Using command line, navigate to the directory containing the generated files (including ```requirements.txt```) for the SDK.
* Run the command ```pip install -r requirements.txt```. This should install all the required dependencies.

![Building SDK - Step 1](https://apidocs.io/illustration/python?step=installDependencies&workspaceFolder=PayPal%20Express%20Checkout-Python)


## How to Use

The following section explains how to use the Paypalexpresscheckout SDK package in a new project.

### 1. Open Project in an IDE

Open up a Python IDE like PyCharm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PyCharm - Step 1](https://apidocs.io/illustration/python?step=pyCharm)

Click on ```Open``` in PyCharm to browse to your generated SDK directory and then click ```OK```.

![Open project in PyCharm - Step 2](https://apidocs.io/illustration/python?step=openProject0&workspaceFolder=PayPal%20Express%20Checkout-Python)     

The project files will be displayed in the side bar as follows:

![Open project in PyCharm - Step 3](https://apidocs.io/illustration/python?step=openProject1&workspaceFolder=PayPal%20Express%20Checkout-Python&projectName=paypalexpresscheckout)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PyCharm - Step 1](https://apidocs.io/illustration/python?step=createDirectory&workspaceFolder=PayPal%20Express%20Checkout-Python&projectName=paypalexpresscheckout)

Name the directory as "test"

![Add a new project in PyCharm - Step 2](https://apidocs.io/illustration/python?step=nameDirectory)
   
Add a python file to this project with the name "testsdk"

![Add a new project in PyCharm - Step 3](https://apidocs.io/illustration/python?step=createFile&workspaceFolder=PayPal%20Express%20Checkout-Python&projectName=paypalexpresscheckout)

Name it "testsdk"

![Add a new project in PyCharm - Step 4](https://apidocs.io/illustration/python?step=nameFile)

In your python file you will be required to import the generated python library using the following code lines

```Python
from paypalexpresscheckout.paypalexpresscheckout_client import PaypalexpresscheckoutClient
```

![Add a new project in PyCharm - Step 4](https://apidocs.io/illustration/python?step=projectFiles&workspaceFolder=PayPal%20Express%20Checkout-Python&libraryName=paypalexpresscheckout.paypalexpresscheckout_client&projectName=paypalexpresscheckout)

After this you can write code to instantiate an API client object, get a controller object and  make API calls. Sample code is given in the subsequent sections.

### 3. Run the Test Project

To run the file within your test project, right click on your Python file inside your Test project and click on ```Run```

![Run Test Project - Step 1](https://apidocs.io/illustration/python?step=runProject&workspaceFolder=PayPal%20Express%20Checkout-Python&libraryName=paypalexpresscheckout.paypalexpresscheckout_client&projectName=paypalexpresscheckout)


## How to Test

You can test the generated SDK and the server with automatically generated test
cases. unittest is used as the testing framework and nose is used as the test
runner. You can run the tests as follows:

  1. From terminal/cmd navigate to the root directory of the SDK.
  2. Invoke 'pip install -r test-requirements.txt'
  3. Invoke 'nosetests'

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| client_id | client id |
| client_secret | client secret |
| o_auth_access_token | OAuth 2.0 Access Token |



API client can be initialized as following.

```python
# Configuration parameters and credentials
client_id = 'AQzwHJt9jZAyQbf-DnaqZefvbTCMammV7ZFsnW23thr9qUQX9RGMgSVbzRjxXTAODKjh2W0k6Ei4Q2m9' # client id
client_secret = 'EGo6tHB30V0ORQE1pFmr1hrsURQdXOgEJla9Ro5zjoAwyT0An3ddyqIYL836EOVS5XjSvmw_qwEEMsgd' # client secret
o_auth_access_token = 'o_auth_access_token' # OAuth 2.0 Access Token

client = PaypalexpresscheckoutClient(client_id, client_secret, o_auth_access_token)
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [PaymentController](#payment_controller)

## <a name="payment_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PaymentController") PaymentController

### Get controller instance

An instance of the ``` PaymentController ``` class can be accessed from the API Client.

```python
 payment_client = client.payment
```

### <a name="create_execute"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create_execute") create_execute

> Executes a PayPal payment that the customer has approved. You can optionally update one or more transactions when you execute the payment.
> 
> A successful request returns the HTTP 200 OK status code and a JSON response body that shows details for the executed payment.
> 
> Important: This call works only after a customer has approved the payment. For more information, learn about PayPal payments.

```python
def create_execute(self,
                       options=dict())
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | The ID of the payer that PayPal passes in the return_url. |
| paymentId |  ``` Required ```  | The ID of the payment to execute. |



#### Example Usage

```python
collect = {}

body = ExecuteRequestModel()
collect['body'] = body

payment_id = 'payment_id'
collect['payment_id'] = payment_id


result = payment_client.create_execute(collect)

```


### <a name="create"></a>![Method: ](https://apidocs.io/img/method.png ".PaymentController.create") create

> To create an Express Checkout payment, set the payment intent to sale and include a list of items in the transaction object. The items enable buyers to see the transaction total when they check out at PayPal. If you omit items from the request, the PayPal windows do not display the transaction total.

```python
def create(self,
                body)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | After you collect payment details from the buyer, include these details in the JSON payload of a create payment request |



#### Example Usage

```python
body = PaymentRequestModel()

result = payment_client.create(body)

```


[Back to List of Controllers](#list_of_controllers)



