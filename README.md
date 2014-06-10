### Instalation using composer

In the composer.json file in your project add:

```json
{
    "repositories": [
        {
            "url": "http://github.com/websupport-sk/api_php.git",
            "type": "git"
        }
    ],
	"require" : {
		"websupport/api_php" : "dev-master"
	}
}
```

And then run:

```sh
php composer.phar install
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
		array('type'=>'domain', 'domain'=>'newdomain.com')
	));
	var_dump($orderInfo);
} catch (\websupport\RestException $e) {
	var_dump($e); // error via exception
}

```

### API Docs

https://rest.websupport.sk/docs/index
