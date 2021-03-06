MQTT Demo
================

## Requirements

 * Java 1.7 and later
 * Maven 3.3.9 and later
 * Docker 1.12.5 and later
 * NodeJs 6 and later
 * Web Browser that supports websocket

## Run Broker

```bash
    $ docker run --rm -ti -p 1883:1883 -p 9001:8080 -e "DOCKER_VERNEMQ_ALLOW_ANONYMOUS=on" erlio/docker-vernemq
```

## Run Fake Sensor Java

```bash
	$ cd fake-sensor-java   
	$ mvn compile
	$ mvn exec:java
```

## Run Fake Sensor C

```bash
	$ cd fake-sensor-c   
	$ docker build -t fake-sensor-c .
	$ docker run --rm -it --net=host fake-sensor-c ./fake-sensor-c
```

## Run Fake Sensor NodeJS

```bash
	$ cd fake-sensor-nodejs
  $ npm install
	$ npm start -- <username> <password>
```

## Run Logger Subscriber Java

```bash
	$ cd logger-subscriber-java   
	$ mvn compile
	$ mvn exec:java
```

## Run Temperature Web Monitor

Open `web-gui-websocket/index.html` within a web browser that supports websockets (eg Google Chrome).

## References and Kudos

 * http://www.hivemq.com/blog/how-to-get-started-with-mqtt
 * https://eclipse.org/paho/clients/c/
 * https://www.eclipse.org/paho/files/mqttdoc/Cclient/_m_q_t_t_client_8h_source.html
 * http://jpmens.net/2014/07/03/the-mosquitto-mqtt-broker-gets-websockets-support/
