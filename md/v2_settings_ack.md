### Device behavior description

A device responded to a settings change request.

Gen2 devices may receive settings for reminder alerts. Since the device may be off at the time the settings are sent, this message is delivered asynchronously. The device responds during its next successful connection session. When the platform receives an acknowledgement (ACK) from the device, the platform publishes an ACK to the registered endpoint.
