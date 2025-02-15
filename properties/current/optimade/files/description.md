# Description (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/description`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/description)**  
**Definition name:** `description`

**Property name:** Description  
**Description:** Free-form description of a file.  
**Type:** string  



**Examples:**

- `POSCAR format file`

**Formats:** [[JSON](description.json)] [[MD](description.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/description",
    "title": "Description",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "description"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Free-form description of a file.",
    "examples": [
        "POSCAR format file"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```