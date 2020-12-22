## `POST /post` Post a message
Post a message. Message will only be accepted if it contains at least title, message or media.  
### Hash  
>sha256("api_secret" + "md5_for_file(media)" + "title" + "message");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__title__ `string`| __Title__: Title for the post. Plain string. No html tags are allowed.| `Example title` `See a drone swarm replant a burnt forest`  | `maxLength: 512`  
__message__ `string`| __Message__: Post's message. HTML tags &lt;b&gt;&lt;strong&gt;&lt;div&gt;&lt;i&gt;&lt;u&gt;&lt;strike&gt;&lt;s&gt;&lt;del&gt;&lt;ul&gt;&lt;ol&gt;&lt;li&gt;&lt;br&gt;&lt;em&gt;&lt;code&gt; are allowed.| `Centuries ago, a prestigious Islamic library brought Arabic numerals to the world. Though the library long since disappeared, its mathematical revolution changed our world.` `<strong>The Gatsby</strong> is one of <em>Cape Town</em>'s most famous sandwiches. But there’s more to the takeaway than simply being a solid hangover fix.`  |  
__duration_from__ `int`| __Duration from__: Show this post only from this timestamp. Seconds from Epoch| `1606367122` `1611822480`  |  
__duration_to__ `int`| __Duration to__: Show this post only until this timestamp. Seconds from Epoch| `1606397180` `1613897380`  |  
__display_time__ `int`| __Display time__: How long should this post be displayed. Seconds.| `12` `8`  | `min: 4` `max: 30`  
__pages__ `json`| __Page settings__: JSON encoded array for page settings if using multi page PDF. First page number is 1. You can only modify visibility and display time for pages. By default all of the pages are visible and have the default display time.|[See here](#pages-example)  |  
__media__ `file`| __Media__: Medial file. Supports image, video and pdf. Recommended jpg, png, svg or avi, mp4, webm (h.264 or VP8 compressed) video. Other file formats might also work.|  |  
   
#### pages example
 ```json
[
    {
        "page": 1,
        "display_time": 10,
        "visible": true
    },
    {
        "page": 2,
        "display_time": 8,
        "visible": true
    },
    {
        "page": 8,
        "visible": false
    },
    {
        "page": 12,
        "display_time": 5
    }
]
```
   
> _Example endpoint_  
> https://my-api.valota.live/post  
  
### Return value
Returns message_id of the created message.  

#### examples
```json
{
    "message_id": 123
}
```
```json
{
    "message_id": 987
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
