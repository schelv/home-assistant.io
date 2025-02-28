---
title: Random
description: Instructions on how to integrate random numbers into Home Assistant.
ha_category:
  - Binary Sensor
  - Sensor
  - Utility
ha_iot_class: Local Polling
ha_release: 0.32
ha_quality_scale: internal
ha_codeowners:
  - '@fabaff'
ha_domain: random
ha_platforms:
  - binary_sensor
  - sensor
ha_integration_type: integration
---

The `random` integration simply creates random values or state. This can be useful if you want to test automation rules or run an interactive demo. It generates a new state every time it is polled.

## Binary Sensor

The `random` binary sensor platform is creating random states (`true`, 1, `on` or `false`, 0, `off`).

### Configuration

To enable the random binary sensor, add the following lines to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
binary_sensor:
  - platform: random
```

{% configuration %}
name:
  description: Name to use in the frontend.
  required: false
  type: string
  default: Random Binary Sensor
{% endconfiguration %}

## Sensor

The `random` sensor platform is creating random sensor values (integers) out of a given range. Returned values form a [discrete uniform distribution](https://en.wikipedia.org/wiki/Discrete_uniform_distribution), meaning that each integer value in the range configured is equally likely to be drawn.

### Configuration

To enable the random sensor, add the following lines to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
sensor:
  - platform: random
```

{% configuration %}
name:
  description: Name to use in the frontend.
  required: false
  type: string
  default: Random Sensor
minimum:
  description: Lower limit for the values.
  required: false
  type: string
  default: 0
maximum:
  description: Upper limit for the values.
  required: false
  type: integer
  default: 20
unit_of_measurement:
  description: Defines the units of measurement of the sensor, if any.
  required: false
  type: string
{% endconfiguration %}

### Examples

In this section you find am example of how this sensor can be used.

Create a random sensor called "My random sensor" which will return a number between 10 (minimum) and 500 (maximum).

```yaml
# Example configuration.yaml entry
sensor:
  - platform: random
    name: "My random sensor"
    minimum: 10
    maximum: 500
```
