---
layout: bidder
title: RiseXChange
description: Prebid RiseXChange Bidder Adapter
multiformat_supported: will-bid-on-any
pbjs: true
biddercode: risexchange
media_types: banner, video, native
schain_supported: true
coppa_supported: true
pbs: false
tcfeu_supported: true
gpp_supported: true
gpp_sids: tcfeu, usstate_all, usp
usp_supported: true
floors_supported: true
userIds: all
gvl_id: 1043
sidebarType: 1
---

### Note

The RiseXChange adapter requires setup and approval. Please reach out to [prebid-rise-engage@risecodes.com] to setup an account.

### Bid Parameters

#### Banner, Video, Native

{: .table .table-bordered .table-striped }

| Name | Scope | Type | Description | Example
| ---- | ----- | ---- | ----------- | -------
| `org` | required | String |  RiseXChange publisher Id  | "1234567890abcdef12345678"
| `floorPrice` | optional | Number |  Minimum price in USD. <br/><br/> **WARNING:**<br/> Misuse of this parameter can impact revenue | 2.00
| `placementId` | optional | String |  A unique placement identifier  | "12345678"
| `testMode` | optional | Boolean |  This activates the test mode  | false
| `rtbDomain` | optional | String |  Sets the seller end point    | "www.test.com"

### Example

```javascript
var adUnits = [{
        code: 'banner-div',
        mediaTypes: {
            banner: {
                sizes: [
                    [300, 250],
                    [728, 90]
                ]
            }
        },
        bids: [{
            bidder: 'risexchange',
            params: {
                org: '1234567890abcdef12345678', // Required
                floorPrice: 0.05, // Optional
                placementId: '12345678', // Optional
                testMode: false, // Optional,
                rtbDomain: 'www.test.com' //Optional
            }
        }]
    },
    {
        code: 'dfp-video-div',
        sizes: [
            [640, 480]
        ],
        mediaTypes: {
            video: {
                playerSize: [
                    [640, 480]
                ],
                context: 'instream'
            }
        },
        bids: [{
            bidder: 'risexchange',
            params: {
                org: '1234567890abcdef12345678', // Required
                floorPrice: 5.00, // Optional
                placementId: '12345678', // Optional
                testMode: false, // Optional,
                rtbDomain: 'www.test.com' //Optional
            }
        }]
    }
];
```

### Configuration

We recommend setting UserSync by iframe for monetization.

### Versions

Prebid versions 5.0-5.3 are not supported.

Banner >= 6.14.0.

Native >= 9.27.0.

Multi-format requests >= 9.27.0.
