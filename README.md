# WP Endpoints: Routes

> Get the set of routes and exposes them via WP-API. This extension will create an endpoint (at ```/wp-json/leean/v1/routes``` by default).

## Getting Started

The easiest way to install this package is by using composer from your terminal:

```bash
composer require moxie-leean/wp-endpoints-routes
```

Or by adding the following lines on your `composer.json` file

```json
"require": {
  "moxie-leean/wp-endpoints-routes": "dev-master"
}
```

This will download the files from the [packagist site](https://packagist.org/packages/moxie-leean/wp-endpoints-routes) 
and set you up with the latest version located on master branch of the repository. 

After that you can include the `autoload.php` file in order to
be able to autoload the class during the object creation.

```php
include '/vendor/autoload.php';
```

Finally you need to initialise the endpoint by adding this to your code:

```php
\Leean\Endpoints\Routes::init();
```

## Usage

The endpoint takes no inputs and returns data in the following format:

```
[
  {
    "state": "home",
    "url": "/",
    "template": "home",
    "endpoint": "post",
    "params": {
      "id": 123
    }
  },
  {
    "state": "allPhotos",
    "url": "/photos",
    "template": "allPhotos",
    "endpoint": "collection",
    "params": {
      "type": "photo",
      "posts_per_page": 10
    }
  },
  {
    "state": "authorPhotos",
    "url": "/photos/:authorId",
    "template": "authorPhotos",
    "endpoint": "collection",
    "params": {
      "type": "photo",
      "posts_per_page": 10
    }
  },
  {
    "state": "photo",
    "url": "/photos/:authorId/:photoId",
    "template": "photo",
    "endpoint": "post",
    "params": {}
  }
]
```
