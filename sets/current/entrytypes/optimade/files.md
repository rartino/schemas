# Files (entrytype)
This page documents an [OPTIMADE](https://www.optimade.org/) [Entrytype Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/files`](https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/files)**  
**Definition name:** `files`

**Entrytype name:** Files  
**Description:** The files entry type describes a file with metadata and an URL to retrive it  

**Formats:** [[JSON](files.json)] [[MD](files.md)]

This entrytype defines the following properties:

* **[ID](../../../../properties/v1.2.0/core/id)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/id`](https://schemas.optimade.org/properties/v1.2.0/core/id)  
  A unique string referencing a specific entry in the database.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - Taken together, the ID and entry type MUST uniquely identify the entry.
    - Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.
    - IDs MAY change over time.


* **[Type](../../../../properties/v1.2.0/core/type)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/type`](https://schemas.optimade.org/properties/v1.2.0/core/type)  
  The name of the type of an entry.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - MUST be an existing entry type.
    - The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.


* **[Immutable ID (immutable_id)](../../../../properties/v1.2.0/core/immutable_id)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/immutable_id`](https://schemas.optimade.org/properties/v1.2.0/core/immutable_id)  
  The entry's immutable ID (e.g., a UUID).

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - This is important for databases having preferred IDs that point to "the latest version" of a record, but still offer access to older variants.
    - This ID maps to the version-specific record, in case it changes in the future.


* **[Last modified (last_modified)](../../../../properties/v1.2.0/core/last_modified)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/core/last_modified`](https://schemas.optimade.org/properties/v1.2.0/core/last_modified)  
  Date and time representing when the entry was last modified.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[URL](../../../../properties/v1.2.0/optimade/files/url)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/url`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/url)  
  The URL to get the contents of a file.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MUST be included by default in the response.
    - The URL MUST point to the actual contents of a file (i.e. byte stream), not an intermediate (preview) representation. For example, if referring to a file on GitHub, a link should point to raw contents.


* **[URL stable until (url_stable_until)](../../../../properties/v1.2.0/optimade/files/url_stable_until)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/url_stable_until`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/url_stable_until)  
  Point in time until which the URL in `url` is guaranteed to stay stable.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - `null` means that there is no stability guarantee for the URL in url.
      Indefinite support could be communicated by providing a date sufficiently far in the future, for example, 9999-12-31.


* **[Name](../../../../properties/v1.2.0/optimade/files/name)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/name`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/name)  
  Base name of a file.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - File name extension is an integral part of a file name and, if available, MUST be included.


* **[Size](../../../../properties/v1.2.0/optimade/files/size)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/size`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/size)  
  Size of a file in bytes.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - If provided, it MUST be guaranteed that either exact size of a file is given or its upper bound.
      This way if a client reserves a static buffer or truncates the download stream after this many bytes the whole file would be received.
      Such provision is included to allow the providers to serve on-the-fly compressed files.


* **[Media type (media_type)](../../../../properties/v1.2.0/optimade/files/media_type)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/media_type`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/media_type)  
  Media type identifier (also known as MIME type), for a file as per [RFC 6838 Media Type Specifications and Registration Procedures](https://datatracker.ietf.org/doc/html/rfc6838).

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.

* **[Version](../../../../properties/v1.2.0/optimade/files/version)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/version`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/version)  
  Version information of a file (e.g. commit, revision, timestamp).

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - If provided, it MUST be guaranteed that file contents pertaining to the same combination of id and version are the same.


* **[Modification timestamp (modification_timestamp)](../../../../properties/v1.2.0/optimade/files/modification_timestamp)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/modification_timestamp`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/modification_timestamp)  
  Timestamp of the last modification of file contents. A modification is understood as an addition, change or deletion of one or more bytes, resulting in file contents different from the previous.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - Timestamps of subsequent file modifications SHOULD be increasing (not earlier than previous timestamps).


* **[Description](../../../../properties/v1.2.0/optimade/files/description)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/description`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/description)  
  Free-form description of a file.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.

* **[Checksums](../../../../properties/v1.2.0/optimade/files/checksums)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/checksums`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/checksums)  
  Dictionary providing checksums of file contents.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - The keys in the dictionary identify checksum functions and the values are strings containing the corresponding checksum.
    
    - Supported dictionary keys: `md5`, `sha1`, `sha224`, `sha256`, `sha384`, `sha512`.
      Checksums outside this list MAY be used, but their names MUST be prefixed by database-provider-specific namespace prefix.


* **[Access time (atime)](../../../../properties/v1.2.0/optimade/files/atime)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/atime`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/atime)  
  Time of last access of a file as per POSIX standard.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.

* **[Change time (ctime)](../../../../properties/v1.2.0/optimade/files/ctime)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime)  
  Time of last status change of a file as per POSIX standard.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.

* **[Modification time (mtime)](../../../../properties/v1.2.0/optimade/files/ctime)** (property) - [`https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime`](https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime)  
  Time of last modification of a file as per POSIX standard.

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** Support for queries on this property is OPTIONAL.
    - **Response:** MAY be included by default in the response.
    - It should be noted that the values of `last_modified`, `modification_timestamp` and `mtime` do not necessary match.
      `last_modified` pertains to the modification of the OPTIMADE metadata, `modification_timestamp` pertains to file contents and `mtime` pertains to the modification of the file (not necessary changing its contents).
      For example, appending an empty string to a file would result in the change of `mtime` in some operating systems, but this would not be deemed as a modification of its contents.



**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/sets/v1.2.0/entrytypes/optimade/files",
    "title": "Files",
    "description": "The files entry type describes a file with metadata and an URL to retrive it",
    "x-optimade-definition": {
        "kind": "entrytype",
        "format": "1.2",
        "version": "1.2.0",
        "name": "files"
    },
    "type": "object",
    "properties": {
        "id": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/id",
            "title": "ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "id"
            },
            "type": [
                "string"
            ],
            "description": "A unique string referencing a specific entry in the database.\n\n**Requirements/Conventions:**\n\n- Taken together, the ID and entry type MUST uniquely identify the entry.\n- Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.\n- IDs MAY change over time.",
            "examples": [
                "db/1234567",
                "cod/2000000",
                "cod/2000000@1234567",
                "nomad/L1234567890",
                "42"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "type": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/type",
            "title": "Type",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "type"
            },
            "type": [
                "string"
            ],
            "description": "The name of the type of an entry.\n\n**Requirements/Conventions:**\n\n- MUST be an existing entry type.\n- The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.",
            "examples": [
                "structures"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "immutable_id": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/immutable_id",
            "title": "Immutable ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "immutable_id"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The entry's immutable ID (e.g., a UUID).\n\n**Requirements/Conventions:**\n\n- This is important for databases having preferred IDs that point to \"the latest version\" of a record, but still offer access to older variants.\n- This ID maps to the version-specific record, in case it changes in the future.",
            "examples": [
                "8bd3e750-b477-41a0-9b11-3a799f21b44f",
                "fjeiwoj,54;@=%<>#32"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "last_modified": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/core/last_modified",
            "title": "Last modified",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "last_modified"
            },
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "Date and time representing when the entry was last modified.",
            "examples": [
                "2007-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "url": {
            "x-optimade-requirements": {
                "support": "must",
                "sortable": false,
                "query-support": "none",
                "response-level": "must"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/url",
            "title": "URL",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "url"
            },
            "type": [
                "string"
            ],
            "description": "The URL to get the contents of a file.\n\n**Requirements/Conventions:**\n\n- The URL MUST point to the actual contents of a file (i.e. byte stream), not an intermediate (preview) representation. For example, if referring to a file on GitHub, a link should point to raw contents.",
            "examples": [
                "https://example.org/files/cifs/1000000.cif"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "url_stable_until": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/url_stable_until",
            "title": "URL stable until",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "url_stable_until"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "Point in time until which the URL in `url` is guaranteed to stay stable.\n\n**Requirements/Conventions:**\n\n- `null` means that there is no stability guarantee for the URL in url.\n  Indefinite support could be communicated by providing a date sufficiently far in the future, for example, 9999-12-31.",
            "examples": [
                "2052-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable",
            "format": "date-time"
        },
        "name": {
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/name",
            "title": "Name",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "name"
            },
            "type": [
                "string"
            ],
            "description": "Base name of a file.\n\n**Requirements/Conventions:**\n\n- File name extension is an integral part of a file name and, if available, MUST be included.",
            "examples": [
                "1000000.cif"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "size": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/size",
            "title": "Size",
            "x-optimade-type": "integer",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "size"
            },
            "x-optimade-unit-definitions": [
                {
                    "$id": "https://schemas.optimade.org/units/v1.2.0/iso-iec-80000/2008/information_science_and_technology/byte",
                    "title": "byte",
                    "symbol": "B",
                    "display-symbol": "B",
                    "description": "A unit of digital information representing eight bits, defined in the International System of Quantities in ISO/IEC 80000-13 (2008).\n\n\"In English, the name byte, symbol B, is used as a synonym for octet. Here byte means an eight-bit byte.\" [ISO/IEC 80000-13 (2008)]",
                    "standard": {
                        "name": "gnu units",
                        "version": "3.15",
                        "symbol": "byte"
                    },
                    "resources": [
                        {
                            "relation": "Defining standard",
                            "resource-id": "https://www.iso.org/standard/31898.html"
                        },
                        {
                            "relation": "Wikipedia article describing the unit",
                            "resource-id": "https://en.wikipedia.org/wiki/Byte"
                        }
                    ],
                    "defining-relation": {
                        "base-units": [
                            {
                                "symbol": "bit",
                                "id": "https://schemas.optimade.org/units/v1.2.0/information/bit"
                            }
                        ],
                        "base-units-expression": "bit",
                        "scale": {
                            "numerator": 8
                        }
                    },
                    "x-optimade-definition": {
                        "kind": "unit",
                        "format": "1.2",
                        "version": "1.2.0",
                        "name": "byte"
                    }
                }
            ],
            "type": [
                "integer",
                "null"
            ],
            "description": "Size of a file in bytes.\n\n**Requirements/Conventions:**\n\n- If provided, it MUST be guaranteed that either exact size of a file is given or its upper bound.\n  This way if a client reserves a static buffer or truncates the download stream after this many bytes the whole file would be received.\n  Such provision is included to allow the providers to serve on-the-fly compressed files.",
            "examples": [
                4711
            ],
            "x-optimade-unit": "byte"
        },
        "media_type": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
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
            "x-optimade-unit": "inapplicable"
        },
        "version": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/version",
            "title": "Version",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "version"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "Version information of a file (e.g. commit, revision, timestamp).\n\n**Requirements/Conventions:**\n\n- If provided, it MUST be guaranteed that file contents pertaining to the same combination of id and version are the same.",
            "examples": [
                "3.2.6"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "modification_timestamp": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
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
            "x-optimade-unit": "inapplicable"
        },
        "description": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
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
            "x-optimade-unit": "inapplicable"
        },
        "checksums": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
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
            }
        },
        "atime": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/atime",
            "title": "Access time",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "atime"
            },
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "Time of last access of a file as per POSIX standard.",
            "examples": [
                "2007-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "ctime": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
            "$id": "https://schemas.optimade.org/properties/v1.2.0/optimade/files/ctime",
            "title": "Change time",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "ctime"
            },
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "Time of last status change of a file as per POSIX standard.",
            "examples": [
                "2007-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "mtime": {
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "none",
                "response-level": "may"
            },
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
            "x-optimade-unit": "inapplicable"
        }
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/entrytype_definition.md"
}
```