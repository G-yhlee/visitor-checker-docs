
## Server to Client
```erlang
Manual Guide of Server to Client

INFO : ...

```

## Server to Client JSON format
```js
{
    "result": 0,
    "reqid": "40137",
    "output": {
        "items": [
            {
                "src": "0",
                "num_people": "3",
                "people_names": ["Pham_Tung_Lam", "visitor_001", "visitor_002"],
                "known_samples": [
                    {
                        "name": "Pham_Tung_Lam",
                        "img": "Base64EncodedString",
                        "bboxes":[
                            "x1 y1 x2 y2 frame_id"
                        ],
                        "prob": "0.89",
                        "visit_times": "VisitTimesToday VisitTimesThisWeek",
                        "last_visit": "LastVisitDescription_DetailTimestamp"
                    } 
                ],
                "stranger_samples": [
                    {
                        "name": "visitor_001_M",
                        "img": "Base64EncodedString",
                        "bboxes":[
                            "x1 y1 x2 y2 frame_id"
                        ],
                        "prob": "0.93",
                        "visit_times": "VisitTimesToday VisitTimesThisWeek",
                        "last_visit": "LastVisitDescription_DetailTimestamp" 
                    },
                    {
                        "name": "visitor_002_M",
                        "img": "Base64EncodedString",
                        "bboxes":[
                            "x1 y1 x2 y2 frame_id"
                        ],
                        "prob": "0.93",
                        "visit_times": "VisitTimesToday VisitTimesThisWeek",
                        "last_visit": "LastVisitDescription_DetailTimestamp" 
                    }
                ]
            }
        ]
    }
}
```



<table>
<tr>
<td>NAME</td>
<td>TYPE</td>
<td>DESCRIPTION</td>
</tr>
<tr>
<td>src</td>
<td>string</td>
<td>Camera id or video directory – client side</td>
</tr>
<tr>
<td>num_people</td>
<td>string</td>
<td>Number of detected people in frames sequence</td>
</tr>
<tr>
<td>people_names</td>
<td>list of string</td>
<td>List of known visitors name and unknown visitors id</td>
</tr>
<tr>
<td>known_samples</td>
<td>list of dictionaries</td>
<td>List of detail information on detected known visitors</td>
</tr>
<tr>
<td>stranger_samples</td>
<td>list of dictionaries</td>
<td>List of summarized information on visitors who visit today for updating the record file in client side</td>
</tr>
</table>




## Known/Unknown Visitor JSON sample

```erlang
Manual Guide of Known/Unknown Visitor JSON Format

INFO : 등록된 사용자(Known) 등록되지 않은 사용자(Unknown) 의 경우 각각의 Json data 포맷은 다음과 같습니다. 등록되지 않은 사용자의 경우, 자동생성된 아이디로 구분짓습니다.

```


```js
{
    "name": "Pham_Tung_Lam",
    "bboxes":[
        "x1 y1 x2 y2 frame_id"
    ],
    "prob": "0.89"
    "img": "Base64EncodedString",
    "visit_times": "2 17",
    "last_visit": "5 hours ago_20210318-155328"
}
```
```js
{
    "name": "visitor_001_M",
    "bboxes":[
        "x1 y1 x2 y2 frame_id"
    ],
    "prob": "0.93",
    "img": "Base64EncodedString",
    "visit_times": "2 17",
    "last_visit": "5 hours ago_20210318-155328" 
}
```

<table >
<tr>
<td><strong>NAME</strong></td>
<td><strong>TYPE</strong></td>
<td><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td>name</td>
<td>string</td>
<td style="width: 750px;">Visitor ‘s name or auto-generated id</td>
</tr>
<tr>
<td>img</td>
<td>string</td>
<td>Sample face with size = 160 x 160, which is encoded to string using base64 encoding method</td>
</tr>
<tr>
<td>bboxes</td>
<td>list of string</td>
<td>List of information of processed bounding box on visitor ‘s face. frame_id is the index of frame within N frames received from client, start from 0 to N-1.</td>
</tr>
<tr>
<td>prob</td>
<td>string</td>
<td>Probability of prediction. Value is float between 0 and 1.</td>
</tr>
<tr>
<td>visit_times</td>
<td>string</td>
<td>Number of visit times today and number of visit times this week, separated by one space-unit</td>
</tr>
<tr>
<td>last_visit</td>
<td>string</td>
<td>Human-readable description for last visit timestamp with detail timestamp, separated by “_”</td>
</tr>
</table>


<!-- <img src="Facial_bbox.jpg" alt="Detected face with bounding box" style="width:400px;" class="center"> -->
<!-- <head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
</head> -->
