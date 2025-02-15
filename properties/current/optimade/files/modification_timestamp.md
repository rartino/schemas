# Modification timestamp (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/modification_timestamp`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/modification_timestamp)**  
**Definition name:** `modification_timestamp`

**Property name:** Modification timestamp  
**Description:** Timestamp of the last modification of file contents. A modification is understood as an addition, change or deletion of one or more bytes, resulting in file contents different from the previous.  
**Type:** timestamp  

**Requirements/Conventions:**

- Timestamps of subsequent file modifications SHOULD be increasing (not earlier than previous timestamps).

**Examples:**

- `2020-04-05T14:30:20Z`

**Formats:** [[JSON](modification_timestamp.json)] [[MD](modification_timestamp.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/modification_timestamp",
    "title": "Modification timestamp",
    "x-optimade-type": "timestamp",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "modification_timestamp"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Timestamp of the last modification of file contents. A modification is understood as an addition, change or deletion of one or more bytes, resulting in file contents different from the previous.\n\n**Requirements/Conventions:**\n\n- Timestamps of subsequent file modifications SHOULD be increasing (not earlier than previous timestamps).",
    "examples": [
        "2020-04-05T14:30:20Z"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```