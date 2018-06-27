```
{
    "id": "IxexyLDIIk", //string; required; Unique ID of the bid request, provided by the exchange.
    "imp": [ //object array; required; Array of Imp objects representing the impressionsoffered. At least 1 Impobjectis required.
        {
            "id": "1", //string; required; A unique identifier for this impression within the context of the bid request (typically, starts with 1 and increments.
            "banner": { //A Banner object; required if this impression is offered as a banner ad opportunity.
                "w": 728, //integer; recommended; Width of the impression in pixels.
If neither wmin nor wmax are specified, this value is an exact width requirement. Otherwise it is a preferred width.
                "h": 90, //integer; recommended; Height of the impression in pixels.
If neither hmin nor hmax are specified, this value is an exact height requirement. Otherwise it is a preferred height.
                "pos": 1, //integer; Ad position on screen
                "btype": [
                    4
                ],
                "battr": [
                    14
                ],
                "api": [
                    3
                ]
            },
            "instl": 0,
            "tagid": "agltb3B1Yi1pbmNyDQsSBFNpdGUY7fD0FAw",
            "bidfloor": 0.5
        }
    ],
    "app": {
        "id": "agltb3B1Yi1pbmNyDAsSA0FwcBiJkfIUDA",
        "name": "Yahoo Weather",
        "cat": [
            "weather",
            "IAB15",
            "IAB15-10"
        ],
        "ver": "1.0.2",
        "bundle": "628677149",
        "publisher": {
            "id": "agltb3B1Yi1pbmNyDAsSA0FwcBiJkfTUCV",
            "name": "yahoo",
            "domain": "www.yahoo.com"
        },
        "storeurl": "https://itunes.apple.com/id628677149"
    },
    "device": {
        "dnt": 0,
        "ua": "Mozilla/5.0 (iPhone; CPU iPhone OS 6_1 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3",
        "ip": "123.145.167.189",
        "geo": {
            "country": "USA",
            "lat": 35.012345,
            "lon": -115.12345,
            "city": "Los Angeles",
            "metro": "803",
            "region": "CA",
            "zip": "90049"
        },
        "dpidsha1": "AA000DFE74168477C70D291f574D344790E0BB11",
        "dpidmd5": "AA003EABFB29E6F759F3BDAB34E50BB11",
        "carrier": "310-410",
        "language": "en",
        "make": "Apple",
        "model": "iPhone",
        "os": "iOS",
        "osv": "6.1",
        "js": 1,
        "connectiontype": 3,
        "devicetype": 1
    },
    "user": {
        "id": "ffffffd5135596709273b3a1a07e466ea2bf4fff",
        "yob": "1984",
        "gender": "M"
    },
    "at": 2,
    "bcat": [
        "IAB25",
        "IAB7-39",
        "IAB8-18",
        "IAB8-5",
        "IAB9-9"
    ],
    "badv": [
        "apple.com",
        "go-text.me",
        "heywire.com"
    ]
}
```
