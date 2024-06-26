# HA-ecowitt-rest-yaml
Alternative to integrate EcoWitt Weatherstation through REST API to Home Assistant

To use this yaml example you will have to create an application and API key on the ecowitt server first.

Open https://www.ecowitt.net/home/user and go to your profil to create new keys. (see example folder for screenshots)

once you have the two keys get the mac address of your EcoWitt Gateway.

replace the placeholders in the yaml with the three values you just retrieved

https://api.ecowitt.net/api/v3/device/real_time?application_key=<application key>&api_key=<API key>&mac=<gateway mac>&call_back=all

when you open that url in the browser you will get the JSON and can check if it is working properly.

On your HA create a folder named integrations in the config folder. Place the ecowitt.yaml in that folder.
To include the configuration file (if not yet existing) open the /config/configuration.yaml and add the following lines to it

homeassistant:
  packages: !include_dir_named integrations

last but not least restart your HA to get the new entities.
