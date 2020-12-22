## `GET /get/{message_id}` Get message
Get one message  
### Hash  
>sha256("api_secret" + "message_id");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__message_id__ `required` `int`| __Message ID__: Identifier of the message| `1827` `51`  | `min: 0`  
   
   
> _Example endpoints_  
> https://my-api.valota.live/get/12  
> https://my-api.valota.live/get/271  
  
### Return value
  

#### examples
```json
{
    "id": 144,
    "name": "Jukka",
    "email": "email@address.com",
    "title": null,
    "message": "",
    "conf": {
        "mediaType": "video"
    },
    "date": 1603967167,
    "media": "2020102911260747c6db0b2d9145e52a350c28fb9bd88d.mp4",
    "archived": true
}
```
```json
{
    "id": 130,
    "name": "Jukka",
    "email": "email@address.com",
    "title": "Title",
    "message": "Message<div><i>Italic<\/i><\/div><div><b>Bold<\/b><\/div><div><b><i>BoldItalic<\/i><\/b><\/div><div><u>Underline<\/u><\/div><div><strike>Strikehthrough<\/strike><\/div><div><ol><li>ordered List<\/li><li>2<\/li><\/ol><div><ul><li>unordered list<\/li><li>2<\/li><\/ul><div>Update<\/div><\/div><\/div>",
    "conf": [],
    "date": 1596096766,
    "media": null,
    "archived": true
}
```
```json
{
    "id": 85,
    "name": "Jukka",
    "email": "email@address.com",
    "title": null,
    "message": "Message 1.8.2018",
    "conf": {
        "mediaType": "image",
        "display_time": 5
    },
    "date": 1543925516,
    "media": "201804111606443dc802f6b289212f55e965b0864d2845.jpeg",
    "archived": true
}
```
```json
{
    "id": 60,
    "name": "Jukka",
    "email": "email@address.com",
    "title": null,
    "message": "",
    "conf": [],
    "date": 1507922604,
    "archived": true,
    "pages": [
        {
            "id": 0,
            "media": "0GSrVvWPxtZnOOfLtScHdPxk5vkPJPZJvSarn7hVBgip4xayqmfDcNYhii6176LD.1.svg",
            "active": true,
            "display_time": 4
        },
        {
            "id": 1,
            "media": "0GSrVvWPxtZnOOfLtScHdPxk5vkPJPZJvSarn7hVBgip4xayqmfDcNYhii6176LD.2.svg",
            "active": false,
            "media_type": "image",
            "display_time": 5
        },
        {
            "id": 2,
            "media": "0GSrVvWPxtZnOOfLtScHdPxk5vkPJPZJvSarn7hVBgip4xayqmfDcNYhii6176LD.3.svg",
            "active": true,
            "media_type": "image",
            "display_time": 6
        },
        {
            "id": 3,
            "media": "0GSrVvWPxtZnOOfLtScHdPxk5vkPJPZJvSarn7hVBgip4xayqmfDcNYhii6176LD.4.svg",
            "active": false,
            "media_type": "image",
            "display_time": 17
        }
    ]
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
