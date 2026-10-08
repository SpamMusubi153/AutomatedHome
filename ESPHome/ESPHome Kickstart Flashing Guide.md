# Onboarding EspHome-Kickstart Devices to Home Assistant

Last Updated 10/8/2026

### Prerequisites:
- Access to a Home Assistant instance with the ESPHome "app"/"add-on" installed
- WiFi credentials for a network that your Home Assistant instance is on (or can access)
- A second device such as a phone or computer with a webbrowser you can use to give your kickstart device the WiFi credentials
- (Useful) A way to determine the IP address of your Kickstart device when it joins your WiFi


### Steps:
1. Plug in the ESPHome-Kickstart device and wait for a "kickstart-[...]" WiFi to appear.
2. Connect to the Kickstart WiFi and enter your WiFi credentials.
3. Inside Home Assistant, locate ESPHome and create a new device configuration that matches the hardware of your kickstart device. (Other guides describe how these configurations can be made; sample configurations are available under the "ESPHome Device Configurations" folder)
    - Make sure to uniquely name your device -- this helps keep your setup expandable.
    - Make sure to auto-generate a unique API key (to keep communications to and from your device encrypted). This should be stored in ESPHome secrets.
4. Press "Install" on your ESPHome configuration, and choose an advanced option "Device IP or Hostname". Enter the IP address of your Kickstart device.
    - If you don't know the IP address of your device, you can add it to Home Assistant first under "Devices & Services". To prevent things from being mixed up later, however, it is usually best to remove the device from Home Assistant immediately before installing the configuration on ESPHome.
5. After the ESPHome firmware builds and installs (it could take a few minutes) you can add your device to Home Assistant as you usually would under the "ESPHome" integration.
    - If the device still appears as something with "kickstart" in its name (or requests an API Key), manually press "Add Integration -> EspHome" and enter the IP address of your device again. Home Assistant will force discovery again and shoul dhave the proper credentials.