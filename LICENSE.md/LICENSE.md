[
    {
        "id": "e9daff0f.f29e7",
        "type": "tab",
        "label": "Flow 2"
    },
    {
        "id": "a24eab46.19f858",
        "type": "inject",
        "z": "e9daff0f.f29e7",
        "name": "",
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "repeat": "5",
        "crontab": "",
        "once": true,
        "x": 171,
        "y": 80,
        "wires": [
            [
                "c5bf6411.aef178"
            ]
        ]
    },
    {
        "id": "c5bf6411.aef178",
        "type": "function",
        "z": "e9daff0f.f29e7",
        "name": "Payload",
        "func": "msg.headers={\n    deviceKey: \"WhZiygeFvQ4KVSFX\"\n    };\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 420,
        "y": 120,
        "wires": [
            [
                "eb57b3de.2af88",
                "342a8a31.475e16"
            ]
        ]
    },
    {
        "id": "eb57b3de.2af88",
        "type": "http request",
        "z": "e9daff0f.f29e7",
        "name": "",
        "method": "GET",
        "ret": "txt",
        "url": "http://api.mediatek.com/mcs/v2/devices/D00HmGbY/datachannels/Humidity/datapoints.csv",
        "tls": "",
        "x": 630,
        "y": 120,
        "wires": [
            [
                "6748a98a.3fc178",
                "ba92349d.316818"
            ]
        ]
    },
    {
        "id": "6748a98a.3fc178",
        "type": "http response",
        "z": "e9daff0f.f29e7",
        "name": "",
        "statusCode": "",
        "headers": {},
        "x": 870,
        "y": 60,
        "wires": []
    },
    {
        "id": "ba92349d.316818",
        "type": "debug",
        "z": "e9daff0f.f29e7",
        "name": "",
        "active": true,
        "console": "false",
        "complete": "false",
        "x": 890,
        "y": 200,
        "wires": []
    },
    {
        "id": "342a8a31.475e16",
        "type": "http request",
        "z": "e9daff0f.f29e7",
        "name": "",
        "method": "GET",
        "ret": "txt",
        "url": "http://api.mediatek.com/mcs/v2/devices/D00HmGbY/datachannels/Temperature/datapoints.csv",
        "tls": "",
        "x": 630,
        "y": 200,
        "wires": [
            [
                "6748a98a.3fc178",
                "ba92349d.316818"
            ]
        ]
    }
]
