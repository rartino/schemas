# school (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/references/school`](https://schemas.optimade.org/properties/v1.2.0/optimade/references/school)**  
**Definition name:** `school`

**Property name:** school  
**Description:** The name of the school where a thesis was written (the school field in the BibTeX specification).  
**Type:** string  



**Examples:**

- `Stanford University`

**Formats:** [[JSON](school.json)] [[MD](school.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/references/school",
    "title": "school",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "school"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "The name of the school where a thesis was written (the school field in the BibTeX specification).",
    "examples": [
        "Stanford University"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```