# Wake county restaurant inspections API

## JSON API

This RESTful API follows the [jsonapi](http://jsonapi.org) specification. Please refer to the [specification](http://jsonapi.org/format/) for details on how to query the API and how the response is structured.

## Example queries

### Restaurant geo-search:

* `curl -g 'localhost:8888/api/restaurants?filter[coords][0]=-78.808524&filter[coords][1]=35.619695'`
* `curl -g 'localhost:8888/api/restaurants?filter[coords][0]=-78.808524&filter[coords][1]=35.619695&filter[radius]=20'`

### Full-text search on restaurant name:
	
* `curl 'localhost:8888/api/restaurants?filter[query]=fainting'`

### Date range filtering on inspections:

* `curl -g 'localhost:8888/api/inspections?filter[dateRange][0]=1358294400000&filter[dateRange][1]=1358467200000'`

### Inspection geo-search:

* `curl -g 'localhost:8888/api/inspections?filter[coords][0]=-78.808524&filter[coords][1]=35.619695'`

### Filtering on inspection type

* `curl -g 'localhost:8888/api/inspections?filter[inspectionTypes][0]=routine'`

### Single restaurant

* `curl 'localhost:8888/api/restaurants/155F3C7A-7D26-5310-B208FB954BE96976'`

## Basic response format

```
{
	"meta": {
		"total": 123 // Total number of documents matched
	},
	"data": {
		// Primary data returned
	},
	"included": {
		// The actual documents from any relationships in the primary data returned
	},
	"links": {
		// If pagination necessary
		"prev": "<url to get previous page>",
		"next": "<url to get next page>"
	}
}
```