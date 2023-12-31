CHANGELOG
=================

View diff for a specific commit:  
https://github.com/johnkary/phpunit-speedtrap/commit/XXX where XXX is the commit hash

View diff between two versions:  
https://github.com/johnkary/phpunit-speedtrap/compare/v4.0.0...v5.0.0

## 5.0 (xxxx-xx-xx)

Version 5.0 is the largest change since v1.0. It now uses PHPUnit's Extension
and Hook systems, which have more restrictions on what an Extension is allowed
to do.

Changes are required if you have extended SpeedTrapListener. See
[UPGRADE.md](UPGRADE.md) for upgrading your subclass to support 5.0.

* SpeedTrap now requires PHPUnit 8+ and PHP 7.2+,
* Moved namespace from `JohnKary\PHPUnit\Listener\SpeedTrapListener` to `JohnKary\PHPUnit\Extension\SpeedTrap`
* `phpunit.xml` requires registering using <extension> element instead of <listener> element. See README.
* Removed option `stopOnSlow` because Extensions can no longer manipulate the Test Runner

## 4.0.1 (2022-10-16)

* README documents working with Symfony Framework `simple-phpunit`

## 4.0.0 (2021-05-03)

* Changelog ([`v3.3.0...v.4.0.0`](https://github.com/johnkary/phpunit-speedtrap/compare/v3.3.0...v4.0.0))
* [PR #81](https://github.com/johnkary/phpunit-speedtrap/pull/81) Reformat slow test case output for compatibility with PHPUnit --filter option
* [PR #82](https://github.com/johnkary/phpunit-speedtrap/pull/82) New option `stopOnSlow` stops execution upon first slow test. Default: false.
* [PR #84](https://github.com/johnkary/phpunit-speedtrap/pull/84) New annotation option `@slowThreshold 0` disables checks for individual tests.

## 3.3.0 (2020-12-18)

Version 3.3 adds supports for PHPUnit 9.5+, and a way to enable or disable the SpeedTrap listener using environment variables.

* [PR #73](https://github.com/johnkary/phpunit-speedtrap/pull/73) Compatibility with PHPUnit 9.5
* [PR #66](https://github.com/johnkary/phpunit-speedtrap/pull/66) Environment variable PHPUNIT_SPEEDTRAP="disabled" can disable profiling

## 3.2.0 (2020-02-12)

Version 3.2 introduces supports for PHPUnit 9.0+.
If your use of SpeedTrap depends on specific text output from SpeedTrap slowness
report, see below wording changes that may require updating your implementation.

* [PR #57](https://github.com/johnkary/phpunit-speedtrap/pull/57) Wording change to slowness report in renderHeader()

## 3.1.0 (2019-02-23)

Version 3.1 introduces support for PHPUnit 8.0+.

## 3.0.0 (2018-02-24)

Version 3.0 introduces support for PHPUnit 7.0+ and PHP 7.1+.

Changes may be required if you have extended SpeedTrapListener. See
[UPGRADE.md](UPGRADE.md) for upgrading your subclass to support 3.0.

* [PR #41](https://github.com/johnkary/phpunit-speedtrap/pull/41) Make compatible with phpunit 7.x

## 2.0.0 (2017-12-06)

Version 2.0 introduces support for PHPUnit 6.0+, PHP 7.0+ and PSR-4 autoloading.

Changes are required if you have extended SpeedTrapListener. See
[UPGRADE.md](UPGRADE.md) for upgrading your subclass to support 2.0.

* [PR #26](https://github.com/johnkary/phpunit-speedtrap/pull/26) Support PHPUnit 6.0
* [PR #30](https://github.com/johnkary/phpunit-speedtrap/pull/30) Add PHP 7 features (includes backwards compatibility breaks, see UPGRADE.md)
* [PR #31](https://github.com/johnkary/phpunit-speedtrap/pull/31) Support PSR-4 autoloading
* [PR #39](https://github.com/johnkary/phpunit-speedtrap/pull/39) SpeedTrapListener extends PHPUnit BaseTestListener
