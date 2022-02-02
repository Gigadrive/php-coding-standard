# Gigadrive's PHP Coding Standard

This repository holds the coding standard used for Gigadrive PHP projects. It is available to the public and licensed under the [MIT License](https://github.com/Gigadrive/php-coding-standard/blob/master/LICENSE).

The coding standard was made to be used with the [PHP CS Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer) tool for easy IDE and CI pipeline integrations.

## Installation

You will need to install both PHP CS Fixer and the Gigadrive coding standard with composer:

```shell
composer require --dev friendsofphp/php-cs-fixer
composer require --dev gigadrive/php-coding-standard
```

## Usage

Next, create a `.php-cs-fixer.dist.php` file at your project root:

```php
<?php

$config = require_once "vendor/gigadrive/php-coding-standard/php-cs-fixer-config.php";

// Define what project files you want to pass to PHP CS Fixer.
$finder = (new PhpCsFixer\Finder())
	->in(__DIR__)
	->exclude("var")
	->exclude("vendor");

return $config
    ->setFinder($finder);
```

Your project will now use the Gigadrive PHP Coding Standard by default.

**IMPORTANT:** This coding standard contains rules that are considered **risky** by PHP CS Fixer. Use them at your own risk. To prevent unintended damage, the risky flag is disabled by default. You can adjust your config file to enable it, or pass the `--allow-risky=yes` option to the command line.

* `$config` is a PHP CS Fixer Config object you can use according to the [PHP CS Fixer documentation](https://github.com/FriendsOfPHP/PHP-CS-Fixer/blob/master/doc/config.rst). You can use this to adjust the coding standard rules to your liking.

## Copyright and License

This program was developed by [Mehdi Baaboura](https://github.com/Zeryther) and published by [Gigadrive UG](https://gigadrivegroup.com) under the MIT License. For more information click [here](https://github.com/Gigadrive/php-coding-standard/blob/master/LICENSE).
