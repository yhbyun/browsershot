# Convert a webpage to an image

[![Build Status](https://secure.travis-ci.org/freekmurze/browsershot.png)](http://travis-ci.org/freekmurze/geocoder)
[![Total Downloads](https://poser.pugx.org/spatie/browsershot/downloads.svg)](https://packagist.org/packages/spatie/browsershot)
[![Latest Stable Version](https://poser.pugx.org/spatie/browsershot/version.png)](https://packagist.org/packages/spatie/browsershot)
[![License](https://poser.pugx.org/spatie/browsershot/license.png)](https://packagist.org/packages/spatie/browsershot)

The package can convert a webpage to an image. To accomplish this conversion [Phantomjs](http://phantomjs.org/) (included in the project) is used.

This package is used to generate the sitepreviews on the homepage of [spatie.be](https://spatie.be). It is also used by [Gordon Murray](https://twitter.com/murrion) to [add previews to shared content](http://www.murrion.com/2015/02/how-i-automate-sharing-content-to-linkedin-using-ayliens-content-analysis-api-and-browsershot/).

## Installation

This package can be installed through Composer.

```bash
composer require spatie/browsershot
```

When using Laravel there is a service provider that you can make use of.

```php

// app/config/app.php

'providers' => [
    '...',
    'Spatie\Browsershot\BrowsershotServiceProvider'
];
```

## Usage

Here is a sample call to create an image of a webpage:

```php
    $browsershot = new Spatie\Browsershot\Browsershot();
    $browsershot
        ->setURL('http://www.arstechnica.com')
        ->setWidth('1024')
        ->setHeight('768')
        ->save('targetdirectory/arstechnica-browsershot.jpg');
```

These methods are provided:

* `setBinPath()`: Specify the path to your own phantomjs-binary.
* `setWidth()`: Set the width of the image (defaults to 640).
* `setHeight()`: Set the height of the image (defaults to 480).
* `setURL()`: Set the URL of the webpage which should be converted to an image
* `save($targetFile)`: Starts the conversion-process. The targetfile should have one of these extensions: png, jpg, jpeg.

