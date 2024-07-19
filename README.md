# ESP32-Ethernet-connecting-to-aws-iot
This is the MQTTClient_SSL example ( available installing library WebServer_WT32_ETH01 ) modified for connecting to aws iot core.
It is similar to the esp32_aws example ( which connects to the net via wifi )

Prerequisites:
- arduino ide
- install library WebServer_WT32_ETH01
- ESP32 board WT32_ETH01

In file secrets.h:
- insert your thing/device certificate ( AWS_CERT_CRT ) and private key ( AWS_CERT_PRIVATE ), you generated on the 'aws iot core console' ( the Amazon root certificate should be ok )
- insert your AWS_IOT_ENDPOINT ( see the settings page of the 'aws iot core console'  )

In file MQTTClient_aws_iot:
- insert your lan parameters ( myIP, myGW, mySN, myDNS )
- insert ID ( identifier ), TOPIC ( to publish to ) and subTopic ( to subscribe to )

To program WT32_ETH01 board ( which does not include an usb connection ) you need an usb-to-serial-ttl converter:
- connect the usb-ttl rx to the wt32_ETH01 tx0 ( pin 26 )
- connect the usb-ttl tx to the wt32_ETH01 rx0 ( pin 25 )
- connect the usb-ttl gnd to the wt32_ETH01 gnd
- connect the usb-ttl +5V to the wt32_ETH01 +5V ( do not connect this if you power the board differently )
- on wt32_ETH01 board connect a button between en ( pin 1 ) and gnd ( pin 2 )
- on wt32_ETH01 board connect a button between io0 ( pin 24 ) and gnd ( pin 23 )
When esptool starts, keep pressed the button on io0, press breafly the button on en and then release the button on io0, programming should begin.

![wt32-eth01_a](https://github.com/user-attachments/assets/fb0572c2-574e-49fb-8de9-6801417946cb)
![wt32-eth01_b](https://github.com/user-attachments/assets/480acd31-d88e-41e9-a835-ca398ab7b56a)


More information on the wt32_eth01 board:
- <a href="https://github.com/egnor/wt32-eth01?tab=readme-ov-file#unofficial-guide-to-the-wt32-eth01">Unofficial guide to the WT32-ETH01</a>
- <a href="https://aws.amazon.com/it/blogs/compute/building-an-aws-iot-core-device-using-aws-serverless-and-an-esp32/">esp32_aws example</a>
