# GetSet

[![Author](http://img.shields.io/badge/author-@mikebarlow-red.svg?style=flat-square)](https://twitter.com/mikebarlow)
[![Latest Version](https://img.shields.io/github/release/mikebarlow/getset.svg?style=flat-square)](https://github.com/mikebarlow/GetSet/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/mikebarlow/GetSet/blob/master/LICENSE)
[![Build Status](https://img.shields.io/travis/mikebarlow/GetSet/master.svg?style=flat-square)](https://travis-ci.org/mikebarlow/GetSet)

## Introduction

GetSet is a PSR-2 compliant trait to be used for adding magic getters / setters to objects.

## Requirements

### Composer

GetSet requires the following:

* "php": ">=5.6.0"

And the following if you wish to run in dev mode and run tests.

* "phpunit/phpunit": "~5.7"
* "squizlabs/php_codesniffer": "~2.0"

## Installation

### Composer

Simplest installation is via composer.

    composer require snscripts/getset 0.*

or adding to your projects `composer.json` file.

    {
        "require": {
            "snscripts/getset": "1.*"
        }
    }

### Setup

To initiate GetSet simply `use` the trait within your class

    class MyClass
    {
        use \Snscripts\GetSet\GetSet;

        ...
    }

## Usage




## Changelog

You can view the changelog [HERE](https://github.com/mikebarlow/GetSet/blob/master/CHANGELOG.md)

## Contributing

Please see [CONTRIBUTING](https://github.com/mikebarlow/GetSet/blob/master/CONTRIBUTING.md) for details.

## License

The MIT License (MIT). Please see [License File](https://github.com/mikebarlow/GetSet/blob/master/LICENSE) for more information.