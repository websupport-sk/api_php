### Instalation using composer

Require composer package using terminal:

```sh
composer require websupport/api_php
```

Or add following to `composer.json` file in your project:

```json
{
	"require" : {
		"websupport/api_php" : "~1.0"
	}
}
```

And then run:

```sh
composer update
```

**Note:** Requires PHP version 5.3 or higher and the PHP cURL extension


### Quick Start Example

```php
$api = new \websupport\RestConnection('https://rest.websupport.sk/v1/', 'login', 'pass');

// load user info
try {
	$userInfo = $api->get('user/self'); 
	var_dump($userInfo);
} catch (\websupport\RestException $e) {
	var_dump($e); // error via exception
}

// ordering domain
try {
	$orderInfo = $api->post('user/self/order', array(
		"services"=>array(
			array('type'=>'domain', 'domain'=>'newdomain.com')
		)
	));
	var_dump($orderInfo);
} catch (\websupport\RestException $e) {
	var_dump($e); // error via exception
}

```

### API Docs

More detailed documentation of all api methods can be found at our [docs page](https://rest.websupport.sk/docs/index).
