## Get Package Information

### Description
The calls returns information for a package with the given package ID.

You can preview the output, which will display up to 100 lines, using the preview_url listed in the outputs of the response. 
View [Preview Job Output] (https://github.com/xplenty/xplenty-api-doc/blob/master/sections/preview-output.md) for details.

The details returned for the job are:

* **id** - the numeric package ID
* **name** - the name given to the package upon creation
* **description** - the description given to the package upon creation
* **variables** - package variables
* **owner_id** - the numeric user id of the package owner
* **created_at** - the date and time the "run" request was made
* **updated_at** - the date and time the job was last updated (occurs when package tasks are completed)
* **url** - the job resource URL

### Input Parameters
The **package ID** must be supplied at the end of the request URL.

### Request (Curl Call) Syntax
```shell
    curl -X GET -H "Accept: application/vnd.xplenty+json" -u <APIkey>: "https://api.xplenty.com/<accountID>/api/packages/<packageID>"
```

### Response Example
```json
{
    "id": 2373,
    "name": "AWS CloudFront Log Analysis",
    "description": "This package processes AWS CloudFront logs and extracts traffic information by time, geography and URIs",
    "variables": {},
    "owner_id": 8,
    "created_at": "2014-03-12T07:09:18Z",
    "updated_at": "2014-04-13T19:38:04Z",
    "url": "https://api.xplenty.com/xplenation/api/packages/2373"
}
```
