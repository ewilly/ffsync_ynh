<!--
N.B.: This README was automatically generated by https://github.com/YunoHost/apps/tree/master/tools/README-generator
It shall NOT be edited by hand.
-->

# Firefox Sync Server for YunoHost

[![Integration level](https://dash.yunohost.org/integration/ffsync.svg)](https://dash.yunohost.org/appci/app/ffsync) ![Working status](https://ci-apps.yunohost.org/ci/badges/ffsync.status.svg) ![Maintenance status](https://ci-apps.yunohost.org/ci/badges/ffsync.maintain.svg)
[![Install Firefox Sync Server with YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=ffsync)

*[Lire ce readme en français.](./README_fr.md)*

> *This package allows you to install Firefox Sync Server quickly and simply on a YunoHost server.
If you don't have YunoHost, please consult [the guide](https://yunohost.org/#/install) to learn how to install it.*

## Overview

The Sync Server provides a replacement for Firefox’s default server (hosted at Mozilla).

By default, a server set up will defer authentication to the Mozilla-hosted accounts server at [https://accounts.firefox.com](https://accounts.firefox.com). So you will still have to authenticate at Mozilla, but _the storage of your information will be done on your host_.

**Shipped version:** 1.9.1~ynh4
## Disclaimers / important information

## Configuration

Once installed, reaching `http://domain.tld/path` should show a page explaining how to configure it.

### Solving problems with Android

The sure-fire way to know what Sync on Android is really doing is to observe the Android device log using adb logcat. You’ll want to bump your log-level:
```
adb shell setprop log.tag.FxAccounts VERBOSE
```

Then, you can observe the log using:
```
adb logcat | grep FxAccounts
```

It’s best to observe the log while you force a sync from the Android Settings App. You should see output like:

```
D FxAccounts(...) fennec :: BaseResource :: HTTP GET https://token.stage.mozaws.net/1.0/sync/1.5
...
D FxAccounts(...) fennec :: BaseResource :: HTTP GET https://sync-4-us-east-1.stage.mozaws.net/
```

## :red_circle: Antifeatures

- **Upstream not maintained**: This software is not maintained anymore. Expect it to break down over time, be exposed to unfixed security breaches, etc.

## Documentation and resources

* Official admin documentation: <https://mozilla-services.readthedocs.io/en/latest/howtos/run-sync-1.5.html>
* Upstream app code repository: <https://github.com/mozilla-services/syncserver>
* YunoHost documentation for this app: <https://yunohost.org/app_ffsync>
* Report a bug: <https://github.com/YunoHost-Apps/ffsync_ynh/issues>

## Developer info

Please send your pull request to the [testing branch](https://github.com/YunoHost-Apps/ffsync_ynh/tree/testing).

To try the testing branch, please proceed like that.

``` bash
sudo yunohost app install https://github.com/YunoHost-Apps/ffsync_ynh/tree/testing --debug
or
sudo yunohost app upgrade ffsync -u https://github.com/YunoHost-Apps/ffsync_ynh/tree/testing --debug
```

**More info regarding app packaging:** <https://yunohost.org/packaging_apps>
