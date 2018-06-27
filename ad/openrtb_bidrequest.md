```
{
    "id": "7979d0c78074638bbdf739ffdf285c7e1c74a691",
    "imp": [
        {
            "id": "1",
            "banner": {
                "w": 300,
                "h": 250,
                "pos": 1
            }
            "instl": 0,
            "bidfloor": 0.5
        }
    ],
    "app": {
        "id": "20625",
        "name": "Yahoo Weather",
        "cat": [
            "IAB15",
            "IAB15-10"
        ],
        "ver": "1.0.2",
        "bundle": "628677149"
    },
    "device": {
        "make": "Samsung",
        "model": "SCH-I535",
        "os": "Android",
        "osv": "4.3",
        "ua": "Mozilla/5.0 (Linux; U; Android 4.3; en-us; SCH-I535 Build/JSS15J) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 Mobile Safari/534.30",
        "ip": "192.168.1.1",
        "language": "en",
        "devicetype": 1,
        "js": 1,
        "connectiontype": 3,
        "dpidsha1": "F099E6D1C485756C45D1EEACB33C73B55C4BC499",
        "carrier": "Verizon Wireless",
        "geo": {
            "country": "USA",
            "region": "PA",
            "type": 3,
            "ext": {
                "latlonconsent": 1
            }
        }
    },
    "user": {
        "id": "bd5adc55dcbab4bf090604df4f543d90b09f0c88",
        "ext": {
            "sessiondepth": 207
        }
    }
}
```
| field  | desc |
| ------------- | ------------- |
| id  | string; required; Unique ID of the bid request, provided by the exchange.  |
| imp  | object array; required; Array of Imp objects representing the impressionsoffered. At least 1 Impobjectis required.  |
| imp[0].id  | string; required; A unique identifier for this impression within the context of the bid request (typically, starts with 1 and increments.  |
| imp[0].banner  | A Banner object; required if this impression is offered as a banner ad opportunity.  |
| imp[0].banner.w  | integer; recommended; Width of the impression in pixels. If neither wmin nor wmax are specified, this value is an exact width requirement. Otherwise it is a preferred width. |
| imp[0].banner.h  | integer; recommended; Height of the impression in pixels. If neither hmin nor hmax are specified, this value is an exact height requirement. Otherwise it is a preferred height.  |
| imp[0].banner.pos  | integer; <a href="https://github.com/jialechan/notes/blob/master/ad/list/Ad_Position.md" target="_blank">Ad position on screen</a>  |
| imp[0].instl  | integer; default 0; 1 = the ad is interstitial or full screen, 0 = not interstitial.  |
| imp[0].bidfloor  | float; default 0; Minimum bid for this impression expressed in CPM.  |
| app  | object; recommended; Details via an App object about the publisher’s app (i.e., non-browser applications). Only applicable and recommended for apps.  |
| app.id  | string; recommended; Exchange-specific app ID.  |
| app.name  | string; App name (may be aliased at the publisher’s request).  |
| app.cat  | string array; Array of IAB <a href="https://github.com/jialechan/notes/blob/master/ad/list/Content_Categories.md">content categories</a> of the app.  |
| app.ver  | Application version.  |
| app.bundle  | Application bundle or package name (e.g., com.foo.mygame); intended to be a unique ID across exchanges. |
| device  | object; recommended; Details via a Device object about the user’s device to which the impression will be delivered.  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

