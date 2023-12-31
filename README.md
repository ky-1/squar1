<h1 align="center">cheeseRox Beta 2.0.6</h1>

<p align="center">
<img src="https://user-images.githubusercontent.com/45898787/142709724-671da494-3498-4941-bf94-1aa0987fc2a5.png">
<br><br>
<a href="https://www.youtube.com/channel/UCMnG3eA5QcSgIPsavuW4ubA">
<img src="https://img.shields.io/youtube/channel/subscribers/UCMnG3eA5QcSgIPsavuW4ubA?style=social">
</a>
<br>
</p>

<!--<h3 align="center"><a href="https://squarebracket.veselcraft.ru/">cheeseRox's live website</a></h3>-->

## How to setup cheeseRox.
1. Get a web server (Apache/NGINX) with PHP and MariaDB up and running, including Composer.
1. Run `composer update` from the terminal.
1. Copy `config.sample.php`, rename it to `config.php` and fill in your database credentials.
1. Import the database dump found in `sql/` into the database you want to use.
1. Either run the `compile-scss-sassc` or `compile-scss-dartsass` script available in the tools directory to generate CSS. This will be a bit more complicated for Windows 7 users.
1. (Optional for Discord webhook functionality) Enable the cURL module in PHP.

### Production specific
1. Instead of installing dependencies using `composer update` you do `composer update --no-dev`
1. Make the `videos/`, `templates/cache/` and `assets/thumb/` directories writable by your web server.

### Development specific
1. Disable Twig's template caching by setting `$tplNoCache` to true.
1. Enable debugging features by setting `$isDebug` to true.
1. If you want to be able to upload videos during development, make the `videos/` and `assets/thumb/` directory writable by your web server.

## Questions

## Why is it closed source?
Bhief.

![image](https://user-images.githubusercontent.com/45898787/144720541-f5e3a389-b205-40ee-80cb-5f7d2e376fd5.png)

We will make cheeseRox open source ONLY when Bhief quits the OYC (Old YouTube Community).

### How do I translate cheeseRox?
squareBracket Translations: https://crowdin.com/project/squarebracket

RelativeTime Repo (used for dates): https://github.com/mpratt/RelativeTime

### Why use Twig? Why not just PHP?
Twig literally makes HTML injection attacks a thing of the past. It's more short and concise than PHP's "templating" syntax, it supports layout inheritance and it allows for more code reuse and it's versatile for creating more frontends in the future. It's secure (it treats all variables as "unsafe" and automatically escapes them unless you explicitly mark them as safe), concise (its liquid-like syntax is shorter and way more appropriate for the context of templating) and fast (with caching enabled there's basically no overhead compared to not using Twig).

### Why ditch Bootstrap?
We had problems with it, hense we're writing our own custom SCSS (called Finalium) for cheeseRox's new layout, which is sbNext.

However, Finalium uses parts of the Bootstrap 3 grid system for better compatibility.
