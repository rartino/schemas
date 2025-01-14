# bibliographic type (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/references/bib_type`](https://schemas.optimade.org/properties/v1.2.0/optimade/references/bib_type)**  
**Definition name:** `bib_type`

**Property name:** bibliographic type  
**Description:** Type of the reference (the type field in the BibTeX specification).  
**Type:** string  



**Examples:**

- `Research Note`

**Formats:** [[JSON](bib_type.json)] [[MD](bib_type.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/references/bib_type",
    "title": "bibliographic type",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "bib_type"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Type of the reference (the type field in the BibTeX specification).",
    "examples": [
        "Research Note"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```