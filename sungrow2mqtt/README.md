# Sungrow2MQTT Home Assistant Add-on

<p align="center">
  <img src="logo.png" width="200" alt="Sungrow2MQTT Logo">
</p>

This add-on integrates **Sungrow SHx inverters** into Home Assistant via Modbus TCP using MQTT. It reads register data and automatically provides them as sensors and other entities.

The project uses the register definitions from [mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant](https://github.com/mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant) and keeps them up to date through automatic updates at startup.

## Features
*   **Modbus TCP Interface**: Direct communication with the inverter (recommended via WiNet-S dongle or LAN port).
*   **MQTT Auto Discovery**: Automatically creates matching entities in Home Assistant (Sensors, Binary).
*   **Automatic Updates**: Downloads the latest `modbus_sungrow.yaml` from GitHub on startup, if available.

## Planned Features

*   **Write Access**: Control the inverter (e.g., force battery charging) via MQTT.
*   **Multi-Inverter Support**: Support for multiple inverters in a single instance.
*   **MQTT Auto Discovery**: Additional entities (Numbers, Button, Select, Switch).

## Installation

1. **Add Repository**: Navigate to **Settings** > **Add-ons** > **Add-on Store**.
2. **Menu**: Click the three-dot menu in the top right and select **Repositories**.
3. **URL**: Add `https://github.com/cyphylax/home-assistant-addons`.
4. **Install**: Search for "Sungrow2MQTT" and click **Install**.
5. **Configuration**: Adjust the settings (see below) and start the add-on.

---

## Configuration

Configuration is done via the "Configuration" tab in the add-on.

| Option | Description | Default |
| :--- | :--- | :--- |
| **Inverter** | | |
| `inverter.host` | IP address or hostname of your Sungrow inverter. | `""` |
| `inverter.port` | Modbus TCP port (usually 502). | `502` |
| `inverter.model` | Inverter model name (e.g., SH10RT). | `""` |
| **MQTT** | | |
| `mqtt.host` | IP address or hostname of your MQTT broker. | `""` |
| `mqtt.port` | Port of your MQTT broker. | `1883` |
| `mqtt.user` | Username for MQTT authentication. | `""` |
| `mqtt.passwd` | Password for MQTT authentication. | `""` |
| **Scan** | | |
| `scan.level` | Scan level for registers (`STANDARD`, `BASIC`, or `FULL`). | `STANDARD` |
| `scan.interval` | Polling interval in seconds. | `30` |
| `scan.timeout` | Modbus connection timeout in seconds. | `5` |
| `scan.connection` | Connection type (usually `Modbus`). | `Modbus` |
| **General** | | |
| `smart_meter` | Set to `true` if a smart meter is connected to the inverter. | `false` |
| `log_level` | Logging verbosity (`DEBUG`, `INFO`, `WARNING`, `ERROR`). | `INFO` |

## Credits & Inspirations

*   [SunGather](https://github.com/bohdan-s/SunGather)
*   [SungrowClient](https://github.com/m-reuter/SungrowClient)
*   [ModbusTCP2MQTT](https://github.com/m-reuter/ModbusTCP2MQTT)
*   [mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant](https://github.com/mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant)

## Legal Notices & Disclaimer

**Disclaimer:** This is a community project and is not officially affiliated with Sungrow Power Supply Co., Ltd.

*   **Use at your own risk:** Manipulating inverter settings via Modbus can lead to damage or loss of warranty if handled improperly. The author assumes no liability for damage to the device or the system.
*   **Third-party Licenses:** This project uses register definitions from [mkaiser](https://github.com/mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant), which are published under the MIT license.
*   **Trademarks:** All mentioned trademarks (Sungrow, Home Assistant, etc.) are the property of their respective owners.

## License

This add-on is published under the [MIT License](LICENSE).

---

**Support:** If you like this add-on, please consider supporting the projects listed under [Credits](#credits--inspirations), as this add-on is built upon their preliminary work.