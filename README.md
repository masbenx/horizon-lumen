## Introduction

Horizon Horizon is based on the official [Laravel Horizon](https://github.com/laravel/horizon) package.The web UI is also included.

If you prefer a pure restful api and want to customize the UI, you can refer to [Lumen-horizon](https://github.com/servocoder/lumen-horizon) by servocoder.

## Installation

1. Run composer to add the dependency.

```
composer require kinsolee/horizon-lumen
```

2.Add the vendor:publish command dependency and publish its assets and config file. 

```text
composer require "laravelista/lumen-vendor-publish" --dev
```

3. Add `Laravelista\LumenVendorPublish\VendorPublishCommand` to `app/Console/Kernel.php` file.

4. Add `$app->register(\Laravel\Horizon\HorizonServiceProvider::class);` in your `boorstrap/app.php` file.

5. Publish horizon vendor
```text
php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"
``` 

## Problems
* If you get the follow errors when you run vendor:publish:
```
Type error: Argument 1 passed to Laravel\Horizon\Repositories\RedisMasterSupervisorRepository::__construct() must implement interface Illuminate\Contr
  acts\Redis\Factory, instance of Redis given
```
Make sure you register `Illuminate\Redis\RedisServiceProvider::class` in your `boorstrap/app.php` file.

* If you deploy horizon-lumen on sub-directory, please specific `base_path` in config/horizon.php
## Official Documentation

Documentation for Horizon can be found on the [Laravel website](http://laravel.com/docs/horizon).

## License

Laravel Horizon is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
