# Inventory-tracker 🗃

A way to track Inventory in a simple way for storage. Right now I'm still in the planning stage of this project will have an outline of how to use the api created and a way to add the to what is in the inventory delete from the inventory and check in and out of the inventory.
<br>
I plan on using a rasberry pi or arduino mega to scan barcodes and check againts the inventory. I also plan on adding a way for the inventory to have items added and removed throught the website and adding a barcode creator so that it is possible to a print of the barcodes from the website. As well as create new ones if old ones get distroyed.

<br>
<br>

# API Documentaion

This is where the documentaion of the api that I create will go including the creation of the docker file and every single thing I installed to create a REST API for the tracking of the inventory.

## Usage

All responses will be in this form:

```JSON
{
    "data": "Mixed type holding the content of the response",
    "message": "Description of what happened"
}
```

### List all Items

**Definition**

`GET /iventory`

**Response**

- `200 OK` on success

```JSON
[
    {
        "item-id": "string",
        "name": "string",
        "barcode": "num",
        "category": "string",
        "inventory": "num",
        "location": {
            "site": "string",
            "name": "string",
            "shorthand": "string"
        },
    }
]
```

<br>
<br>

### Adding a New Item

**Definition**

`POST /inventory`

**Arguments**

Item

- `"item-id":string` Unique string of letters and numbers for idenification of an item e.g. `SX0001`
- `"name":string` user readble name of the item e.g. `3-Pin XLR`
- `"barcode":num` Barcode given to the item e.g. `9772204821170`
- `"category":string` Category of the item e.g. `Sound`
- `"inventory":num` Number of how many item are in storage e.g. `31`

<br>
Location

- `"site":string` Name of site stored at e.g. `Paradise`
- `"name":string` Name of room and shelf item is stored e.g. `TS-Shelf01`
- `"shorthand":string` Short hand of the long version of name above e.g. `TS-S1`

**Response**

- `201 Created` on success

```JSON
{
    "item-id": "string",
    "name": "string",
    "barcode": "num",
    "category": "string",
    "inventory": "num",
    "location": {
        "site": "string",
        "name": "string",
        "shorthand": "string"
    },
}
```

<br>
<br>

### Looking up items details

**Definition**

`GET /inventory/<item-id>`

**Response**

- `404 Not Found` if the item does not exist
- `200 OK` on success

```JSON
{
    "item-id": "string",
    "name": "string",
    "barcode": "num",
    "category": "string",
    "inventory": "num",
    "location": {
        "site": "string",
        "name": "string",
        "shorthand": "string"
    },
}
```

<br>
<br>

### Looking up items details

**Definition**

`DELETE /inventory/<item-id>`

**Response**

- `404 Not Found` if the item does not exist
- `204 No Content` on success

<br>
<br>

## Website intergration example

This is where the example of adding the inventory tracking system to the production website I'm wrighting will go.

<br>
<br>

## Connect with me:

[<img align="left" alt="codeSTACKr | Twitter" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/twitter.svg" />][twitter]
[<img align="left" alt="codeSTACKr | Instagram" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/instagram.svg" />][instagram]

<br />

[twitter]: https://twitter.com/XeTENcO
[instagram]: https://instagram.com/nathaniel.chang
