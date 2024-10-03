**SolaX cloud for Home assistant**
*Based on version 2 of the API*

### SolaX Cloud Integration for Home Assistant (Based on API V2)

This Home Assistant integration fetches data from the SolaX Cloud using the official API V2, as described in the 1.2 API documentation. It was initially developed as an improvement over the API V1 integration, from which it was forked. However, several significant changes have been made.

### Key Differences:

- Unlike the original V1 version, this one groups all sensors under a RESTful API.
- The sensors are fully configured with measurement types, making them compatible with Home Assistant’s energy monitoring features.
- Sensors do not return `0.00` when no data is available. Instead, they leave gaps, allowing Home Assistant to handle the absence of data correctly. A `0` reading would inaccurately indicate a measured value of zero, which is not the case.

### Requirements:

- **Inverter Serial Number** (Refer to the official SolaX documentation below for guidance)
- **Token ID:** [Generate here](https://www.solaxcloud.com/#/api)

### Installation:

1. Edit the `secrets.yaml` file (refer to `secrets.yaml.sample` for reference).
2. Create a `rest` directory in the configuration directory (`config/`).
3. Update the configuration file (refer to `configuration.yaml.sample`).

### Additional Notes:

- The **SolaX Cloud site** displays the total energy yield of the entire site, while the API fetches data directly from the inverter. This can lead to differences in the reported totals, especially if a new inverter was installed or there were issues during the initial setup.
- For the most accurate and reliable energy data, it is recommended to pull information directly from the energy meter. The energy meter provides certified and precise readings, ensuring you get the correct data. Using the inverter's data might lead to discrepancies in total yield values.

### Official API Documentation:

Official API Documentation: [SolaX API Documentation v1.2](https://github.com/Travelbacon/homeassistant-solax-api-V2/blob/main/misc/SolaXCloud%20User%20API%20V2-1-2.pdf).
