# Laravel "Accept-Language" middleware

Laravel middleware for automatically setting application locale based on [HTTP "Accept-Language"](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language) header

## Requirements

- PHP **8.3** or higher.
- Laravel **^12.0** or higher

## Installation

You can install the package via composer:

```bash
composer require php-monsters/laravel-accept-language-middleware
```

## Usage

Register `\PhpMonsters\LaravelAcceptLanguageMiddleware\Middleware::class` middleware in application's HTTP Kernel.

You can install it as global middleware in Kernel's `$middleware` property:

``` php
protected $middleware = [
    ...
    \PhpMonsters\LaravelAcceptLanguageMiddleware\Middleware::class
];
```

You can install it to specific middleware groups in Kernel's `$middlewareGroups` property:

``` php
protected $middlewareGroups = [
    'web' => [
        ...
        \PhpMonsters\LaravelAcceptLanguageMiddleware\Middleware::class
    ]
];
```

Or you can install is as route middleware in Kernel's `$routeMiddleware` and use it manually in routes:

Kernel:

``` php
protected $routeMiddleware = [
    ...
    'accept-language' => \PhpMonsters\LaravelAcceptLanguageMiddleware\Middleware::class
];
```

Route file
``` php
Route::middleware(['accept-language'])->get('/', 'MyController@index');
```

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Credits

- [Aboozar Ghaffari](https://github.com/samuraee)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
