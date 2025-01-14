# note (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/references/note`](https://schemas.optimade.org/properties/v1.2.0/optimade/references/note)**  
**Definition name:** `note`

**Property name:** note  
**Description:** Additional information about the reference (the note field in the BibTeX specification).  
**Type:** string  



**Examples:**

- `Accessed: 2022-11-04`

**Formats:** [[JSON](note.json)] [[MD](note.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/references/note",
    "title": "note",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "note"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Additional information about the reference (the note field in the BibTeX specification).",
    "examples": [
        "Accessed: 2022-11-04"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```