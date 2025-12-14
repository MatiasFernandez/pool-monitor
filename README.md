# Pool Monitor

A DIY IoT project to monitor your pool water temperature in real-time using Esphome and an ESP32 board.

## Hardware

- **Microcontroller**: Seeed Studio XIAO ESP32S3 (this one is optimized for battery-powered projects)
- **Temperature Sensor**: DS18B20 (1-Wire digital temperature sensor)
- **Power**: Single 18650 lithium battery cell

## Features

- 📊 **Periodic Temperature Monitoring**: Track your pool water temperature at regular intervals
- 🏠 **Home Assistant Integration**: Seamless integration with Home Assistant via native Esphome API
- 🔋 **Low Power Design**: Deep sleep mode to extend battery life

## Setup Instructions

### Hardware details

TBD

### Software Configuration

1. Clone or download this repository
2. Update `secrets.yaml` with your credentials:
   ```yaml
   wifi_ssid: "your_network_name"
   wifi_password: "your_network_password"
   api_encryption_key: "generate_using_esphome"
   ota_password: "generate_using_esphome"
   ```

3. Customize `config.yaml` if needed:
   - Adjust `run_duration` for active sensor reading time
   - Modify `sleep_duration` for deep sleep intervals
   - Update static IP address if desired

### Flashing the Device

```bash
esphome run config.yaml
```

Follow the prompts to select your serial port and build the firmware.

## Power saving

The project uses Esphome's deep sleep functionality to minimize power consumption. The device wakes periodically, reads the temperature sensor, reports the data, then returns to sleep.

## Acknowledgments

- [Neon Ninja](https://neon.ninja/2017/10/smarter-swimming-pool-2-water-temperature/) - Inspiration on sensor mounting design
- [donburch888](https://community.home-assistant.io/t/notes-on-esphome-deep-sleep/860987?hl=es-AR) - Deep sleep optimization techniques with Esphome
- [Esphome](https://esphome.io/) - Excellent open-source firmware framework
- [Home Assistant](https://www.home-assistant.io/) - Powerful open-source home automation platform