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

Q: What does `relevance` mean in my case?  
A: `relevance` can be `HIGH`, `MEDIUM` or `LOW` and indicates the relevance and weighting for the visibility of the individual attributes.

Q: What does `featureRelevance` mean in my case?  
A: `featureRelevance` indicates what your information about the attribute is used for.
`LEGAL` is a mandatory field. All others are optional. Nevertheless, you should fill them in if possible, as they increase the visibility of your products on otto.de.

For further information see [OTTOmarket Kategorienliste](https://og2gether-my.sharepoint.com/:x:/g/personal/micha_saake_otto_de/EXg5Id8bTxNKuV8mRkQ1wrsBNFuBrjP8iQJINZjcezvjdg?e=cgq4Cz).
