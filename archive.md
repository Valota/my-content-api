## `POST /archive` Archive a message
Archive a message from the gallery.  
### Hash  
>sha256("api_secret" + "message_id");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__message_id__ `required` `int`| __Message ID__: Identifier of the message| `1827` `51`  | `min: 0`  
   
   
> _Example endpoint_  
> https://my-api.valota.live/v1/archive  
  
### Return value
  

#### examples
```json
{
    "message": "Message 123 has been archived."
}
```
```json
{
    "message": "Didn't do anything. Message 123 was already archived."
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
