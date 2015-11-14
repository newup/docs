# Installation

- [Installation](#installation)
   - [Server Requirements](#server-requirements)
   - [Installing NewUp](#installing-newup)
     - [Installing in a Specific Directory](#installing-newup-directory)
     - [Installing NewUp Globally](#installing-newup-globally)
- [Configuration](#configuration)
  - [composer.json File Configuration](#configuration-composer)

<a name="installation"></a>
## Installation

<a name="server-requirements"></a>
### Server Requirements

NewUp is built on top of the Laravel framework and therefore shares it's system requirements:

* PHP >= 5.5.9
* OpenSSL PHP Extension
* PDO PHP Extension
* Mbstring PHP Extension
* Tokenizer PHP Extension

<a href="installing-newup"></a>
### Installing NewUp

NewUp utilizes [Composer](http://getcomposer.org) to manage package templates and their dependencies. You will need to make sure you have Composer installed and configured before continuing.

<a href="installing-newup-directory"></a>
#### Installing in a Specific Directory

NewUp is installed using [Composer](https://getcomposer.org/). This is the easiest installation option as Composer is required to use NewUp. To install NewUp, decide which directory you want to install NewUp in and run the following command from that directory:

~~~
composer create-project newup/newup .
~~~

Composer will take just a moment to install all of the dependencies required for NewUp to work correctly.

To make it easier to work with NewUp, consider adding the directory you installed NewUp in to your `PATH`.

<a href="installing-newup-globally"></a>
#### Installing NewUp Globally

NewUp can be installed globally using [Composer](https://getcomposer.org/). To do this, issue the following command:

~~~
composer global require newup/newup
~~~

When NewUp is globally installed, it might be easier to move the configuration directory location to somewhere else on the system. To do this, copy the contents of the `config` directory and create a new environment variable named `NEWUP_CONFIGURATION` with the path to the configuration directory as the value.

<a name="configuration"></a>
## Configuration

<a href="configuration-composer"></a>
### composer.json File Configuration

NewUp provides utilities to generate `composer.json` files for your projects and package templates. You can configure what values NewUp will use by default for the package authors and license values.

To configure the default values that will be used when generated `composer.json` files, locate the `config/configuration.php` file. You should see the following entries:

~~~
    ...

    /*
    |--------------------------------------------------------------------------
    | Package Authors
    |--------------------------------------------------------------------------
    |
    | When you create new packages NewUp will automatically add the
    | following authors to the generated "composer.json" file.
    | You can add as many authors as you like to the list.
    |
    */
    'authors' => [
        [
            'name'  => 'Your Name',
            'email' => 'Your Email'
        ]
    ],

    /*
    |--------------------------------------------------------------------------
    | Package License
    |--------------------------------------------------------------------------
    |
    | When you create new packages NewUp will automatically set the
    | license for the newly created package template. You should
    | set the following license to your preferred license.
    |
    */
    'license' => 'MIT',

    ...
~~~

Simply change the values to your desired defaults. The `authors` entry is actually an array, so you can have multiple authors by default when the `composer.json` file is generated.