# Redsys query PHP

Allow query order transactions done into spanish gateway banks that uses Sermepa/Redsys.

This is used into webservice located in /apl02/services/SerClsWSConsulta.

The spanish documentation is located in 'Consultas SOAP HMAC SHA256 2.5', in root folder.

## Installation

@TODO

## Examples

### Get transactions
This service allows get the redsys transactions by id. 

Example (also available in examples/get_transaction.php:


```php

<?php
require './vendor/autoload.php';

use RedsysConsultasPHP\Client\Client;

$url = 'https://sis-t.redsys.es:25443/apl02/services/SerClsWSConsulta';
$client = new Client($url, 'Introduce your merchant password');

$order = 'Introduce your order';
$terminal = 'Introduce your terminal';
$merchant_code = 'Introduce your merchant code';
$response = $client->getTransaction($order, $terminal, $merchant_code);

print_r($response);

```