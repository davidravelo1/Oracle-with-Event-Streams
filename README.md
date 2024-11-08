# Conexión de Oracle con Event Streams 
para conectar Oracle con Event Streams se necesita de los siguientes pre-requisitos: Configurar LogMiner en Oracle e instalar Debezium en Kafka. 
## 1. Configurar LogMiner en Oracle 
La configuración necesaria se puede encontrar en la documentación de debezium: [Documentación Debezium](https://debezium.io/documentation/reference/stable/connectors/oracle.html#setting-up-oracle).

Aquí hay una configuración de ejemplo: [logminer](logMiner.sql).

Además, ejecutar el siguiente comando ***ALTER TABLE SCHEMA.NOMBRE_TABLA ADD SUPPLEMENTAL LOG DATA (ALL) COLUMNS*** para las tablas que desea leer en event streams.

## 2. Instalación del plugin de Debezium en EventStreams


Se necesita del plugin de 
[KafkaConnect.yaml](logMiner.sql).
