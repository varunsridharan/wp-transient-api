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

<!-- START common-footer.mustache  -->
## 📝 Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

[Checkout CHANGELOG.md](https://github.com/varunsridharan/wp-transient-api/blob/main/CHANGELOG.md)


## 🤝 Contributing
If you would like to help, please take a look at the list of [issues](https://github.com/varunsridharan/wp-transient-api/issues/).


## 📜  License & Conduct
- [**GNU General Public License v3.0**](https://github.com/varunsridharan/wp-transient-api/blob/main/LICENSE) © [Varun Sridharan](website)
- [Code of Conduct](https://github.com/varunsridharan/.github/blob/main/CODE_OF_CONDUCT.md)


## 📣 Feedback
- ⭐ This repository if this project helped you! :wink:
- Create An [🔧 Issue](https://github.com/varunsridharan/wp-transient-api/issues/) if you need help / found a bug


## 💰 Sponsor
[I][twitter] fell in love with open-source in 2013 and there has been no looking back since! You can read more about me [here][website].
If you, or your company, use any of my projects or like what I’m doing, kindly consider backing me. I'm in this for the long run.

- ☕ How about we get to know each other over coffee? Buy me a cup for just [**$9.99**][buymeacoffee]
- ☕️☕️ How about buying me just 2 cups of coffee each month? You can do that for as little as [**$9.99**][buymeacoffee]
- 🔰         We love bettering open-source projects. Support 1-hour of open-source maintenance for [**$24.99 one-time?**][paypal]
- 🚀         Love open-source tools? Me too! How about supporting one hour of open-source development for just [**$49.99 one-time ?**][paypal]

<!-- Personl Links -->
[paypal]: https://sva.onl/paypal
[buymeacoffee]: https://sva.onl/buymeacoffee
[twitter]: https://sva.onl/twitter/
[website]: https://sva.onl/website/


## Connect & Say 👋
- **Follow** me on [👨‍💻 Github][github] and stay updated on free and open-source software
- **Follow** me on [🐦 Twitter][twitter] to get updates on my latest open source projects
- **Message** me on [📠 Telegram][telegram]
- **Follow** my pet on [Instagram][sofythelabrador] for some _dog-tastic_ updates!

<!-- Personl Links -->
[sofythelabrador]: https://www.instagram.com/sofythelabrador/
[github]: https://sva.onl/github/
[twitter]: https://sva.onl/twitter/
[telegram]: https://sva.onl/telegram/


---

<p align="center">
<i>Built With ♥ By <a href="https://sva.onl/twitter"  target="_blank" rel="noopener noreferrer">Varun Sridharan</a> <a href="https://en.wikipedia.org/wiki/India">
   <img src="https://cdn.svarun.dev/flag-india.jpg" width="20px"/></a> </i> <br/><br/>
   <img src="https://cdn.svarun.dev/codeispoetry.png"/>
</p>

---


<!-- END common-footer.mustache  -->


[composer]: http://getcomposer.org/download/
[downloadzip]:https://github.com/varunsridharan/wp-transient-api/archive/master.zip

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