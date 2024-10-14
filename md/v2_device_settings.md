### Device behavior description

The device’s settings will be updated.

Gen2 devices may receive settings for the reminder alerts. Since the device may be off at the time the settings are sent, this message is delivered asynchronously. The device responds during its next successful connection session. When the platform receives an acknowledgement (ACK) from the device, the platform publishes an ACK to the registered endpoint. When the settings endpoint is called between ACK messages, the settings value updates to the newly requested value.
