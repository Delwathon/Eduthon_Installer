# Laravel Web Installer | A Web Installer [Package](https://packagist.org/packages/delwathon/eduthon-installer)

[![Total Downloads](https://poser.pugx.org/delwathon/eduthon-installer/d/total.svg)](https://packagist.org/packages/delwathon/eduthon-installer)
[![Latest Stable Version](https://poser.pugx.org/delwathon/eduthon-installer/v/stable.svg)](https://packagist.org/packages/delwathon/eduthon-installer)
[![License](https://poser.pugx.org/delwathon/eduthon-installer/license.svg)](https://packagist.org/packages/delwathon/eduthon-installer)

- [About](#about)
- [Requirements](#requirements)
- [Installation](#installation)
- [Routes](#routes)
- [Usage](#usage)
<!-- - [Contributing](#contributing)
- [Help](#help) -->
- [Screenshots](#screenshots)
<!-- - [License](#license) -->

## About

We want our clients to be able to install a our Eduthon project just like they do with WordPress or any other CMS?
This Laravel package allows users who don't use Composer, SSH etc to install your application just by following the setup wizard.
The current features are :

- Check For Purchase Code Authenticity.
- Check For Server Requirements.
- Check For Folders Permissions.
- Ability to set database information.
	<!-- - .env text editor -->
- .env form wizard
- Migrate The Database.
- Seed The Tables.

## Requirements

* [Laravel 5.1, 5.2, 5.3, 5.4, or 5.5+](https://laravel.com/docs/installation)

## Installation

1. From your projects root folder in terminal run:

```bash
    composer require delwathon/eduthon-installer
```

2. Register the package

* Laravel 5.5 and up
Uses package auto discovery feature, no need to edit the `config/app.php` file.

* Laravel 5.4 and below
Register the package with laravel in `config/app.php` under `providers` with the following:

```php
	'providers' => [
	    Delwathon\LaravelInstaller\Providers\LaravelInstallerServiceProvider::class,
	];
```

3. Publish the packages views, config file, assets, and language files by running the following from your projects root folder:

```bash
    php artisan vendor:publish --tag=laravelinstaller
```

## Routes

* `/install`
* `/update`

## Usage

* **Install Routes Notes**
	* In order to install your application, go to the `/install` route and follow the instructions.
	* Once the installation has ran the empty file `installed` will be placed into the `/storage` directory. If this file is present the route `/install` will abort to the 404 page.

* **Update Route Notes**
	* In order to update your application, go to the `/update` route and follow the instructions.
	* The `/update` routes countes how many migration files exist in the `/database/migrations` folder and compares that count against the migrations table. If the files count is greater then the `/update` route will render, otherwise, the page will abort to the 404 page.

* Additional Files and folders published to your project :

|File|File Information|
|:------------|:------------|
|`config/installer.php`|In here you can set the requirements along with the folders permissions for your application to run, by default the array cotaines the default requirements for a basic Laravel app.|
|`public/installer/assets`|This folder contains a css folder and inside of it you will find a `main.css` file, this file is responsible for the styling of your installer, you can overide the default styling and add your own.|
|`resources/views/vendor/installer`|This folder contains the HTML code for your installer, it is 100% customizable, give it a look and see how nice/clean it is.|
|`resources/lang/en/installer_messages.php`|This file holds all the messages/text, currently only English is available, if your application is in another language, you can copy/past it in your language folder and modify it the way you want.|

<!-- ## Contributing

* If you have any suggestions please let me know : https://github.com/Delwathon/LaravelInstaller/pulls.
* Please help us provide more languages for this awesome package please send a pull request https://github.com/Delwathon/LaravelInstaller/pulls. -->

<!-- ## Help

* Cannot figure it out? Need more help? Here is a video tutorial: [Laravel Installer by Devdojo](https://www.youtube.com/watch?v=Jput5doFYLg) -->

## Screenshots

###### Installer
![Laravel web installer | Step 1](https://i.ibb.co/6b3s0FV/Delwathon-Installer.png)
![Laravel web installer | Step 2](https://i.ibb.co/S7bhtF6/Delwathon-Installer-1.png)
![Laravel web installer | Step 3](https://i.ibb.co/ThrR6b2/Delwathon-Installer-2.png)
![Laravel web installer | Step 4](https://i.ibb.co/yqGwVTc/Delwathon-Installer-3.png)
![Laravel web installer | Step 5](https://i.ibb.co/HYZh9BC/Delwathon-Installer-4.png)
![Laravel web installer | Step 6](https://i.ibb.co/YTrNCLZ/Delwathon-Installer-5.png)
![Laravel web installer | Step 7](https://i.ibb.co/j44NzBt/Delwathon-Installer-6.png)
![Laravel web installer | Step 58](https://i.ibb.co/23m8yk8/Delwathon-Installer-7.png)

<!-- ###### Updater
![Laravel web updater | Step 1](https://s3-us-west-2.amazonaws.com/github-project-images/eduthon-installer/update/1-welcome.jpg)
![Laravel web updater | Step 2](https://s3-us-west-2.amazonaws.com/github-project-images/eduthon-installer/update/2-updates.jpg)
![Laravel web updater | Step 3](https://s3-us-west-2.amazonaws.com/github-project-images/eduthon-installer/update/3-finished.jpg)

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Treeware

You're free to use this package, but if it makes it to your production environment I would highly appreciate you buying the world a tree.

It’s now common knowledge that one of the best tools to tackle the climate crisis and keep our temperatures from rising above 1.5C is to [plant trees](https://www.bbc.co.uk/news/science-environment-48870920). If you contribute to my forest you’ll be creating employment for local families and restoring wildlife habitats.
