## `GET /information` Get basic information
Returns an array containing My Content's name and other basic information.  
### Hash  
>sha256("api_secret" + "api_key");
   
   
> _Example endpoint_  
> https://my-api.valota.live/v1/information  
  
### Return value
  

#### examples
```json
{
    "name": "Wall Name",
    "category": "Category name",
    "type": "My Content or Wall",
    "color": "#ff0000",
    "company": "Company Name",
    "max_filesize": "330 MB"
}
```



#### My Content API
- [My Content API](README.md)
  - [Edit a message [edit]](edit.md)  
  - [Post a message [post]](post.md)  
  - [List Messages [list]](list.md)  
  - [Get message [get]](get.md)  
  - [Get basic information [information]](information.md)  
  - [Restore a message [restore]](restore.md)  
  - [Archive a message [archive]](archive.md)  
  - [Delete a message [delete]](delete.md)  
