# Useful DHIS2 API requests

This is a list of common API requests. API requests can be executed in a web browser by accessing a URL. The format of the URL is always the same:

`<server_url>/api/<request>`

The field `server_url` depends on the requested server. For example, it could be `http://localhost:8989/dhis` to access a local instance, or `https://hmisocba.msf.es` to access the HMISOCBA production server.

The following sections deal only with the `request` field of the URL.

## Data Elements
### List of dataelements with some information (Tally Sheet)
List all dataelements

`/dataElements?paging=false&fields=id,code,name,formName,description,categoryCombo[name],dataElementGroups[name],dataSets[name,code]`

## Indicators
### List indicators with all fields
List all the indicators in the system with description, numerator, denominator and factor (unit, per houndred, per thousand, etc).

`/indicators?paging=false&fields=id,code,name,description,numeratorDescription,denominatorDescription,indicatorType[name],indicatorGroups[name]`

## Filters
You can use any field to filter a request. To apply a filter you only have to append it to the URL.

For example, to look for an indicator with code HIV010 you have to append the following to the url:

`&filter=code:eq:HIV010`

the whole request could be for example:

`/indicators?paging=false&fields=id,code,name,description&filter=code:eq:HIV010`

If you want to filter by a field, but you don't know exactly the value of the field and you want to do a search, you can use the LIKE operator and include a key word. For example, to look for all the indicator that contains the word Malaria in their name, you can use the filter:

`filter=name:like:malaria`

