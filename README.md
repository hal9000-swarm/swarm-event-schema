# Swarm Event Schema

This specifies the JSON schema (https://json-schema.org/) for generated events. Messages can be validated against the schema e.g. on https://www.jsonschemavalidator.net/.

The expert event schema is defined in swarm-event-schema.json, while solution specific schemas are defined in the corresponding subfolders.

## Supported Events / Examples



### Counting Line / Crossing Line

Sample message
```json
{ 
   "crossingLineEvent":{ 
      "class":"person",
      "direction":"in",
      "directionName": "optional custom direction name",
      "speedestimate": "83.26",
      "lineId":"test_id",
      "lineName":"office",
      "timestamp":"2019-12-29T10:31:14.373202Z",
      "trackId": 23
   },
   "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname"
   },
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
}
```

### Counting Line / Crossing Line with ANPR

Sample message
```json
{ 
   "crossingLineEvent":{ 
      "class":"car",
      "subClass":"van",
      "direction":"in",
      "lineId":"test_id",
      "lineName":"garage",
      "timestamp":"2019-12-29T10:31:14.373202Z",
      "trackId": 42,
      "numberPlate": "IXXX42",
      "numberPlateOrigin": "AT"
   },
   "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname"
   },
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
}
```

### Counting Line / Including Journey Time Observation

Sample message
```json
{ 
   "crossingLineEvent":{ 
      "class":"person",
      "direction":"in",
      "speedestimate": "83.26",
      "lineId":"test_id",
      "lineName":"office",
      "timestamp":"2019-12-29T10:31:14.373202Z",
      "trackId": 23,   
      "journeyTimePrimaryTag": {
          "hash": "0f3f0125e621b6f29313eb8e6adddec192afa1dee9626fb8062725caf83f6867",
          "saltId": "0c7355bd-bb7b-41c2-ae4c-a4f5ab89d1fa",
          "validFrom": "2019-12-29T01:31:14.373202Z",
          "validUntil":"2019-12-29T12:31:14.373202Z"
      },
      "journeyTimeSecondaryTag": {
         "hash": "d8cee0c8f219e0e46480c374aa0a8cabe149f2f21e2c1e60ceea137s186e8c34",
          "saltId": "0854a686-401a-42f2-b715-655180888c85",
          "validFrom": "2019-12-29T09:31:14.373202Z",
          "validUntil":"2019-12-29T16:31:14.373202Z"
      }
   },
   "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname",
      "geoLocation": {
        "coordinates": [47.2692, 11.4041]
      }
   },
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
}
```

### Heatmap

Sample message
```json
{ 
   "heatmapEvent":{ 
      "class":"car",
      "trackId": 23,
      "path":[ 
         { 
            "h":554.192138671875,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":766.527587890625,
            "x":0.0,
            "y":525.807861328125
         },
         { 
            "h":757.237060546875,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":1013.7042236328125,
            "x":137.61514282226563,
            "y":161.38143920898438
         },
         { 
            "h":757.2371215820313,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":789.4736938476563,
            "x":249.7304229736328,
            "y":108.07360076904297
         },
         { 
            "h":757.2371215820313,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":1013.704345703125,
            "x":149.989990234375,
            "y":157.8472137451172
         },
         { 
            "h":757.237060546875,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":789.4736938476563,
            "x":184.40171813964844,
            "y":161.38143920898438
         },
         { 
            "h":757.2371215820313,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":1013.7042236328125,
            "x":131.88348388671875,
            "y":157.8472137451172
         },
         { 
            "h":757.2371215820313,
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "w":1013.7042236328125,
            "x":131.88348388671875,
            "y":157.8472137451172
         }
      ]
   },
   "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname"
   },
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
}
```

### Region of Interest

Sample message
```json
{
   "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname"
   },
  "regionOfInterestEvent": {
    "objects": [
      {
        "class": "person", "trackId": 23, "dwellTime": 19
      }
    ],
    "roiId": "69031920-6239-471e-a3d7-f241b7753fd0",
    "roiName": "R1",
    "state": "occupied",
    "timestamp": "2020-01-02T14:59:27.85136Z",
    "triggerType": "time",
    "capacity": 20
  },
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
}
```

### Parking specific Region of Interest


```json
{
    "eventSchema": "https://swarm-analytics.com/schema/event/",
    "node":
    {
        "id": "nodeId",
        "name": "nodeName"
    },
    "parkingEvent":
    {
        "parkingSummary":
        [
            {
                "capacity": 20,
                "roiId": "9e70ac77-872c-40c0-a65f-1044061aaf60",
                "roiName": "Parking1",
                "vehicles": 2,
                "numberPlates":
                [
                    {
                        "numberplate": "ISWARM1",
                        "numberplateOrigin": "AT"
                    },
                    {
                        "numberplate": "ISWARM2",
                        "numberplateOrigin": "AT"
                    }
                ]
            },
            {
                "capacity": 15,
                "roiId": "8e70ac77-872c-40c0-a65f-1044061aaf60",
                "roiName": "Parking2",
                "vehicles": 8
            }
        ],
        "timestamp": "2022-02-18T10:22:50.373408Z",
        "totalCapacity": 35,
        "totalVehicles": 12
    },
    "stream":
    {
        "id": "streamId",
        "name": "streamname"
    },
    "version": "4.0"
}
```

### Origin Destination

Sample message
```json
{
   "version":"4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
    "node":{ 
      "id":"99031920-6239-471e-a3d7-f241b7753fd0",
      "name":"test"
   },
   "stream":{ 
      "id":"79031920-6239-471e-a3d7-f241b7753fd0",
      "name":"streamname"
   },
   "originDestinationEvent":{
      "classification":"truck",
      "subClass": "articulated-truck",
      "entry":{
         "zone":{
            "zoneId":"56317209-9B83-43A6-A63E-58C9191A7869",
            "name":"entryZoneName"
         },
         "timestamp":"2019-12-29T10:31:14.373202Z"
      },
      "exit":{
         "zone":{
            "zoneId":"c28ed4e8-bf1b-4c2e-9938-aeb28687f7aa",
            "name":"exitZoneName"
         },
         "timestamp":"2019-12-29T10:31:20.373202Z"
      },
      "trackId": 23,
      "movementPath":[
         {
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "h":554.192138671875,
            "w":766.527587890625,
            "x":0.0,
            "y":525.807861328125
         },
         {
            "timestamp":"2019-12-29T10:31:15.173212Z",
            "h":757.237060546875,
            "w":1013.7042236328125,
            "x":137.61514282226563,
            "y":161.38143920898438
         },
         {
            "timestamp":"2019-12-29T10:31:16.229202Z",
            "h":757.2371215820313,
            "w":789.4736938476563,
            "x":249.7304229736328,
            "y":108.07360076904297
         },
         {
            "timestamp":"2019-12-29T10:31:17.343202Z",
            "h":757.2371215820313,
            "w":1013.704345703125,
            "x":149.989990234375,
            "y":157.8472137451172
         },
         {
            "timestamp":"2019-12-29T10:31:18.373202Z",
            "h":757.237060546875,
            "w":789.4736938476563,
            "x":184.40171813964844,
            "y":161.38143920898438
         },
         {
            "timestamp":"2019-12-29T10:31:19.373202Z",
            "w":1013.7042236328125,
            "h":757.2371215820313,
            "x":131.88348388671875,
            "y":157.8472137451172
         },
         {
            "timestamp":"2019-12-29T10:31:20.373202Z",
            "h":757.2371215820313,
            "w":1013.7042236328125,
            "x":131.88348388671875,
            "y":157.8472137451172
         }
      ]
   }
}
```

### Virtual Door

Sample message
```json
{
   "version": "4.0",
   "eventSchema": "https://swarm-analytics.com/schema/event/",
   "node": {
      "id": "b8ade223-e847-4741-a405-7f62c0403aa2",
      "name": "test"
   },
   "stream":{ 
      "id":"streamid",
      "name":"streamname"
   },
    "virtualDoorEvent": {
         "object": {
            "class": "person"
         },
         "virtualDoorId": "69031920-6239-471e-a3d7-f241b7753fd0",
         "virtualDoorName": "door1",
         "timestamp": "2020-01-02T14:59:27.85136Z",
         "direction": "in",
         "trackId": 23
    }
}
```


### Rule Event

Sample message
```json
{
    "eventSchema": "https://swarm-analytics.com/schema/event/",
    "ruleEvents":
    [
        {
            "regionOfInterestEvent":
            {
                "capacity": 10,
                "objects":
                [
                    {
                        "class": "person",
                        "dwellTime": 25,
                        "trackId": 2
                    },
                    {
                        "class": "person",
                        "dwellTime": 10,
                        "trackId": 10
                    }
                ],
                "roiId": "96dfc3e0-0e82-4790-8104-cff33455dc2b",
                "roiName": "roi1",
                "state": "occupied",
                "timestamp": "2022-04-28T12:22:06.761660Z",
                "triggerType": "time"
            }
        },
        {
            "crossingLineEvent":
            {
                "class": "car",
                "direction": "in",
                "lineId": "3a103372-8b85-4191-8fe9-d88cb978d55d",
                "lineName": "dangerline",
                "speedestimate": "120",
                "subClass": "van",
                "timestamp": "2022-04-28T12:22:06.761660Z",
                "trackId": 3
            }
        }
    ],
    "node":
    {
        "id": "96dfc3e0-0e82-4790-8104-cff33455dc2a",
        "name": "node1"
    },
    "ruleId": "2b854935-cf8b-45af-b0e2-eaec456195bc",
    "ruleName": "cars near people",
   "timestamp": "2022-04-28T12:22:06.761660Z",
    "stream":
    {
        "id": "96dfc3e0-0e82-4790-8104-cff33455dc2b",
        "name": "stream1"
    },
    "version": "4.0"
}
```

