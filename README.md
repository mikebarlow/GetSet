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

Once setup, simply set or get any variables on the object you need.

    $MyClass->foo_bar = 'barfoo';

    echo $MyClass->foo_bar; // barfoo

This will set the variable into a `$data` array added to your object via the GetSet trait.

### Variable Transformers

You can create custom get / set transformers to change a variables data as it gets added to or retrieved from the `$data` variable. These should be in the format `setXAttr` and `getXAttr` where `X` is a CamelCased version of the variable you are setting or getting from the object.

In the example above, basic getter / setter methods for `foo_bar` could look like:

    public function setFooBarAttr($value)
    {
        $this->data['foo_bar'] = strtoupper($value);
    }

    public function getFooBarAttr()
    {
        return strtolower($this->data['foo_bar']);
    }

## Mass data assignment

If you need to assign a full array of data to your object and wish for the variables to be passed through any custom setters there is the `setAllData` method.

    $MyClass->setAllData([
        'foo_bar' => 'barfoo'
    ]);

## Data Export

If you need to export all the data set within your object you can use 1 of 2 methods.

### toArray

    $MyClass->toArray();

This will simply return all data set onto the object as an array.

### toJson

    $MyClass->toJson();

This will return all the data set onto the object as a Json object. This first uses the toArray method to retrieve an array before returning the data through `json_encode`.


## Changelog

You can view the changelog [HERE](https://github.com/mikebarlow/GetSet/blob/master/CHANGELOG.md)

## Contributing

Please see [CONTRIBUTING](https://github.com/mikebarlow/GetSet/blob/master/CONTRIBUTING.md) for details.

## License

The MIT License (MIT). Please see [License File](https://github.com/mikebarlow/GetSet/blob/master/LICENSE) for more information.