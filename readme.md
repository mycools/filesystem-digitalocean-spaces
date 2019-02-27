# Mycools\Flysystem\DoSpaces

[![Author](http://img.shields.io/badge/author-@mycools-blue.svg?style=flat-square)](https://twitter.com/mycools)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Packagist Version](https://img.shields.io/packagist/v/mycools/filesystem-digitalocean-spaces.svg?style=flat-square)](https://packagist.org/packages/mycools/filesystem-digitalocean-spaces)
[![Total Downloads](https://img.shields.io/packagist/dt/mycools/filesystem-digitalocean-spaces.svg?style=flat-square)](https://packagist.org/packages/mycools/filesystem-digitalocean-spaces)

This is a Flysystem adapter for the aws-sdk-php v3.

# Installation

```bash
composer require mycools/filesystem-digitalocean-spaces
```

# Bootstrap

``` php
<?php
use Aws\S3\S3Client;
use Mycools\Flysystem\DoSpaces\DoSpacesAdapter;
use Mycools\Flysystem\Filesystem;

include __DIR__ . '/vendor/autoload.php';

$client = new S3Client([
    'credentials' => [
        'key'    => 'your-key',
        'secret' => 'your-secret'
    ],
    'region' => 'your-region',
    'version' => 'latest|version',
]);

$adapter = new DoSpacesAdapter($client, 'your-bucket-name');
$filesystem = new Filesystem($adapter);
```
