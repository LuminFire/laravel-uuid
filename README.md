# Laravel-UUID

[![Build Status](https://travis-ci.org/luminfire/laravel-uuid.svg?branch=master)](https://travis-ci.org/luminfire/laravel-uuid)
[![Latest Stable Version](http://img.shields.io/packagist/v/luminfire/laravel-uuid.svg?style=flat)](https://packagist.org/packages/luminfire/laravel-uuid)
[![Total Downloads](http://img.shields.io/packagist/dt/luminfire/laravel-uuid.svg?style=flat)](https://packagist.org/packages/luminfire/laravel-uuid)

A trait to add UUID integration, using Laravel’s native `Str:uuid()` functionality. Forked from [binarycabin/laravel-uuid](https://github.com/binarycabin/laravel-uuid), removing the `webpatser/laravel-uuid` dependency.

```bash
composer require luminfire/laravel-uuid
```

This package adds a very simple trait to automatically generate a UUID for your Models.

Simply add the `\LuminFire\LaravelUUID\Traits\HasUUID;` trait to your model:

```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Project extends Model
{

    use \LuminFire\LaravelUUID\Traits\HasUUID;

}
```

If your column name is not "uuid", simply add a new property to your model named "uuidFieldName":

```php
protected $uuidFieldName = 'unique_id';
```

This trait also adds a scope:

```php
\App\Project::byUUID('uuid')->first();
```

And static find method:

```php
\App\Project::findByUUID('uuid')
```
