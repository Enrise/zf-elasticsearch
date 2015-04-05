ZF2 Elasticsearch Module
========================

[![Latest Stable Version](https://poser.pugx.org/enrise/zf-elasticsearch/v/stable.svg)](https://packagist.org/packages/enrise/zf-elasticsearch)
[![License](https://poser.pugx.org/enrise/zf-elasticsearch/license.svg)](https://packagist.org/packages/enrise/zf-elasticsearch)

This repository contains a _very_ simple but drop-in solution for using the 
[elasticsearch client library](https://github.com/elastic/elasticsearch-php) in a ZF2 project.

The client is pre-configured with sensible defaults. You can further configure the client in the module config just as 
you would [configure the elasticsearch client](https://github.com/elastic/elasticsearch-php/blob/master/docs/configuration.asciidoc) 
directly.

Usage example
-------------
```php
$searchClient = $serviceLocator->get('elasticsearch');
$searchClient->search();
```

Installation
------------
Require the module via composer:
```sh
$ composer require enrise/zf-elasticsearch
```

Load the module in your application:
```php
// config/application.config.php
return array(
    'modules' => array(
        // ...
        'Enrise\\ZfModule\\ElasticSearch',
    )
);
```

And you're done!

Configuration example
---------------------

To fine-tune your installation you can tweak the elasticsearch client configuration. For example:

```php
// In your config file
return [
    'elasticsearch' => [
        'hosts' => [
            'es1.enrise.com',
            'es2.enrise.com'
        ],
        'logging' => true
    ]
];
```

Dependencies
------------
- `elasticsearch/elasticsearch:^1.0`

License
-------
Please see the LICENSE file in this repository

Contributors
------------
This zend framework module was made by [Richard Tuin](https://github.com/rtuin).
