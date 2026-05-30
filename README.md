# ac-infinity-hacs
 Custom Integration to test AC Infinity Controllers

1.0.4

Added Airtap T4 (device type ID 6) to DEVICE_MODEL in const.py

Added FanEntityFeature.TURN_ON | FanEntityFeature.TURN_OFF to _attr_supported_features in fan.py (fixes "does not support action fan.turn_off" error in HA 2026.3.4+)

Fixed _async_update_attrs in fan.py to guard against None or zero fan speed when computing percentage

Fixed config_flow.py to skip non-AC-Infinity Bluetooth devices during discovery (fixes "500 Internal Server Error" when loading config flow)

Fixed config_flow.py to abort with "no_devices_found" if no AC Infinity devices are visible in BT scan, instead of showing an empty/broken address form

Fixed config_flow.py to safely handle missing address in _discovered_devices on form submit

Added not_supported and device_not_found error strings to strings.json and translations/en.json

Note:
For the Airtap vent fans, humidity is provided as an entity but these devices have no humidity sensor.
