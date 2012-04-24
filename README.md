README
======

YepsuaSmarTwigBundle
--------------------

Is a set of Twig Tags that allow the creation of jQueryUI widgets in an easy way.

Create RIA (RICH INTERNET APPLICATIONS) with Symfony2 and jQuery4PHP.

Visit the [showcase](http://smartwig.yepsua.com/web/)

# Installation

## Add YepsuaSmarTwigBundle to your vendor/bundles/ directory

Use one of the following:

### Using the vendors script

Add the following lines in your ``deps`` file

```
[YepsuaSmarTwigBundle]
    git=http://github.com/oyepez003/YepsuaSmarTwigBundle.git
    target=/bundles/Yepsua/SmarTwigBundle
```

Run the vendors script

    ./bin/vendors update

### Using submodules

``` bash
$ git submodule add http://github.com/oyepez003/YepsuaSmarTwigBundle.git vendor/bundles/Yepsua/SmarTwigBundle
```

### Download via HTTP:

Download the sourcecode from https://github.com/oyepez003/YepsuaSmarTwigBundle/downloads
unzip into vendor/bundles/Yepsua/SmarTwigBundle


# Configuration

## 1) Add the Yepsua namespace to your autoloader (app/autoload.php)

``` php
<?php
// app/autoload.php

$loader->registerNamespaces(array(
    'Yepsua' => __DIR__.'/../vendor/bundles/Yepsua',
    // ...
);
```

## 2) Activate the jQuery4PHP library in your autoloader (app/autoload.php)

Copy the next code at end of file

``` php
<?php
// app/autoload.php
include_once 'path/to/YepSua/Labs/RIA/jQuery4PHP/YsJQueryAutoloader.php';
YsJQueryAutoloader::register();
```

## 3) Add the YepsuaSmarTwigBundle to your application kernel (app/AppKernel.php)

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    return array(
        new Yepsua\SmarTwigBundle\YepsuaSmarTwigBundle(),
        // ...
    );
}
```

## 4) Public assets

Run the symfony command

``` bash
$ php app/console assets:install web
```

## 5) Include the SmarTwigBundle assets in your layout

``` html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>YepsuaSmarTwigBundle</title>

  {% include 'YepsuaSmarTwigBundle::smartwigAssets.html.twig' %}

</head>
<body>
  {% ui_dialog  %}
    
  {% end_ui_dialog %}
</body>
</html>
```


Enjoy

[Showcase](http://smartwig.yepsua.com/web/)
[Twig](http://www.twig-project.org/)
[jQuery4PHP](http://jquery4php.sourceforge.net/)