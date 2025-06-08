<ins>**VPD and Temperature-Based Controller for Humidifier, Cooler, Heater, and Dehumidifier**</ins>

Overview
This Home Assistant Blueprint controls a humidifier, cooler, heater, and dehumidifier as simple On/Off switches, independently based on:

VPD (Vapor Pressure Deficit) value (in kPa)

Temperature (in °C)

Humidity (in %)




<ins>_**Features:**_</ins>

✅ Humidifier Control

Turns ON when VPD exceeds the threshold.

Turns OFF when VPD drops below the threshold.

✅ Cooler Control

Turns ON when VPD exceeds the threshold.

Turns ON when temperature exceeds the threshold.

Turns OFF when temperature drops below the threshold, unless activated by VPD.

✅ Heater Control

Turns ON when temperature drops below the threshold.

Turns OFF when temperature rises above the threshold.

✅ Dehumidifier Control

Turns ON when humidity exceeds the threshold.

Turns OFF when humidity drops below the threshold.

✅ Failsafe Dummy Switch

If a device is not available, a Dummy Switch (switch.dummy_switch) is used as a placeholder to prevent errors.

✅ Automatic Updates

The automation triggers every 10 seconds to ensure real-time adjustments.




<ins>**Installation Guide**</ins>

1️⃣ Set Up the Dummy Switch (Optional) If you don’t have a heater or dehumidifier, you need a Dummy Switch as a placeholder to prevent errors.

Create a Dummy Switch in configuration.yaml

Open Home Assistant.

Go to → File Editor. (Add-On)

Open the configuration.yaml file.

Add the code from the dummy.switch file

Save the file.

Restart Home Assistant:

Go to Settings → System → Server Controls → Restart.

2️⃣ Install the VPD Controller Blueprint Using the File Editor Open Home Assistant.

Go to Settings → File Editor.

Navigate to config/blueprints/automation/.

Create a new folder (if needed) and name it VPD_Controller.

Upload or paste the VPD_Controller.yaml file into this folder.

Save the file.

3️⃣ Configure the Automation Go to Settings → Automations & Scenes.

Click "Create Automation" and select the VPD Controller Blueprint.

Assign the correct sensor entities:

VPD Sensor

Temperature Sensor

Humidity Sensor

Select your humidifier, cooler, heater, and dehumidifier.

If a device is missing, choose switch.dummy_switch as a placeholder.

4️⃣ Save and Activate Click "Save" to store the automation.

Enable the automation to start controlling your climate devices.

5️⃣ Restart Home Assistant (if needed) If you added a Dummy Switch, restart Home Assistant:

Settings → System → Server Controls → Restart.
