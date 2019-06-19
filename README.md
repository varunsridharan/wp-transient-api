# WordPress Transient API
This library provides developers to manage all their Transients with version management. 

[![Latest Stable Version](https://poser.pugx.org/varunsridharan/wp-transient-api/version)](https://packagist.org/packages/varunsridharan/wp-transient-api)
[![Total Downloads](https://poser.pugx.org/varunsridharan/wp-transient-api/downloads)](https://packagist.org/packages/varunsridharan/wp-transient-api)
[![Latest Unstable Version](https://poser.pugx.org/varunsridharan/wp-transient-api/v/unstable)](//packagist.org/packages/varunsridharan/wp-transient-api)
[![License](https://poser.pugx.org/varunsridharan/wp-transient-api/license)](https://packagist.org/packages/varunsridharan/wp-transient-api)
[![composer.lock available](https://poser.pugx.org/varunsridharan/wp-transient-api/composerlock)](https://packagist.org/packages/varunsridharan/wp-transient-api)


## Installation
The preferred way to install this extension is through [Composer](http://getcomposer.org/download/).

To install **WP_Transient_API library**, simply:

    $ composer require Varunsridharan/WP_Transient_API

The previous command will only install the necessary files, if you prefer to **download the entire source code** you can use:

    $ composer require Varunsridharan/WP_Transient_API --prefer-source

You can also **clone the complete repository** with Git:

    $ git clone https://github.com/varunsridharan/wp-transient-api.git

Or **install it manually**:

[Download WP_Transient_API.php](https://raw.githubusercontent.com/varunsridharan/wp-transient-api/master/class-transient-wp-api.php):

    $ wget https://raw.githubusercontent.com/varunsridharan/wp-transient-api/master/class-transient-wp-api.php


## Options
| Option | Notes |
| ------ | ----- |
| ***WP Options API*** ||
| `option_prefix` | Custom text to auto prefix for each option added via this class |
| `option_surfix` | Custom text to auto append for each option added via this class | 
| `option_version` | On Which version the given option to be saved
| `option_auto_delete` | if set to true then it auto deletes if the version dose not match|
| ***WP Transient API*** ||
| `transient_prefix` | Custom text to auto prefix for each option added via this class |
| `transient_surfix` | Custom text to auto append for each option added via this class | 
| `transient_version` | On Which version the given option to be saved
| `transient_auto_delete` | if set to true then it auto deletes if the version dose not match|


## Usage 

```php
$api = new Varunsridharan\WordPress\Transient_API::instance('instance_key',array(
    // Transients
    'transient_version'     => 1.0,
    'transient_auto_delete' => false,
    'transient_surfix'      => '',
    'transient_prefix'      => '',
    // WP DB Options
    'option_auto_delete'    => false,
    'option_version'        => 1.0,
    'option_surfix'         => '',
    'option_prefix'         => '',
    // Global Config.
    'is_option'             => false,
));
YourPlugin_Transient_Api::instance();

```

## Global Based On Class Settings 
**Note** : `update only works for if class set to wp options api` 
```php
YourPlugin_Transient_Api::instance('instance_key')->set('your-key','your-value');
YourPlugin_Transient_Api::instance('instance_key')->get('your-key'); # Returns the values only if option version matched with $option_version
YourPlugin_Transient_Api::instance('instance_key')->update('your-key','your-value'); # Updates the options value
YourPlugin_Transient_Api::instance('instance_key')->delete('your-key'); # Deletes the options and its releated options 
```



## WP Options API With Version Management
```php
YourPlugin_Transient_Api::instance('instance_key')->add_option('your-key','your-value');
YourPlugin_Transient_Api::instance('instance_key')->get_option('your-key'); # Returns the values only if option version matched with $option_version
YourPlugin_Transient_Api::instance('instance_key')->update_option('your-key','your-value'); # Updates the options value
YourPlugin_Transient_Api::instance('instance_key')->delete_option('your-key'); # Deletes the options and its releated options 
```


## WP Transient API With Version Management
```php
YourPlugin_Transient_Api::instance('instance_key')->add_transient('your-key','your-value',2000);
YourPlugin_Transient_Api::instance('instance_key')->get_transient('your-key'); # Returns the values only if option version matched with $transient_version
YourPlugin_Transient_Api::instance('instance_key')->delete_transient('your-key'); # Deletes the options and its releated options 
```



---

## Contribute
If you would like to help, please take a look at the list of
[issues][issues] or the [To Do](#-todo) checklist.

## License
This project is licensed under **General Public License v3.0 license**. See the [LICENSE](LICENSE) file for more info.

## Copyright
2017 - 2018 Varun Sridharan, [varunsridharan.in][website]

If you find it useful, let me know :wink:

You can contact me on [Twitter][twitter] or through my [email][email].

## Backed By
| [![DigitalOcean][do-image]][do-ref] | [![JetBrains][jb-image]][jb-ref] |  [![Tidio Chat][tidio-image]][tidio-ref] |
| --- | --- | --- |

[twitter]: https://twitter.com/varunsridharan2
[email]: mailto:varunsridharan23@gmail.com
[website]: https://varunsridharan.in
[issues]: issues/
[composer]: http://getcomposer.org/download/
[downloadzip]:https://github.com/varunsridharan/wp-transient-api/archive/master.zip

[do-image]: https://vsp.ams3.cdn.digitaloceanspaces.com/cdn/DO_Logo_Horizontal_Blue-small.png
[jb-image]: https://vsp.ams3.cdn.digitaloceanspaces.com/cdn/phpstorm-small.png?v3
[tidio-image]: https://vsp.ams3.cdn.digitaloceanspaces.com/cdn/tidiochat-small.png
[do-ref]: https://s.svarun.in/Ef
[jb-ref]: https://www.jetbrains.com
[tidio-ref]: https://tidiochat.com

[latest-stable-version-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/version
[latest-Unstable-version-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/v/unstable
[total-downloads-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/downloads
[Latest-Unstable-version-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/v/unstable
[wpcs-img]: https://img.shields.io/badge/WordPress-Standar-1abc9c.svg
[license-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/license
[composerlock-img]: https://poser.pugx.org/varunsridharan/wp-transient-api/composerlock

[latest-stable-version-link]: https://packagist.org/packages/varunsridharan/wp-transient-api
[latest-Unstable-version-link]: https://packagist.org/packages/varunsridharan/wp-transient-api
[total-downloads-link]: https://packagist.org/packages/varunsridharan/wp-transient-api
[Latest-Unstable-Version-link]: https://packagist.org/packages/varunsridharan/wp-transient-api
[wpcs-link]: https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/
[license-link]: https://packagist.org/packages/varunsridharan/wp-transient-api
[composerlock-link]: https://packagist.org/packages/varunsridharan/wp-transient-api