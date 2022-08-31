# V-ZUG

## V-ZUG API
```
http://10.10.1.1/ai?command=getDeviceStatus
http://10.10.1.2/hh?command=getProgram
http://10.10.1.1/ai?command=getAPIVersion
http://10.10.1.2/hh?command=getAPIVersion
```
# API Version Abfragen

```
http://172.16.200.158/ai?command=getAPIVersion
{"value":"1.7.0"}
Version 1.1.0 ist die alte APIVersion
Version 1.7.0 ist die neue APIVersion mit Abfrage mit hh?command=getProgram
http://172.16.200.158/hh?command=getProgram
[{"id":2500,"name":"Stark trocken","status":"active","duration":{"set":12000,"act":1271},"allowedStatusChanges":{"options":["idle","paused"]}}]

http://172.16.200.158/hh?command=doTurnOff
http://172.16.200.105/hh?command=doTurnOff

http://172.16.200.105/hh?command=setDeviceName&value=' + encodeURIComponent(deviceName)
		#
http://172.16.200.158/hh?command=getZHMode
{"value":2}
http://172.16.200.105/ai?command=getModelDescription
Adora SL
http://172.16.200.105/ai?command=getLastPUSHNotifications
[{"date":"2021-06-01T02:33:55","message":"Programm Eco-Programm gestartet"} ,{"date":"2021-05-31T22:31:38","message":"Programm Automatik beendet - Energie: <0,1 kWh, Wasser: 0 ℓ"} ,{"date":"2021-05-31T21:59:34","message":"Programm Eco-Programm beendet - Energie: <0,1 kWh, Wasser: 0 ℓ"} ]
http://172.16.200.105/hh?command=setProgram&value=%7B%22id%22:50%7D    // URL decode {"id":50}
setProgram
id: 50 = Eco Modus
id: 51 = Auto
id: 52 = ALltag Kurz
id: 53 = Sprint
id: 54 = Intensiv
id: 55 = Silent
id: 56 = Patry
id: 57 = Glas
id: 58 = Fondue / Raclette
id: 59 = Hygiene
id: 61 = Vorspülen
http://172.16.200.105/hh?command=setProgram&value=%7B%22partialload%22:false,%22eco%22:%22none%22,%22steamfinish%22:false%7D
		#
http://172.16.200.105/hh?command=setProgram&value={"partialload":true,"steamfinish":true,"eco":"optiStart"}
eco: energySaving
eco: optiStart
eco: none
steamfinish: true / false
partialload: true / false
}
```

https://www.loxwiki.eu/display/LOXBERRY/V-ZUG-HOME
https://github.com/marcelzoller/loxberry-plugin-vzug
https://github.com/loleg/v-zug-recipe-parser
