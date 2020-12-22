## `DELETE /delete/{message_id}` Delete a message
Delete a message. Deleted messages cannot be recovered  
### Hash  
>sha256("api_secret" + "message_id");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__message_id__ `required` `int`| __Message ID__: Identifier of the message| `1827` `51`  | `min: 0`  
   
   
> _Example endpoints_  
> https://my-api.valota.live/delete/128  
> https://my-api.valota.live/delete/1827  
  
### Return value
  

#### examples
```json
{
    "message": "Message 123 was deleted."
}
```



#### My Content API
- [My Content API](README.md)
  - [Edit a message [edit]](edit.md)  
  - [Post a message [post]](post.md)  
  - [List Messages [list]](list.md)  
  - [Get message [get]](get.md)  
  - [Restore a message [restore]](restore.md)  
  - [Archive a message [archive]](archive.md)  
  - [Delete a message [delete]](delete.md)  
