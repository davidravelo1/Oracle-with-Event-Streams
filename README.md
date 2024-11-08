# Conexión de Oracle con Event Streams 
para conectar Oracle con Event Streams se necesita de los siguientes pre-requisitos: Configurar LogMiner en Oracle e instalar Debezium en Kafka. 
## 1. Configurar LogMiner en Oracle 
La configuración necesaria se puede encontrar en la documentación de debezium: [Documentación Debezium](https://debezium.io/documentation/reference/stable/connectors/oracle.html#setting-up-oracle).

Aquí hay una configuración de ejemplo: [logminer](logMiner.sql).

Además, ejecutar el siguiente comando ***ALTER TABLE SCHEMA.NOMBRE_TABLA ADD SUPPLEMENTAL LOG DATA (ALL) COLUMNS*** para las tablas que desea leer en event streams.

## 2. Instalación del plugin de Debezium en EventStreams
Genere las credenciales necesiarias para crear una instancia de kafka Connect.
<img width="836" alt="Captura de pantalla 2024-11-07 a las 11 00 55 a  m" src="https://github.com/user-attachments/assets/b7c79674-b4ef-4d4f-a9b8-70b7f9ef59fc">
Se necesita del plugin de debezium encontrado en repositorio de maven [Debezium](https://repo1.maven.org/maven2/io/debezium/debezium-connector-oracle/) y en algunos casos un JDBC en el Yaml de configuración. [Instalar conectores](https://ibm.github.io/event-automation/es/connecting/setting-up-connectors/). 
Una configuracion de ejemplo se puede en el archivo kafkaConnect.yaml
[KafkaConnect.yaml](KafkaConnect.yaml).

## 3. Configurar conector de Debezium         
Todas las configuraciones posibles se pueden encontrar en la documentación de debezium [Documentación Debezium](https://debezium.io/documentation/reference/stable/connectors/oracle.html#setting-up-oracle).

Asegurarse de que es poible conectarse a Oracle e incluir la configuración table.include.list para filtrar las tablas de las que quiere ver eventos.

## 4. Oracle conectado a event streams. 
Se creara un topic por cada tabla que lea el event streams. 
![image](https://github.com/user-attachments/assets/3f4d00bd-f4ef-4c1d-a535-0d1fb365e603)
