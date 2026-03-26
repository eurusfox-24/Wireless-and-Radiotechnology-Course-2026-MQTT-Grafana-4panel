# Wireless-and-Radiotechnology-Course-2026-MQTT-Grafana-4panel

Here is the raw Markdown code for your **README.md** file. You can copy this entire block and paste it into a file named `README.md` in your GitHub repository.

````markdown
# IoT Real-Time Monitoring: Socket to MQTT Pipeline

## Project Overview
This project demonstrates a complete IoT data pipeline. It simulates the flow of sensor data from a hardware source to a cloud-based monitoring dashboard using **Python Sockets**, **MQTT**, and **Grafana**.

### System Architecture & Data Flow
1. **Sensor (Laptop 1):** Runs `socket_sensor.py`. It generates temperature data and transmits it via a TCP Socket.
2. **Edge Device (Laptop 2):** Runs `edge_device.py`. It receives the socket data and publishes it to a global MQTT broker.
3. **Monitoring (Grafana):** Subscribes to the MQTT topic from the broker and displays the live values.

---

## Configuration Details
* **Socket Connection:** `127.0.0.1:5000`
* **MQTT Broker:** `broker.emqx.io`
* **MQTT Port:** `1883`
* **MQTT Topic:** `savonia/iot/temperature`
* **Grafana URI:** `tcp://broker.emqx.io:1883`

---

## How to Run the System
Run the components in this specific order to ensure the connection is established:

1. **Start the Edge Device:**
   ```bash
   python edge_device.py
````

2.  **Start the Sensor:**
    ```bash
    python socket_sensor.py
    ```
3.  **Launch Grafana:**
    Open `http://localhost:3000` in your browser and view the MQTT dashboard.

-----

## Grafana Dashboard

The dashboard uses an **MQTT Data Source** to visualize the live stream. A **Gauge Panel** is used to show the current temperature, set to a range of 0°C to 50°C.

**Note on Limitation:** This setup utilizes the Grafana MQTT data source for **live monitoring only**. Because there is no database (like InfluxDB or Loki) attached, data is not stored; the dashboard only shows values received while the browser is open.

### Dashboard Screenshot

-----

## Reflection Questions

**1. What is the role of Grafana in this system?**
Grafana acts as the visualization layer. It subscribes to the MQTT broker to retrieve raw data and converts it into human-readable formats like gauges for real-time monitoring.

**2. Why is MQTT useful for monitoring applications?**
MQTT is a lightweight, "publish-subscribe" protocol. It is ideal for monitoring because it uses minimal bandwidth and allows multiple subscribers to receive data from a single sensor simultaneously.

**3. What is the difference between live monitoring and historical storage?**

  * **Live Monitoring:** Shows data as it happens in real time. Data is lost if the connection or dashboard is closed.
  * **Historical Storage:** Involves saving data to a database, allowing users to analyze trends and look at data from the past.

-----

## Project Files

  * `socket_sensor.py`: Data source script using sockets.
  * `edge_device.py`: Bridge script converting Socket data to MQTT.
  * `README.md`: System documentation.

<!-- end list -->

```

**Would you like me to show you how to name your screenshot file so it automatically appears in this README?**
```
