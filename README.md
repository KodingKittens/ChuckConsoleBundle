# ChuckConsoleBundle

[![Build Status](https://travis-ci.org/KodingKittens/ChuckConsoleBundle.svg)](https://travis-ci.org/KodingKittens/ChuckConsoleBundle)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/KodingKittens/ChuckConsoleBundle/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/KodingKittens/ChuckConsoleBundle/?branch=master)
[![Latest Stable Version](https://poser.pugx.org/kk/chuck-command/v/stable)](https://packagist.org/packages/kk/chuck-command) 
[![Code Coverage](https://scrutinizer-ci.com/g/KodingKittens/ChuckConsoleBundle/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/KodingKittens/ChuckConsoleBundle/?branch=master)
[![Total Downloads](https://poser.pugx.org/kk/chuck-command/downloads)](https://packagist.org/packages/kk/chuck-command) 
[![Monthly Downloads](https://poser.pugx.org/kk/chuck-command/d/monthly)](https://packagist.org/packages/kk/chuck-command)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/0f9a6eb3-4979-4768-bf41-3e5389c3a60d/mini.png)](https://insight.sensiolabs.com/projects/0f9a6eb3-4979-4768-bf41-3e5389c3a60d)

Simple and stupid Symfony2 Bundle displaying a random Chuck Norris fact after every console command.

<img src="http://4.bp.blogspot.com/-3frZS2Q5h94/VQg-0h2ALBI/AAAAAAAAEfc/i6vyhIUH_mo/s1600/chuck-norris.jpg" alt="Chuck Norris Rules" border="0">

##NEW

version 1.3.0:

* new configuration option : environments

version 1.2.0:

* fixed ConnectException issue

version 1.1.0:

* added support for Symfony 3

version 1.0.0:

* Guzzle 6 implementation
* chuck:fact console command to get a fact whenever you need one
* timeout configuration parameter

##Installation

just run :

```bash
composer require kk/chuck-command
composer update
```

and register the bundle in your app/AppKernel.php :

```php
// app/AppKernel.php
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new KK\Labs\ChuckConsoleBundle\KKLabsChuckConsoleBundle(),
        );

        // ...
    }
}
```

##Usage
As simple as using any app/console command.

![Screenshot of ChuckConsoleBundle](https://pbs.twimg.com/media/CC-t99KWAAEH5Gy.png:large)

In case of emergency, can also get a fact when you really need one :

```bash
app/console chuck:fact
#output : Fact: Chuck Norris doesn't consider it sex if the woman survives.
app/console chuck:fact Your boss
#output : Fact: Your boss doesn't consider it sex if the woman survives.
```

##Customization in config.yml file :
```yml
kk_labs_chuck_console:
    who:
        #your first name or anyone's first name
        first_name: "Your first name"
        #your last name or anyone's last name
        last_name: "Your last name"
    #after n seconds, don't wait for response from Chuck API
    timeout: 5
    #environments enabled (default : 'dev')
    environments: ['dev', 'prod', 'custom']
```

##API Credit
API Credit goes to [The Internet Chuck Norris Database](http://www.icndb.com/api/)
