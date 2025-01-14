# Modification time (property)
This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime)**  
**Definition name:** `mtime`

**Property name:** Modification time  
**Description:** Time of last modification of a file as per POSIX standard.  
**Type:** timestamp  

**Requirements/Conventions:**

- It should be noted that the values of `last_modified`, `modification_timestamp` and `mtime` do not necessary match.
  `last_modified` pertains to the modification of the OPTIMADE metadata, `modification_timestamp` pertains to file contents and `mtime` pertains to the modification of the file (not necessary changing its contents).
  For example, appending an empty string to a file would result in the change of `mtime` in some operating systems, but this would not be deemed as a modification of its contents.

**Examples:**

- `2007-04-05T14:30:20Z`

**Formats:** [[JSON](ctime.json)] [[MD](ctime.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime",
    "title": "Modification time",
    "x-optimade-type": "timestamp",
    "x-optimade-definition": {
        "kind": "property",
        "version": "1.2.0",
        "format": "1.2",
        "name": "mtime"
    },
    "type": [
        "string",
        "null"
    ],
    "format": "date-time",
    "description": "Time of last modification of a file as per POSIX standard.\n\n**Requirements/Conventions:**\n\n- It should be noted that the values of `last_modified`, `modification_timestamp` and `mtime` do not necessary match.\n  `last_modified` pertains to the modification of the OPTIMADE metadata, `modification_timestamp` pertains to file contents and `mtime` pertains to the modification of the file (not necessary changing its contents).\n  For example, appending an empty string to a file would result in the change of `mtime` in some operating systems, but this would not be deemed as a modification of its contents.",
    "examples": [
        "2007-04-05T14:30:20Z"
    ],
    "x-optimade-unit": "inapplicable",
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/property_definition.md"
}
```