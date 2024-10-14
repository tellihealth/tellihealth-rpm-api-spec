### Device behavior description

A new heartbeat was received from the device.

By default, Gen2 devices send 3 heartbeats per 24-hour period, or one heartbeat every 8 hours. The heartbeat timer resets each time a device is operated; therefore, the next heartbeat will be received \+8 hours from the device's last successful operation.

For example, if a user takes one reading per day, then depending on connectivity and sufficient battery, expect the device to receive one reading and two heartbeats during that day.

Gen2 devices capable of alert reminders must have the alert reminder enabled with a set start and stop time. When a device is in reminder mode (for example, if the start time is 08:00 and it is now 08:05), the heartbeat message will be delayed until the reminder is cleared.
