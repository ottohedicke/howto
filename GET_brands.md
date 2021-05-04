# Q: How do I retreive all available brands on OTTO Market?

### GET Request:

```http
GET
https://api.otto.market/v2/products/brands
```


### Example Response (response contains more than 50.000 lines)

JSON-Format:
```JSON
[
    {
        "name": "- CONTRAER -"
    },
    {
        "name": "!Solid"
    },
    {
        "name": "'47 Brand"
    },
    {
        "name": "@tec"
    },
    {
        "name": "*Alpina*"
    },
    
```

Q: What is a "brand"?  
A: The name of the brand as it is known on the OTTO marketplace.

Q: What type are the brands provided as?  
A: The brand names are provided as `strings`.
