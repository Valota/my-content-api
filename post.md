## `POST /post` Post a message
Post a message. Message will only be accepted if it contains at least title, message or media.  
### Hash  
>sha256("api_secret" + "md5_for_file(media)" + "title" + "message");
  
  
__Payloads__  
Payload | Name and description | example values | details  
----|----|----|----  
__title__ `string`| __Title__: Title for the post. Plain string. No html tags are allowed.| `Example title` `See a drone swarm replant a burnt forest`  | `maxLength: 512`  
__message__ `string`| __Message__: Post's message. HTML tags &lt;b&gt;&lt;strong&gt;&lt;div&gt;&lt;i&gt;&lt;u&gt;&lt;strike&gt;&lt;s&gt;&lt;del&gt;&lt;ul&gt;&lt;ol&gt;&lt;li&gt;&lt;br&gt;&lt;em&gt;&lt;code&gt; are allowed.| `Centuries ago, a prestigious Islamic library brought Arabic numerals to the world. Though the library long since disappeared, its mathematical revolution changed our world.` `<strong>The Gatsby</strong> is one of <em>Cape Town</em>'s most famous sandwiches. But there’s more to the takeaway than simply being a solid hangover fix.`  |  
__schedule__ `json`| __Schedule__: Show this post only acording to given schedules. Array of from and to objects with from and to being timestamps as seconds from epoch. | [See here](#schedule-example)|  
__display_time__ `int`| __Display time__: How long should this post be displayed. Seconds.| `12` `8`  | `min: 4` `max: 30`  
__pages__ `json`| __Page settings__: JSON encoded array for page settings if using multi page PDF. First page number is 1. You can only modify visibility and display time for pages. By default all of the pages are visible and have the default display time.|[See here](#pages-example)  |  
__media__ `file`| __Media__: Medial file. Supports image, video and pdf. Recommended jpg, png, svg or avi, mp4, webm (h.264 or VP8 compressed) video. Other file formats might also work.|  |  
__~~duration_from~~__ `int`| __[Deprecated] ~~Duration from~~__: Show this post only from this timestamp. Seconds from Epoch| `1606367122` `1611822480`  |  
__~~duration_to~~__ `int`| __[Deprecated] ~~Duration to~~__: Show this post only until this timestamp. Seconds from Epoch| `1606397180` `1613897380`  |  
   
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

#### schedule example

 ```json
[
  {
    "from": 1735693261,
    "to": 1735729871
  },
  {
    "from": 2000000000,
    "to": 2147483647
  }  
]
```
   
> _Example endpoint_  
> https://my-api.valota.live/v1/post  
  
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
  - [Get basic information [information]](information.md)  
  - [Restore a message [restore]](restore.md)  
  - [Archive a message [archive]](archive.md)  
  - [Delete a message [delete]](delete.md)

 ## php example
 ```php
<?php

$API_SECRET = getenv('VALOTA_SECRET');

$API_KEY = getenv('VALOTA_KEY');

if (empty($API_SECRET) || empty($API_KEY)) {
    die('could not read key and or secret from environment variables VALOTA_SECRET and VALOTA_KEY' . PHP_EOL);
}

$title = 'Example title See a drone swarm replant a burnt forest';

$message = 'Centuries ago, a prestigious Islamic library brought Arabic numerals to the world. Though the library long since disappeared, its mathematical revolution changed our world. <strong>The Gatsby</strong> is one of <em>Cape Town</em>\'s most famous sandwiches. But there’s more to the takeaway than simply being a solid hangover fix.';

$file = 'file.jpg';

if (!file_exists($file)) {
    die('file not found ' . $file . PHP_EOL);
}

$url = 'https://my-api.valota.live/v1/post';

$ch = curl_init($url);
$cFile = curl_file_create($file);
$post = ['title' => $title, 'message' => $message, 'media' => $cFile];
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, $post);
curl_setopt($ch, CURLOPT_HTTPHEADER,
            [ 'Content-type: multipart/form-data',
              'x-api-key: ' . $API_KEY,
              'x-api-hash: ' . hash('sha256', $API_SECRET . md5_file($file) . $title . $message)
              ]
            );
$result = curl_exec($ch);

if (curl_getinfo($ch, CURLINFO_HTTP_CODE) !== 200) {
    die('failed: ' . curl_error($ch) . ' ' . $result . PHP_EOL);
}
curl_close($ch);
$obj = json_decode($result);

if (!is_object($obj)) {
    die('could not parse return value ' . $result . PHP_EOL);
}

if (!property_exists($obj, 'message_id')) {
    die('could not find message id from return value ' . $result . PHP_EOL);
}
echo 'message id: ' . $obj->message_id . PHP_EOL;
```
