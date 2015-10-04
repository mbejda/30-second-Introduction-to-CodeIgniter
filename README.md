![30 second introduction to CodeIgniter](http://www.mbejda.com/content/images/2015/10/codeigniter.png#cover#cover)

This 30 second series covers the CodeIgniter PHP framework. We are going to install CodeIgniter, create a CodeIgniter controller and a CodeIgniter view. Then we are going to make bind the controller to the view with the router. If you get lost at any step of the way the entire project source code can be found in the following repo https://github.com/mbejda/30-second-Introduction-to-CodeIgniter.
 **Lets get started.**

##Installation
Download,fork or clone CodeIgniter frame work from there [repo](https://github.com/bcit-ci/CodeIgniter) and extract the files. The directory structure should look similarly to the following :
![directory](http://www.mbejda.com/content/images/2015/10/Screen-Shot-2015-10-04-at-1-52-25-PM.png#400). Navigate to the root of the project and run `composer install` to install CodeIgniter dependencies.


##Creating A View
CodeIgniter views are located in `application/views` directory. Navigate to `application/views` and create a new view file. I named my CodeIgniter view file `hello.php`. Paste the following contents into the CodeIgniter view file.
```
<?php
defined('BASEPATH') OR exit('No direct script access allowed');
?><!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<title>Welcome to CodeIgniter</title>

	<style type="text/css">

	::selection { background-color: #E13300; color: white; }
	::-moz-selection { background-color: #E13300; color: white; }

	body {
		background-color: #fff;
		margin: 40px;
		font: 13px/20px normal Helvetica, Arial, sans-serif;
		color: #4F5155;
	}

	a {
		color: #003399;
		background-color: transparent;
		font-weight: normal;
	}

	h1 {
		color: #444;
		background-color: transparent;
		border-bottom: 1px solid #D0D0D0;
		font-size: 19px;
		font-weight: normal;
		margin: 0 0 14px 0;
		padding: 14px 15px 10px 15px;
	}

	code {
		font-family: Consolas, Monaco, Courier New, Courier, monospace;
		font-size: 12px;
		background-color: #f9f9f9;
		border: 1px solid #D0D0D0;
		color: #002166;
		display: block;
		margin: 14px 0 14px 0;
		padding: 12px 10px 12px 10px;
	}

	#body {
		margin: 0 15px 0 15px;
	}

	p.footer {
		text-align: right;
		font-size: 11px;
		border-top: 1px solid #D0D0D0;
		line-height: 32px;
		padding: 0 10px 0 10px;
		margin: 20px 0 0 0;
	}

	#container {
		margin: 10px;
		border: 1px solid #D0D0D0;
		box-shadow: 0 0 8px #D0D0D0;
	}
	</style>
</head>
<body>

<div id="container">
	<h1>Welcome World</h1>



</div>

</body>
</html>
```


##Creating A Controller
CodeIgniters controllers are in the `application/controller` directory. Navigate to `application/controller` and create a new Codeigniter controller file. I named my controller file `Hello.js`. Paste the following code into the controller.<br> *Make sure that your class name reflects your controller file name and your view matches your views file name.*

```
<?php
defined('BASEPATH') OR exit('No direct script access allowed');

class Hello extends CI_Controller {

    public function index()
    {
        $this->load->view('hello');
    }
}

```
##Creating A Route
Routes bind controllers to views. CodeIgniters routes are in `application/config/routes.php` file. Open the route file and add the following:
```
$route['hello'] = 'hello';
```

The `$route['hello']` assigns the necessary URI structure to the `hello` controller.

##Testing It Out
Lets test everything out. Navigate to the project root and launch the application. In the terminal run<br>
```
php -S localhost:9000
```
Then navigate to the URI that has been added to the route. You should see something like this :
![codigniter hello](http://www.mbejda.com/content/images/2015/10/Screen-Shot-2015-10-04-at-2-15-04-PM.png)
