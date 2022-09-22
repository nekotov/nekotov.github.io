---
title: Parsing CeX (WeBuy.com)
layout: post
---

## Intro
I came up with the idea to write a website parser in Python3. The site for the sale / purchase of used equipment is called CeX.

##Idea
After some research I found a button that requests information about products.

![Button image](https://i.imgur.com/7mgifnr.png)

I click on it and…

I got a bunch of responses, but I got one interesting XHR request. Response for this was json.

Json data contains useful information and a number of total requests.

Example of the first Json useful data object

```json
{
    "0": {
        "boxId": "SKOPSONWFXB700B",
        "boxName": "Sony WF-XB700 In-Ear True Wireless Headphones, B",
        "categoryName": "Koptelefoons",
        "categoryFriendlyName": "Headphones",
        "superCatId": 5,
        "superCatName": "Electronics",
        "superCatFriendlyName": "Electronics",
        "imageUrls": {
            "large": "...",
            "medium":"...",
            "small": "..."
        },
        "isNewBox": 0,
        "sellPrice": 32,
        "cashPrice": 13,
        "exchangePrice": 18,
        "boxRating": null
        "categoryId": 973,
        "cannotbuy": 0,
        "outOfEcomStock": 0,
        "ecomQuantityOnHand": 1,
        "collectionQuantity": 1,
        "boxSaleAllowed": 1,
        "boxBuyAllowed": 1,
        "boxWebSaleAllowed": 1,
        "boxWebBuyAllowed": 1,
        "imageNames": null,
        "isImageTypeInternal": null
    }
}
```
