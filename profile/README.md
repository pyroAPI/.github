# 🔥PyroAPI

PyroAPI is a minimal, fast backend framework purpose-built for IoT and embedded systems. It is designed to operate reliably in resource-constrained environments such as microcontrollers, single-board computers, and edge devices. PyroAPI helps streamline sensor data collection, real-time communication, and control tasks without unnecessary overhead.

## Key Features

- Minimal core for quick boot-up and low memory usage
- Native MQTT and REST API support
- Modular router system for defining endpoints
- Token-based authentication support
- Built-in logger and optional database connectors
- Compatible with Raspberry Pi, ESP32 (via serial relay), and similar platforms

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/pyroAPI/pyroapi.git
cd pyroapi
pip install -r requirements.txt
````

## Quick Start

### REST Example

```python
# run.py
from pyroapi import App

app = App()

@app.route("/temperature", methods=["POST"])
def handle_temp(request):
    data = request.json()
    # Process data
    return {"status": "ok"}

app.run()
```

### MQTT Example

```python
# mqtt_run.py
from pyroapi.mqtt import MqttServer

mqtt = MqttServer()

@mqtt.on_message("sensor/temperature")
def receive_temperature(payload):
    print("Temperature:", payload)

mqtt.run()
```

## When to Use PyroAPI

* Lightweight data relay from sensors and edge devices
* Building dashboards or control panels for microcontroller-based systems
* Local gateway systems for home automation or industrial setups
* Quick prototyping of REST or MQTT-based IoT applications

## Documentation

* [Getting Started](https://github.com/pyroAPI/pyroapi/wiki/Getting-Started)
* [API Reference](https://github.com/pyroAPI/pyroapi/wiki/API)
* [Example Projects](https://github.com/pyroAPI/pyroapi/tree/main/examples)

## Contributing

We welcome contributions, especially from embedded developers and system integrators. Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for setup instructions and guidelines.

## License

This project is licensed under the MIT License.
