![Valotalive Logo](https://store.valotalive.com/img/valotalive_logo.png)
# Valotalive - My Content API v1



## Summary
Valotalive My Content API enables you to manage your My Content sources programmatically. 

## Enabling API access
1. Enable API Access in your My Content app (https://my-content.valota.live/): _Settings_ -> _API Access_. **API User Name** is used only as a sender for posts sent by your app.
1. Get **api_key** and **api_secret** from _API Access_. 



## Code Libraries

These libraries support all API endpoints. Save yourself some time and frustration and use them if possible. 

- [TBA - Javascript Library]
- [TBA - PHP Library]


## API Description

### Requests
- All requests __must__ have headers `x-api-key` and `x-api-hash`. `x-api-key` is `api_key`. `x-api-hash` is calculated individually for every request with request data and `api_secret`. See endpoints for exact calculation.
- RESTful Web service. Supports methods GET, POST and DELETE
- Throttling limit of 10 requests / min. Response `429 Too Many Requests` if exceeded. 

#### Payloads
- Payloads are delivered as form data for POST and DELETE requests and URL for GET requests. As all payloads are strings, the payloads of type JSON have to be encoded/stringified.  



### Responses
- Responses follow [HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes). (successful requests return `200 OK`) 
- Response body is stringified JSON.

### API Endpoints
- [My Content API](README.md)
  - [Edit a message [edit]](edit.md)  
  - [Post a message [post]](post.md)  
  - [List Messages [list]](list.md)  
  - [Get message [get]](get.md)  
  - [Restore a message [restore]](restore.md)  
  - [Archive a message [archive]](archive.md)  
  - [Delete a message [delete]](delete.md)  


