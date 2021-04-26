
## Server to Client
```erlang
Manual Guide of Server to Client

INFO : 서버에서 클라이언트로 보내는 JSON api 포맷입니다.
등록된 사용자의 경우 known_samples 에 값이 담겨져 전송되고,
등록되지 않은 사용자의 경우, stranger_samples에 값이 담겨져 전송됩니다.

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



