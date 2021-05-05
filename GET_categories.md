# How do I retreive the category list?

Q: What are "categories"?  
A: I DONT KNOW :D:D:D:D

[Have a look at the products tab in our technical API documentation for further information](https://api.otto.market/docs/03_Products/v2/products-interface.html)

### GET Request

```http
GET
https://api.otto.market/v2/products/categories
```

### Example Response (response shortened for presentation)

```JSON
{
    "categoryGroups": [
        {
            "categoryGroup": "Abbruchhammer",
            "categories": [
                "Abbruchhammer",
                "Druckluft-Meißelhammer",
                "Akku-Meißelhammer"
            ],
            "variationThemes": [
                "Leistung maximal",
                "Länge",
                "Breite",
                "Funktionen",
                "Gewicht",
                "Farbe",
                "Kabellänge",
                "Höhe",
                "Anzahl Teile"
            ],
            "title": "{brand} {category} »{productLine}«, [{Leistung maximal} in W], [für {Typ Aufnahme}],  ({Set-Typ}, [{Anzahl Teile}-{Anzahl Teile.unit}], {Set-Info}) {Besondere Merkmale}",
            "attributes": [
                {
                    "name": "Anzahl Teile",
                    "attributeGroup": "Produktdetails",
                    "type": "INTEGER",
                    "multiValue": false,
                    "unit": "tlg.",
                    "unitDisplayName": "Teilig",
                    "featureRelevance": [
                        "TITLE",
                        "VARIATION_THEME"
                    ],
                    "relevance": "LOW",
                    "description": "",
                    "reference": ""
                },
```

Q: What do `relevance` and `featureRelevance` mean in my case?  
A: `relevance` can be `HIGH`, `MEDIUM` or `LOW` and indicates how important an attribute is.
