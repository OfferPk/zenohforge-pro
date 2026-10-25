# ZenohForge Pro User Guide & Developer Manual

## 1\. Quickstart Guide

1. Launch the interactive studio by opening `index.html` in any modern web browser.  
2. In the "Pub/Sub & Query Dispatch" panel, specify a target Key Expression (e.g., `robot/0/sensor/lidar`).  
3. Select wire priority (Real-Time, Data High, Data Normal) and payload encoding.  
4. Click **Publish (PUT)** to generate the serialized binary frame and examine the hex dump in the console.  
5. Click **Query (GET)** to simulate a distributed Queryable query across the Zenoh network.  
6. Click **Run Normative Audit** to evaluate all 10 normative compliance clauses against the Eclipse Zenoh specification.

## 2\. Headless Python CLI Usage

Run automated tests and generate compliance reports directly from CI/CD pipelines:

python3 zenoh-cli.py \--audit \--key "robot/\*\*/telemetry" \--payload '{"status":"nominal"}'