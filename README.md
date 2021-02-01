# IoT_Startup
This document shows the most common IoT services and how to interface with them. 

 



## The embedded system documentations:
- What RTOS (real time opersating system) that can be used
- Cost for RTOS
- Supported boards
- How to get started with each RTOS

## IoT core and services
- Cloud services
- Edge/offline
- Mobile



# Amazon AWS
1. AWS freeRTOS [Github](https://github.com/aws/amazon-freertos)
    - Based on MIT freeRTOS that has added functions to talk to AWS services using best practices.
    - Open source and can be added ported to work with any manufacturers API
    - [Supported Boards](AWS_supported_boards.md)
    - Includes all of the security protocols (tls, wss, etc)

2. IoT Core
    - Acts as an MQTT broker that any device can publish/subscribe to.
      - Cost: Up to 1 billion messages: $1.00 (per million messages) (message is 5KB)
    - With Device Shadow IoT core can store the state of sensors/devices even if the subscribing device isn't online. This allows the subscribing device to have the most accurate information when it boots up without having to make a call to the publishing device.
      - Cost:Device Shadow and Registry pricing: $1.25 (per million operations) (operations are writes/reads)
    - Set up and manage LoRaWAN network.
      - Cost: Up to 1 billion messages: $2.30 (per million messages)
    - Alexa integration

## STM32 Using freeRtos
  freeRtos can be used inside of STM32Cube by enabling it under the "Middleware" tab. STM32 uses an abstraction layer, CMSIS, to interface with freeRtos. CMSIS functions control the timing/priority of the tasks/threads. An overview of CMSIS and its functions can be found [here](https://arm-software.github.io/CMSIS_5/RTOS2/html/rtos_api2.html#rtos_api2_basics).



# Microsoft Azure
1. Microsoft Azure RTOS [Github](https://github.com/azure-rtos)
    - It is a paid license based RTOS (except for manufacturers that have agreements) and is a lighter weight more optimized solution than freeRTOS.
    - There are different levels of RTOS that add features (ex: file systems, gui, etc) that can be added to the base ThreadX RTOS.
    - Azure RTOS is pre-certified for a variety of safety standards. These include the IEC 61508 SIL 4, IEC 62304 Class C, and ISO 26262 ASIL D certifications. Azure RTOS ThreadX is also DO-178 certified
    - [Supported Boards](Azure_supported_boards.md)
    - Includes all of the security protocols (tls, wss, etc)
2. IoT Hub
    - Handles multiple messaging patterns and can also handle file uploads and transfers
      - Cost: Subscription based and has different tiers. S1 $25 for 400,000 messages	(message is 4 KB)



## Checklist:
- ### Amazon
  - [ x ] aws freeRTOS
  - [ x ] Supported boards 
  - [ ] IoT core
  - [ ] Greengrass
  - [ ] Lamda
  - [ ] SDK
  - [ ] Advantages
  - [ ] Disadvantages
  - [ ] STM32

- ### Azure
  - [ x ] Azure RTOS
  - [ x ] Supported boards 
  - [ ] IoT Hub
  - [ ] IoT Edge
  - [ ] Azure Functions
  - [ ] SDK
  - [ ] Windows for IoT
  - [ ] Advantages
  - [ ] Disadvantages
  - [ ] Example build
