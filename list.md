## `GET /list[/page/{page}]` `GET /list/archive/{archive}[/page/{page}]`  List Messages
Get list of messages.  
### Hash  
>sha256("api_secret" + "api_key");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__archive__ `int`| __Archived messages__: List archived messages| `1` `0`  | `min: 0` `Default: 0`  
__page__ `int`| __Page nro__: Page number. Starts at 0. 100 messages per page.| `0` `1` `2` `25`  | `min: 0` `Default: 0`  
   
   
> _Example endpoints_  
> https://my-api.valota.live/v1/list  
> https://my-api.valota.live/v1/list/archive/1  
> https://my-api.valota.live/v1/list/page/0  
> https://my-api.valota.live/v1/list/archive/1/page/1  
  
### Return value
Returns an array of message objects. See get message for examples.  

#### examples
```json
{
    "total": 123,
    "messages": [
        "[Array of message objects. See get a message endpoint.]"
    ]
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
