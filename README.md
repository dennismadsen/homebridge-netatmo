[![npm](https://img.shields.io/npm/v/homebridge-eveatmo.svg?style=plastic)](https://www.npmjs.com/package/homebridge-eveatmo)
[![npm](https://img.shields.io/npm/dt/homebridge-eveatmo.svg?style=plastic)](https://www.npmjs.com/package/homebridge-eveatmo)
[![GitHub last commit](https://img.shields.io/github/last-commit/skrollme/homebridge-eveatmo.svg?style=plastic)](https://github.com/skrollme/homebridge-eveatmo)

# homebridge-eveatmo

This is a [homebridge](https://github.com/nfarina/homebridge) plugin which lets you integrate your non-HomeKit Netatmo Weatherstation into HomeKit.

Whilst the original [homebridge-netatmo](https://github.com/planetk/homebridge-netatmo)-plugin goes a mostly HomeKit-standard approach (predefined services, characteristics, ...), this plugin tries to mimic the Elgato Eve devices (currently *Room* and *Weather*) as close as possible. 

## Hint
**Because this is a work-in-progress project which is neither feature-complete nor fully testet this readme is more of a stub. Use at your own risk.**

## Configuration
Because this plugin's base was taken from [homebridge-netatmo](https://github.com/planetk/homebridge-netatmo) (see above) you can adapt its config. Just use the plattform-code "eveatmo" and remove "ttl" and/or the other "refresh_" properties for the beginning.

```
"platforms": [
        {
            "platform": "eveatmo",
            "name": "eveatmo platform",
            "extra_co2_sensor": false,
            "ttl": 540,
            "auth": {
    	        "client_id": "XXXXX Create at https://dev.netatmo.com/",
                "client_secret": "XXXXX Create at https://dev.netatmo.com/",
                "username": "your netatmo username",
                "password": "your netatmo password"
            }
        }
    ],

```

- **extra_co2_sensor:** Adds an extra CO2 sensor which is available via Apple's stock Home.app, too.
- **ttl:** Seconds between two Netatmo API polls. Lower is not neccessarily better! The weatherstation itself collects one value per 5minutes, so going below 300s makes no sense
- **auth:** Credentials for the Netatmo API

### Retrieve client id and secret

1. Register at http://dev.netatmo.com as a developer
2. After successful registration create your own app by using the menu entry "CREATE AN APP"
3. On the following page, enter a name for your app. Any name can be chosen. All other fields of the form (like callback url, etc.) can be left blank.
4. After successfully submitting the form the overview page of your app should show client id and secret.

## History

see [HISTORY.md](https://github.com/skrollme/homebridge-eveatmo/blob/master/HISTORY.md)

## ToDos
- <del>maybe refactoring to split characterstics into separate services (better functionality in Apple's default home.app)</del>
- reintegrate <del>rain-sensor, wind-sensor and</del> thermostat
- <del>adding CO2 [ppm] or maybe just "CO2 detected" to indoor devices</del>
- <del>researching/testing/implementing Eve's history-functionality (see: [https://gist.github.com/0ff/668f4b7753c80ad7b60b](https://gist.github.com/0ff/668f4b7753c80ad7b60b))</del>

## Thanks

This plugin's basic structure and most of its basic code is a fork (ok, lets say "copy") of [homebridge-netatmo](https://github.com/planetk/homebridge-netatmo). So big thanks to @planetk and all the other contributors of this project. 

Also big thanks to @gomfunkel and @simont77 for [this gist](https://gist.github.com/gomfunkel/b1a046d729757120907c) and its [fork](https://gist.github.com/simont77/3f4d4330fa55b83f8ca96388d9004e7d), @KhaosT for [this gist](https://gist.github.com/KhaosT/e365acfd589ce840a403), @mplewis for [this gist](https://gist.github.com/mplewis/def678dc4b6e63a86905) and @0ff for [this (almost) working Eve Weather imitating homebridge-plugin](https://gist.github.com/0ff/668f4b7753c80ad7b60b) and once again special thanks to @simont77 for his endurance in digging deeper in Eve's custom characteristics and its protocols.

## What else

Like this and want to express your feelings? Please buy me a beer :beers: ...

[![Donate](https://img.shields.io/badge/Donate-PayPal-blue.svg)](https://www.paypal.me/skroll)

Cheers go to:
- @DJay79 (x2)
- s.k**********r@aon.at
- C. Schneider
- S. Eisenkrämer



