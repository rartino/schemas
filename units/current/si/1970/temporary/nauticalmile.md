# nautical mile, M (unit)
This page documents an [OPTIMADE](https://www.optimade.org/) [Unit Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/nauticalmile`](https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/nauticalmile)**  
**Definition name:** `nauticalmile`

**Unit name:** nautical mile  
**Latin symbol:** M  
**Display symbol:** M  
  
**Description:** A unit of length primarily used in navigation defined as 1852 m using the 1960 SI meter.

The nautical mile appear in the International System of Units (SI), 1th ed. (1970) defined as "1 nautical mile = 1852 m" with the footnote "The nautical mile is a special unit employed for marine and aerial navigation to express distance. The conventional value given above was adopted by the First International Extraordinary Hydrographic Conference, Monaco, 1929, under the name 'International nautical mile'."
Historically, the nautical mile was defined as the meridian arc length corresponding to one arcminute of latitude.

The International System of Units (SI), 1th ed. (1970) categorizes the unit as "Units in use temporarily with the International Sytem."
The International System of Units (SI), 7th ed. (1998) changes the categorization to "Other non-SI units currently accepted for use with the International System" and adds to the footnote that: "As yet there is no internationally agreed symbol. This unit was originally chosen because one nautical mile on the surface of the Earth subtends approximately one minute of angle at the centre."
The International System of Units (SI), 8th ed. (2006) changes the categorization to "Other non-SI units" and adjusts the footnote to say: "As yet there is no internationally agreed symbol, but the symbols M, NM, Nm, and nmi are all used; in the table the symbol M is used. The unit was originally chosen, and continues to be used, because one nautical mile on the surface of the Earth subtends approximately one minute of angle at the centre of the Earth, which is convenient when latitude and longitude are measured in degrees and minutes of angle."
The nautical mile is omitted in the International System of Units (SI), 9th Edition (2019).

**Resources:**

- [Definition in the International System of Units (SI), 1st Edition](https://www.bipm.org/en/publications/si-brochure)
- [Wikipedia article describing the unit](https://en.wikipedia.org/wiki/Nautical_mile)


**Formats:** [[JSON](nauticalmile.json)] [[MD](nauticalmile.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.optimade.org/units/v1.2.0/si/1970/temporary/nauticalmile",
    "title": "nautical mile",
    "symbol": "M",
    "display-symbol": "M",
    "alternate-symbols": [
        "NM",
        "Nm",
        "nmi"
    ],
    "description": "A unit of length primarily used in navigation defined as 1852 m using the 1960 SI meter.\n\nThe nautical mile appear in the International System of Units (SI), 1th ed. (1970) defined as \"1 nautical mile = 1852 m\" with the footnote \"The nautical mile is a special unit employed for marine and aerial navigation to express distance. The conventional value given above was adopted by the First International Extraordinary Hydrographic Conference, Monaco, 1929, under the name 'International nautical mile'.\"\nHistorically, the nautical mile was defined as the meridian arc length corresponding to one arcminute of latitude.\n\nThe International System of Units (SI), 1th ed. (1970) categorizes the unit as \"Units in use temporarily with the International Sytem.\"\nThe International System of Units (SI), 7th ed. (1998) changes the categorization to \"Other non-SI units currently accepted for use with the International System\" and adds to the footnote that: \"As yet there is no internationally agreed symbol. This unit was originally chosen because one nautical mile on the surface of the Earth subtends approximately one minute of angle at the centre.\"\nThe International System of Units (SI), 8th ed. (2006) changes the categorization to \"Other non-SI units\" and adjusts the footnote to say: \"As yet there is no internationally agreed symbol, but the symbols M, NM, Nm, and nmi are all used; in the table the symbol M is used. The unit was originally chosen, and continues to be used, because one nautical mile on the surface of the Earth subtends approximately one minute of angle at the centre of the Earth, which is convenient when latitude and longitude are measured in degrees and minutes of angle.\"\nThe nautical mile is omitted in the International System of Units (SI), 9th Edition (2019).",
    "standard": {
        "name": "gnu units",
        "version": "3.15",
        "symbol": "nauticalmile"
    },
    "resources": [
        {
            "relation": "Definition in the International System of Units (SI), 1st Edition",
            "resource-id": "https://www.bipm.org/en/publications/si-brochure"
        },
        {
            "relation": "Wikipedia article describing the unit",
            "resource-id": "https://en.wikipedia.org/wiki/Nautical_mile"
        }
    ],
    "defining-relation": {
        "base-units": [
            {
                "symbol": "m",
                "id": "https://schemas.optimade.org/units/v1.2.0/si/1960/base/metre"
            }
        ],
        "base-units-expression": "m",
        "scale": {
            "numerator": 1852
        }
    },
    "x-optimade-definition": {
        "kind": "unit",
        "format": "1.2",
        "version": "1.2.0",
        "name": "nauticalmile"
    },
    "$schema": "https://schemas.optimade.org/meta/v1.2.0/optimade/physical_unit_definition.md"
}
```