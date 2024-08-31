The MQTT+ project is an advanced messaging system built on top of the standard MQTT protocol, designed to handle message filtering, prioritization, and efficient data processing. This project includes components for a broker, publishers, and subscribers, as well as a database for persisting and managing messages. It aims to simulate and analyze network traffic, including attack scenarios, for a Cyber-Physical System (CPS) - Internet of Things (IoT) surveillance platform.

Components
Broker (broker_traffic.py)

Receives and processes messages from publishers.
Filters and prioritizes messages.
Logs messages to a CSV file for further analysis.
Publisher (publisher.py)

Sends messages to the broker.
Simulates normal and attack traffic.
Subscriber (subscriber.py)

Receives messages from the broker.
Prints messages in order of priority.
Attack Publisher (attack_publisher.py)

Simulates DDoS attacks by sending high-frequency and large payload messages to the broker.
Transaction Handling (transaction.py)

Handles SQLite database operations, including table creation, data insertion, and retrieval.
Requirements
Python 3.x
Required Python packages:
sqlite3
socket
csv
random
time
Setup
Install Python Packages

Ensure you have Python installed and install required packages using pip:

sh
Copy code
pip install sqlite3
Database Setup

The SQLite database file mqtt+.db is used to persist messages. Ensure transaction.py is run to create necessary tables in the database.

Running the Broker

Start the broker to listen for incoming messages:

sh
Copy code
python broker_traffic.py
Running the Publisher

To simulate normal traffic:

sh
Copy code
python publisher.py
To simulate attack traffic:

sh
Copy code
python attack_publisher.py
Running the Subscriber

To subscribe to a topic and receive messages:

sh
Copy code
python subscriber.py
Usage
Publisher

Enter the number of motes when prompted.
Messages will be published to the specified topic.
Attack Publisher

Simulates high-frequency attack traffic to test the broker's handling of DDoS scenarios.
Subscriber

Enter the topic you wish to subscribe to.
Messages will be printed in order of priority.
Logging
Broker Logs: Messages are logged into broker_traffic_log.csv for analysis.
Transaction Logs: Messages are persisted in mqtt+.db.
