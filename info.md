![version_badge](https://img.shields.io/badge/minimum%20HA%20version-2021.12-red)
# Yandex weather data provider for Home Assistant 
This custom integration is providing weather component and set of sensors based on data from [yandex weather](https://weather.yadex.ru) service.

## Configuration
1. Go to Yandex [developer page](https://developer.tech.yandex.ru/services)
2. Add Weather API with "Test tariff" _(3000 requests for 30 days for free)_
3. Switch to "Weather for web-site tariff" _(50 requests per day for free)_. It may require up to 30 minutes for activating key.
4. Save API key
5. Go to Home Assistant settings
    * Integrations
    * Add
    * Start typing "Yandex weather" _(clean browser cache if nothing found)_
    * Add integration
    * Put API key into API key field

## Usage
### Weather
#### attributes
 * `entity_picture` -- native Yandex.Weather .svg picture for weather condition
### Sensors
Most sensors are disabled by default to not overload system. 
 
* ![added_in_version_badge](https://img.shields.io/badge/Since-v0.3.0-red) `data update time` -- when weather data was updated (at Yandex side).
* ![added_in_version_badge](https://img.shields.io/badge/Since-v0.4.0-red) `original_condition` -- native Yandex.Weather condition. Because Yandex weather conditions is richer than Home Assistant, some different Yandex.Weather conditions is mapped to same Home Assistant. This sensor will keep original condition.  
* ![added_in_version_badge](https://img.shields.io/badge/Since-v0.6.0-red) `pressure_mmhg` -- pressure in mmHg units. Home Asistant is prefer Pa as pressure units, but mmHg is more familiar for some countries. This sensor is enabled by default. 
### Events
![added_in_version_badge](https://img.shields.io/badge/Since-v0.4.0-red) integration will fire events on weather condition changes. This events may be used for triggering automatizations.
