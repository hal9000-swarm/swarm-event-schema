# Swarm Event Schema

This specifies the JSON schema (https://json-schema.org/) for generated events. Messages can be validated against the schema e.g. on https://www.jsonschemavalidator.net/.

For implementation Details see see https://github.com/hal9000-swarm/curiosity_2.0#supported-events

## Supported Events / Examples

### Traffic Monitoring

Sample message
```json
{ 
  {
   "version":"1.0",
   "node":{
      "id":"b8ade223-e847-4741-a405-7f62c0403aa2",
      "name":"test"
   },
   "trafficEvent":{
      "classification":"car",
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
      "movementPath":[
         {
            "timestamp":"2019-12-29T10:31:14.373202Z",
            "h":554.192138671875,
            "w":766.527587890625,
            "x":0.0,
            "y":525.807861328125
         },
         
         ...

         {
            "timestamp":"2019-12-29T10:31:15.173212Z",
            "h":757.237060546875,
            "w":1013.7042236328125,
            "x":137.61514282226563,
            "y":161.38143920898438
         }
      ]
   }
}
}
```

### Crossing Line

Sample message
```json
{ 
   "crossingLineEvent":{ 
      "class":"person",
      "direction":"in",
      "lineId":"test_id",
      "lineName":"office",
      "timestamp":"2019-12-29T10:31:14.373202Z"
   },
   "node":{ 
      "id":"test",
      "name":"test"
   },
   "version":"1.3"
}
```

### Heatmap

Sample message
```json
{ 
   "heatmapEvent":{ 
      "class":"car",
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
      "id":"test",
      "name":"test"
   },
   "version":"1.3"
}
```

### Region of Interest

Sample message
```json
{
  "node": {
    "id": "test",
    "name": "test"
  },
  "regionOfInterestEvent": {
    "objects": [
      {
        "class": "person"
      }
    ],
    "roiId": "69031920-6239-471e-a3d7-f241b7753fd0",
    "roiName": "R1",
    "state": "occupied",
    "timestamp": "2020-01-02T14:59:27.85136Z",
    "triggerType": "time"
  },
  "version": "1.3"
}
```
