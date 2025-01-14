# Media type (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/media_type`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/media_type)**  
**Definition name:** `media_type`

**Property name:** Media type  
**Description:** Media type identifier (also known as MIME type), for a file as per [RFC 6838 Media Type Specifications and Registration Procedures](https://datatracker.ietf.org/doc/html/rfc6838).  
**Type:** string  



**Examples:**

- `chemical/x-cif`

**Formats:** [[JSON](media_type.json)] [[MD](media_type.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/media_type",
    "title": "Media type",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "media_type"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Media type identifier (also known as MIME type), for a file as per [RFC 6838 Media Type Specifications and Registration Procedures](https://datatracker.ietf.org/doc/html/rfc6838).",
    "examples": [
        "chemical/x-cif"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```