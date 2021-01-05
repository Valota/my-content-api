## `POST /edit` Edit a message
Edit a message. Only edits the fields that you supply. You cannot change media. Please send a new post if you want to use a new media.  
### Hash  
>sha256("api_secret" + "message_id");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__message_id__ `required` `int`| __Message's id__: Message's identifier. You can this id when you create a post or from listing messages. | `172` `19273`  | `min: 1`  
__title__ `string`| __Title__: Title for the post. Plain string. No html tags are allowed.| `Example title` `See a drone swarm replant a burnt forest`  | `maxLength: 512`  
__message__ `string`| __Message__: Post's message. HTML tags &lt;b&gt;&lt;strong&gt;&lt;div&gt;&lt;i&gt;&lt;u&gt;&lt;strike&gt;&lt;s&gt;&lt;del&gt;&lt;ul&gt;&lt;ol&gt;&lt;li&gt;&lt;br&gt;&lt;em&gt;&lt;code&gt; are allowed.| `Centuries ago, a prestigious Islamic library brought Arabic numerals to the world. Though the library long since disappeared, its mathematical revolution changed our world.` `<strong>The Gatsby</strong> is one of <em>Cape Town</em>'s most famous sandwiches. But there’s more to the takeaway than simply being a solid hangover fix.`  |  
__duration_from__ `int`| __Duration from__: Show this post only from this timestamp. Seconds from Epoch| `1606367122` `1611822480`  |  
__duration_to__ `int`| __Duration to__: Show this post only until this timestamp. Seconds from Epoch| `1606397180` `1613897380`  |  
__display_time__ `int`| __Display time__: How long should this post be displayed. Seconds. Multi page PDF page settings override this. Set 0 to use default value.| `12` `8`  | `min: 0` `max: 30`  
__pages__ `json`| __Page settings__: JSON encoded array for page settings if using multipage PDF. First page id of the message is always 0. |[See here](#pages-example)  |  
   
#### pages example
 ```json
[
    {
        "page_id": 0,
        "display_time": 10,
        "visible": true
    },
    {
        "page_id": 18200,
        "display_time": 7,
        "visible": true
    },
    {
        "page_id": 18201,
        "visible": false
    },
    {
        "page_id": 18203,
        "display_time": 9
    }
]
```
   
> _Example endpoint_  
> https://my-api.valota.live/v1/edit  
  
### Return value
  

#### examples
```json
{
    "message": "Message was updated."
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
