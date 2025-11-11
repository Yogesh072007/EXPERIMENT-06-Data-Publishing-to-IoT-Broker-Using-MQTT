# EXPERIMENT-06-Data-Publishing-to-IoT-Broker-Using-MQTT3
 ## NAME:YOGESH KUMAR.A
 ## REGISTER NUMBER:212224220125
 ## DEPARTMENT:B.tech IT
 ## YEAR:2nd
 ## Aim:
To publish data to an IoT broker using the MQTT protocol.

 ## Apparatus Required:
MQTT Broker: An MQTT broker, such as HiveMQ or Mosquitto, for handling communication.
Python Environment: To run the script for publishing data to the broker.
Internet Connection: For connecting to the IoT broker.
Theory:
MQTT (Message Queuing Telemetry Transport) is a lightweight messaging protocol used in IoT applications. It allows devices to publish data to a broker, where other devices or applications can subscribe to receive updates. This experiment demonstrates how to use MQTT to send messages to an IoT broker using the paho-mqtt library in Python.

 ## Procedure:
Setup MQTT Broker:

You can use a public broker like broker.hivemq.com or set up your own broker using software like Mosquitto.
Choose a topic for the message, e.g., test/topic.
Install MQTT Client Library:

Install the paho-mqtt Python library to facilitate communication with the MQTT broker.
bash
Copy code
!pip install paho-mqtt
Write the Python Script to Publish Data:

Create a Python script to connect to the broker and publish a message to a specific topic.
Code Implementation: Here’s the Python code to publish data to the IoT broker using MQTT:

python
Copy code
import paho.mqtt.client as mqtt

# Broker details
broker_address = "broker.hivemq.com"  # Broker address
broker_port = 1883  # Broker port
topic = "test/topic"  # Topic to publish to

# Initialize the MQTT Client
client = mqtt.Client()

# Connect to the broker
client.connect(broker_address, broker_port, keepalive=60)

# Publish a message to the topic
message = "Hello, MQTT!"  # Message to be published
client.publish(topic, message)

# Disconnect from the broker
client.disconnect()

# Print confirmation message
print(f"Message '{message}' published to topic '{topic}'")
Run the Script:

Execute the script. It will connect to the MQTT broker, publish the message to the specified topic, and then disconnect.
Verify Message Publishing:

You can verify the message by subscribing to the same topic using an MQTT client, such as MQTT.fx or any other MQTT subscriber tool.
 ## Outputs:
Message Confirmation: The script will print a message confirming that the data has been successfully published to the topic.

Example output:

bash
Copy code
Message 'Hello, MQTT!' published to topic 'test/topic'
Broker Message: The message "Hello, MQTT!" will be published to the topic test/topic.

## Python Code 
```
import paho.mqtt.client as mqtt
broker="bf57e952135f4737a53af447f5991f92.s1.eu.hivemq.cloud"
port = 8883
topic = "iot/sensor/data"
username = "hivemq.webclient.1762401378020"
password = "hH457DAvJdu<.R1q#,kB"

client = mqtt.Client()
client.username_pw_set(username, password)
client.tls_set() 

client.connect(broker, port)
client.publish(topic, "Hello SEC")
client.loop(2)
client.disconnect()

```




 ## Simulation Screenshots:

 <img width="1918" height="1020" alt="Screenshot 2025-11-06 093347" src="https://github.com/user-attachments/assets/68d2b469-54b3-4e21-b003-51af03f29db1" />

 ## Results:
The data was successfully published to the MQTT broker. The experiment demonstrated how to use the MQTT protocol to transfer data to an IoT broker, enabling remote communication between devices or applications. The message was confirmed to be received by the topic, and this communication can be extended to more complex IoT systems.
