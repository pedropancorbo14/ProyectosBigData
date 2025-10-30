# Practica 2

##  2. Creación de las 3 entidades:

Llamada a la api de orion: http://localhost:1026/v2/entities

Los Json:

{
    "id": "Sensor_TempHum_1",
    "type": "Temperatura_y_humedad",
    "location": { "type": "String", "value": "Puerta" },
    "temperature": { "type": "Float", "value": 20 },
    "humidity": { "type": "Float", "value": 80 },
    "created_at": { "type": "Datetime", "value": "2024-04-02 20:22:44" },
    "updated_at": { "type": "Datetime", "value": "2024-04-02 20:22:44" }
}
{
    "id": "Sensor_TempHum_2",
    "type": "Temperatura_y_humedad",
    "location": { "type": "String", "value": "Sala principal" },
    "temperature": { "type": "Float", "value": 22.5 },
    "humidity": { "type": "Float", "value": 65 },
    "created_at": { "type": "Datetime", "value": "2024-04-02 20:25:10" },
    "updated_at": { "type": "Datetime", "value": "2024-04-02 20:25:10" }
}
{
    "id": "Sensor_TempHum_3",
    "type": "Temperatura_y_humedad",
    "location": { "type": "String", "value": "Almacen" },
    "temperature": { "type": "Float", "value": 18.7 },
    "humidity": { "type": "Float", "value": 72 },
    "created_at": { "type": "Datetime", "value": "2024-04-02 20:30:27" },
    "updated_at": { "type": "Datetime", "value": "2024-04-02 20:30:27" }
}

## 3. Creación de una suscripción:

Llamada a la api de orion: http://localhost:1026/v2/subscriptions

Json:

{
    "description": "Suscripcion QuantumLeap Temperatura y Humedad",
    "subject": {
        "entities": [
            {
                "idPattern": ".*",
                "type": "Temperatura_y_humedad"
            }
        ],
        "condition": {
            "attrs": [
                "temperature",
                "humidity"
            ]
        }
    },
    "notification": {
        "attrs": [
            "id",
            "type",
            "location",
            "temperature",
            "humidity",
            "created_at",
            "updated_at"
        ],
        "http": {
            "url": "http://quantumleap:8668/v2/notify"
        },
        "metadata": [
            "dateCreated",
            "dateModified"
        ]
    }
}

## 4. Carga de datos:

Archivo consultas.py

## 5. Consulta Mongodb

./Images/Consulta1.png
./Images/Consulta2.png
./Images/Consulta3.png