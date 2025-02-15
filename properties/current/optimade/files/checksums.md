# Checksums (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/checksums`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/checksums)**  
**Definition name:** `checksums`

**Property name:** Checksums  
**Description:** Dictionary providing checksums of file contents.  
**Type:** dictionary  

**Requirements/Conventions:**

- The keys in the dictionary identify checksum functions and the values are strings containing the corresponding checksum.

- Supported dictionary keys: `md5`, `sha1`, `sha224`, `sha256`, `sha384`, `sha512`.
  Checksums outside this list MAY be used, but their names MUST be prefixed by database-provider-specific namespace prefix.

**Examples:**

- `{'sha1': '8072f787eada2c50b60a27f3f098fbac7eea08cf'}`

**Formats:** [[JSON](checksums.json)] [[MD](checksums.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/checksums",
    "title": "Checksums",
    "x-optimade-type": "dictionary",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "checksums"
    },
    "type": [
        "object",
        "null"
    ],
    "description": "Dictionary providing checksums of file contents.\n\n**Requirements/Conventions:**\n\n- The keys in the dictionary identify checksum functions and the values are strings containing the corresponding checksum.\n\n- Supported dictionary keys: `md5`, `sha1`, `sha224`, `sha256`, `sha384`, `sha512`.\n  Checksums outside this list MAY be used, but their names MUST be prefixed by database-provider-specific namespace prefix.",
    "examples": [
        {
            "sha1": "8072f787eada2c50b60a27f3f098fbac7eea08cf"
        }
    ],
    "x-optimade-unit": "inapplicable",
    "properties": {
        "md5": {
            "x-optimade-type": "string",
            "x-optimade-unit": "inapplicable",
            "type": [
                "string"
            ]
        },
        "sha1": {
            "x-optimade-type": "string",
            "x-optimade-unit": "inapplicable",
            "type": [
                "string"
            ]
        },
        "sha224": {
            "x-optimade-type": "string",
            "x-optimade-unit": "inapplicable",
            "type": [
                "string"
            ]
        },
        "sha384": {
            "x-optimade-type": "string",
            "x-optimade-unit": "inapplicable",
            "type": [
                "string"
            ]
        },
        "sha512": {
            "x-optimade-type": "string",
            "x-optimade-unit": "inapplicable",
            "type": [
                "string"
            ]
        }
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```