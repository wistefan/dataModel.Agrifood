Entidad: AgriGreenhouse  
=======================  
[Licencia abierta](https://github.com/smart-data-models//dataModel.Agrifood/blob/master/AgriGreenhouse/LICENSE.md)  
Descripción global: **Esta entidad contiene una descripción armonizada de las condiciones registradas dentro de un invernadero genérico, un tipo de AgriParcel.**  

## Lista de propiedades  

- `alternateName`: Un nombre alternativo para este artículo  - `belongsTo`: La entidad a la que pertenece el Invernadero  - `co2`: La concentración interior de C02 medida nominalmente en mg/L  - `dailyLight`: Luz acumulada diaria medida en kW por metro cuadrado  - `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  - `dateCreated`: Sello de tiempo de creación de la entidad. Normalmente será asignado por la plataforma de almacenamiento.  - `dateModified`: Sello de tiempo de la última modificación de la entidad. Esta será normalmente asignada por la plataforma de almacenamiento.  - `description`: Una descripción de este artículo  - `drainFlow`: El caudal de drenaje observado en litros por segundo  - `hasAgriParcelChildren`: Registros relacionados con la subcategoría AgriParcel a la que se refiere esta entidad  - `hasAgriParcelParent`: Referencia a la entidad de AgriParcel a la que se refiere esta entidad  - `hasDevice`: Referencia a los dispositivos de IO asociados a este invernadero, es decir, sensores, controles.  - `hasWaterQualityObserved`: Referencia a uno o más registros de observación de la calidad del agua actuales para esta entidad  - `hasWeatherObserved`: Referencia al registro de observación meteorológica actual para esta entidad  - `id`: Identificador único de la entidad  - `leafTemperature`: La humedad relativa interior expresada como un número entre 0 y 1 que representa el rango de 0% a 100 (%).<br/><br/>0 ≤ relativeHumidity ≤ 1  - `name`: El nombre de este artículo.  - `ownedBy`: Propietario (persona u organización) del AgriGreenhouse  - `owner`: Una lista que contiene una secuencia de caracteres codificados JSON que hace referencia a los Ids únicos de los propietarios  - `relatedSource`: Lista de identificaciones que la entidad actual puede tener en aplicaciones externas  - `relativeHumidity`: La temperatura media del aire del invernadero nominalmente en grados centígrados.  - `seeAlso`: lista de uri que apunta a recursos adicionales sobre el tema  - `source`: Una secuencia de caracteres que da como URL la fuente original de los datos de la entidad. Se recomienda que sea el nombre de dominio completamente calificado del proveedor de la fuente, o la URL del objeto fuente.  - `type`: Tipo de entidad NGSI. Tiene que ser AgriGreenhouse    
Propiedades requeridas  
- `hasAgriParcelParent`  - `id`  - `type`    
Esta entidad se asocia principalmente con las aplicaciones verticales agrícolas y las aplicaciones conexas de IO.  
## Modelo de datos Descripción de las propiedades  
Ordenados alfabéticamente (haga clic para ver los detalles)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
AgriGreenhouse:    
  description: 'This entity contains a harmonised description of the conditions recorded within a generic greenhouse, a type of AgriParcel.'    
  properties:    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    belongsTo:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Entity the Greenhouse belongs to'    
      type: Relationship    
    co2:    
      description: 'The measured interior C02 concentration nominally in mg/L'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: mg/L    
    dailyLight:    
      description: 'Daily Accumulated light measured in kW per square metre'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: kw/m2    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    description:    
      description: 'A description of this item'    
      type: Property    
    drainFlow:    
      description: 'The observed drain flow rate in litres per second'    
      type: Property    
      values:    
        maxValue:    
          minimum: 0    
          type: number    
        minValue:    
          minimum: 0    
          type: number    
        unitText:    
          type: string    
        value:    
          minimum: 0    
          type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        units: L/s    
    hasAgriParcelChildren:    
      description: 'Related sub AgriParcel records to which this entity relates'    
      items:    
        - anyOf: &anyof    
            - description: 'Property. Identifier format of any NGSI entity'    
              maxLength: 256    
              minLength: 1    
              pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
              type: string    
            - description: 'Property. Identifier format of any NGSI entity'    
              format: uri    
              type: string    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
    hasAgriParcelParent:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the AgriParcel entity to which this entity relates'    
      type: Relationship    
    hasDevice:    
      description: 'Reference to the IoT devices associated with this greenhouse i.e. sensors, controls.'    
      items:    
        - anyOf: *anyof    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
      x-ngsi:    
        model: http://schema.org/URL    
    hasWaterQualityObserved:    
      description: 'Reference to one or more water quality observation records current for this entity'    
      items:    
        - anyOf: *anyof    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
    hasWeatherObserved:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the weather observation record current for this entity'    
      type: Relationship    
    id:    
      anyOf: *anyof    
      description: 'Unique identifier of the entity'    
      type: Property    
    leafTemperature:    
      description: 'The inside relative humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 ≤ relativeHumidity ≤ 1'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    name:    
      description: 'The name of this item.'    
      type: Property    
    ownedBy:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Owner (Person or Organization) of the AgriGreenhouse'    
      type: Relationship    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    relatedSource:    
      description: 'List of IDs the current entity may have in external applications'    
      items:    
        - type: object    
          values:    
            application:    
              anyOf: *anyof    
              description: 'Property. Unique identifier of the entity'    
            applicationEntityId:    
              type: string    
      type: Property    
    relativeHumidity:    
      description: 'The average greenhouse air temperature nominally in degrees centigrade.'    
      maximum: 1.0    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'Degrees centigrade'    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity Type. It has to be AgriGreenhouse'    
      enum:    
        - AgriGreenhouse    
      type: Property    
  required:    
    - id    
    - type    
    - hasAgriParcelParent    
  type: object    
```  
</details>    
## Ejemplo de cargas útiles  
#### Ejemplo de valores clave de AgriGreenhouse NGSI V2  
Aquí hay un ejemplo de un AgriGreenhouse en formato JSON como valores clave. Es compatible con NGSI V2 cuando se utiliza "opciones=valores-clave" y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
  "type": "AgriGreenhouse",  
  "dateCreated": "2017-01-01T01:20:00Z",  
  "dateModified": "2017-05-04T12:30:00Z",  
  "ownedBy": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c",  
  "relatedSource": [  
    {  
      "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
      "applicationEntityId": "app:greenhouse1"  
    }  
  ],  
  "seeAlso": [  
    "https://example.org/concept/agrigreenhouse",  
    "https://datamodel.org/example/agrigreenhouse"  
  ],  
  "belongsTo": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765",  
  "hasAgriParcelParent": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b",  
  "hasAgriParcelChildren": [  
    "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
    "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
  ],  
  "hasWeatherObserved": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d",  
  "hasWaterQualityObserved": [  
    "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
    "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
  ],  
  "relativeHumidity": 0.4,  
  "leafTemperature": 22,  
  "co2": 28,  
  "dailyLight": 24,  
  "drainFlow": {  
    "value": 33,  
    "maxValue": 50,  
    "minValue": 25,  
    "unitText": "Litre per second"  
  },  
  "hasDevice": [  
    "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
    "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
    "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
    "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
  ]  
}  
```  
#### AgriGreenhouse NGSI V2 normalizado Ejemplo  
Aquí hay un ejemplo de un AgriGreenhouse en formato JSON como normalizado. Es compatible con NGSI V2 cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
  "type": "AgriGreenhouse",  
  "dateCreated": {  
    "type": "DateTime",  
    "value": "2017-01-01T01:20:00Z"  
  },  
  "dateModified": {  
    "type": "DateTime",  
    "value": "2017-05-04T12:30:00Z"  
  },  
  "ownedBy": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c"  
  },  
  "relatedSource": {  
    "value": [  
      {  
        "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
        "applicationEntityId": "app:greenhouse1"  
      }  
    ]  
  },  
  "seeAlso": {  
    "value": [  
      "https://example.org/concept/agrigreenhouse",  
      "https://datamodel.org/example/agrigreenhouse"  
    ]  
  },  
  "belongsTo": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765"  
  },  
  "hasAgriParcelParent": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b"  
  },  
  "hasAgriParcelChildren": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
      "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
    ]  
  },  
  "hasWeatherObserved": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d"  
  },  
  "hasWaterQualityObserved": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
      "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
    ]  
  },  
  "relativeHumidity": {  
    "type": "Property",  
    "value": 0.4  
  },  
  "leafTemperature": {  
    "type": "Property",  
    "value": 22  
  },  
  "co2": {  
    "type": "Property",  
    "value": 28  
  },  
  "dailyLight": {  
    "type": "Property",  
    "value": 24  
  },  
  "drainFlow": {  
    "type": "Property",  
    "value": {  
      "value": 33,  
      "maxValue": 50,  
      "minValue": 25,  
      "unitText": "Litre per second"  
    }  
  },  
  "hasDevice": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
      "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
      "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
      "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
    ]  
  }  
}  
```  
#### Ejemplo de valores clave de AgriGreenhouse NGSI-LD  
Aquí hay un ejemplo de un AgriInvernadero en formato JSON-LD como valores clave. Esto es compatible con NGSI-LD cuando se utiliza "opciones=valores-clave" y devuelve los datos de contexto de una entidad individual.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "belongsTo": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765",  
 "co2": 28,  
 "createdAt": "2017-01-01T01:20:00Z",  
 "dailyLight": 24,  
 "drainFlow": {"maxValue": 50,  
               "minValue": 25,  
               "unitText": "Litre per second",  
               "value": 33},  
 "hasAgriParcelChildren": ["urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
                           "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"],  
 "hasAgriParcelParent": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b",  
 "hasDevice": ["urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
               "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
               "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
               "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"],  
 "hasWaterQualityObserved": ["urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
                             "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"],  
 "hasWeatherObserved": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d",  
 "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
 "leafTemperature": 22,  
 "modifiedAt": "2017-05-04T12:30:00Z",  
 "ownedBy": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c",  
 "relatedSource": [{"application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
                    "applicationEntityId": "app:greenhouse1"}],  
 "relativeHumidity": 0.4,  
 "seeAlso": ["https://example.org/concept/agrigreenhouse",  
             "https://datamodel.org/example/agrigreenhouse"],  
 "type": "AgriGreenhouse"}  
```  
#### AgriGreenhouse NGSI-LD normalizado Ejemplo  
Aquí hay un ejemplo de un AgriGreenhouse en formato JSON-LD normalizado. Esto es compatible con NGSI-LD cuando no se usan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context",  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
    ],  
    "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
    "type": "AgriGreenhouse",  
    "createdAt": "2017-01-01T01:20:00Z",  
    "modifiedAt": "2017-05-04T12:30:00Z",  
    "ownedBy": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c"  
    },  
    "relatedSource": {  
        "type": "Property",  
        "value": [  
            {  
                "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
                "applicationEntityId": "app:greenhouse1"  
            }  
        ]  
    },  
    "seeAlso": {  
        "type": "Property",  
        "value": [  
            "https://example.org/concept/agrigreenhouse",  
            "https://datamodel.org/example/agrigreenhouse"  
        ]  
    },  
    "belongsTo": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765"  
    },  
    "hasAgriParcelParent": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b"  
    },  
    "hasAgriParcelChildren": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
            "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
        ]  
    },  
    "hasWeatherObserved": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d"  
    },  
    "hasWaterQualityObserved": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
            "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
        ]  
    },  
    "relativeHumidity": {  
        "type": "Property",  
        "value": 0.4,  
        "unitCode": "C62",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "leafTemperature": {  
        "type": "Property",  
        "value": 22,  
        "unitCode": "CEL",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "co2": {  
        "type": "Property",  
        "value": 28,  
        "unitCode": "M1",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "dailyLight": {  
        "type": "Property",  
        "value": 24,  
        "unitCode": "N78",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "drainFlow": {  
        "type": "Property",  
        "value": {  
            "value": 33,  
            "maxValue": 50,  
            "minValue": 25,  
            "unitText": "Litre per second"  
        },  
        "unitCode": "G51",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "hasDevice": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
            "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
            "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
            "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
        ]  
    }  
}  
```  
