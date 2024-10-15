# Telli Health Developer's Guide and Specifications

Welcome to the Telli Health Developer Guide, which will guide you through the Telli Health integration process, and focuses on how to get data from, or send data to, Telli Health's patient monitoring devices.

## Device Generations Overview

Telli Health has Generation 1 and Generation 2 patient monitoring devices in circulation.  
* Generation 1 devices send basic reading data to the platform in a unidirectional method using HTTPS.  
* Generation 2 devices use secure bi-directional messaging to send readings, device data, checkin (AKA heartbeat) messages, and acknowledgments to the platform. The Gen2 devices can receive settings requests, which may vary based on the models' capabilities.

Devices that currently support Gen2 capabilities: TelliBP01

To provide a seamless transition between API versions and device generations, readings from either generation device are cross-compatible with either API version endpoint. Therefore, Gen1 device readings can be received on API v2 endpoints, and Generation 2 device readings can be received on existing API v1 endpoints.
  
**NOTE:** Other Gen2 device capabilities and data are NOT supported on API v1 endpoints.

## Getting Started

It is easy to integrate with our hardware before purchasing Telli Health devices. The OpenAPI specification provides the information needed to develop ingestion slugs and control interfaces.

Telli Health highly recommends creating a single endpoint for all message types or a single endpoint slug for each message type, such as readings, heartbeat messages, or setting acknowledgements. The endpoint should parse and handle the inbound data based on the message type in the schema object.  

For full system functionality, the platform developer must provide Telli Health with the following information:

* The enabled slug endpoint or endpoints;  
* The API version currently supported, and  
* The API key required to access the HTTPS endpoint while sending information.

In exchange, Telli Health provides the developer with an API key for calling the endpoint(s) on the Telli Health platform.  

After you purchase Telli Health devices, you will receive an email containing the Device ID and Serial number for the device(s); you must match each device to a user on your platform.

## Data Transmission Overview
All integrations must be able to receive readings via the readings webhook. As Telli Health’s listener receives readings, Telli Health's data gateway sends your data to the POST URL  in your profile in near real-time by HTTPS POST. Telli Health’s POST will come from multiple US – East Amazon Cloud Storage IP addresses.  

For high availability, data packets are replicated in a Telli Health Secure Database in the event of system outages. Contact Telli Health support if you require a playback of your device readings data.

## Authentication and Token Management

The Telli Health platform recommends that you authenticate and secure inbound and outbound connections.

Successful authentication creates a token that grants access to protected resources. To secure your connection, request an authentication token that you can add to all headers:  
```
x-api-key: \<token\>  
```
Contact Telli Health support to enable authentication.
