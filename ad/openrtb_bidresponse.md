```
{
    "id": "IxexyLDIIk",
    "seatbid": [
        {
            "bid": [
                {
                    "id": "1",
                    "impid": "1",
                    "price": 0.751371,
                    "adid": "52a5516d29e435137c6f6e74",
                    "nurl": "http://ads.com/win/112770_1386565997?won=${AUCTION_PRICE}",
                    "adm": "<a href=\"http://ads.com/click/112770_1386565997\"><img src=\"http://ads.com/img/112770_1386565997?won=${AUCTION_PRICE}\" width=\"728\" height=\"90\" border=\"0\" alt=\"Advertisement\" /></a>"
                }
            ]
        }
    ],
    "cur": "USD"
}
```
| field  | desc |
| ------------- | ------------- |
| id  | string; required; ID of the bid request to which this is a response.  |
| seatbid  | object array; Array of seatbid objects; 1+ required if a bid is to be made.  |
| seatbid[0].bid  | object array; required; Array of 1+ Bid objects each related to an impression. Multiple bids can relate to the same impression. |
| seatbid[0].bid[0].id  | string; required; Bidder generated bid ID to assist with logging/tracking.  |
| seatbid[0].bid[0].impid  | string; required; ID of the Imp object in the related bid request.  |
| seatbid[0].bid[0].price  | float; required; Bid price expressed as CPM although the actual transaction is for a unit impression only. Note that while the type indicates float, integer math is highly recommended when handling currencies (e.g., BigDecimal in Java).  |
| seatbid[0].bid[0].adid|string; ID of a preloaded ad to be served if the bid wins. |
| seatbid[0].bid[0].nurl|string; Win notice URL called by the exchange if the bid wins; optional means of serving ad markup. |
| seatbid[0].bid[0].adm|string; Optional means of conveying ad markup in case the bid wins; supersedes the win notice if markup is included in both. |
| cur|string; default “USD”;Bid currency using ISO-4217 alpha codes. |
