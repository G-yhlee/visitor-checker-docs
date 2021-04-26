# Client to Server
```erlang
Manual Guide of Client to Server

INFO : 클라이언트에서 서버로 보내는 JSON api 포맷입니다.
클라이언트에서 3초당 20장의 img data를 수집하여 서버에 전송합니다.
여기서 사진 정보는 frames에 배열형태로 담아서 보내게 됩니다.
```
## Client to Server JSON format
```json
{
    "reqid": "40137",
    "input": {
        "items": [
            {
                "client_id": "testing_client_001",
                "src": "0",
                "frames": [
                    "Base64EncodedString_frame_no1",
                    "Base64EncodedString_frame_no2",
                    "Base64EncodedString_frame_no3",
                    ...
                    "Base64EncodedString_frame_no20",
                ],
                "edge_filter": "1",
                "eye_dist2min_size_ratio": "0.35",
                "yaw_thresh": [
                    "-28",
                    "28"
                ],
                "pitch_thresh": [
                    "-15",
                    "15"
                ],
                "clustering_thresh": "0.95",
                "known_people_conf_thresh": "0.75",
                "unknown_people_conf_thresh": "0.8",
                "visit_cnt_gap": [
                    "0",
                    "0",
                    "15"
                ]
            }
        ]
    }
}
```

<table >
<tr>
<td >NAME</td>
<td >TYPE</td>
<td >DESCRIPTION</td>
</tr>
<tr>
<td >client_id</td>
<td >string</td>
<td >Any predefined text to specify client name</td>
</tr>
<tr>
<td >src</td>
<td >string</td>
<td >Camera id ("0", "1", "2", ...) or video directory.</td>
</tr>
<tr>
<td >frames</td>
<td >list of strings</td>
<td >List of base64 encoded strings, which is encoded from camera/video frames</td>
</tr>
<tr>
<td >edge_filter</td>
<td >string</td>
<td >"1" if use, "0" if not use. Use to filter faces which are collapse with edge of frame</td>
</tr>
<tr>
<td >eye_dist2min_size_ratio</td>
<td >string</td>
<td >(Threshold) The ratio between eyes distance and minimum size of face bounding box. Use to filter out unqualified face poses </td>
</tr>
<tr>
<td >yaw_thresh</td>
<td >list of strings</td>
<td >Range of yaw angle to accept detected faces</td>
</tr>
<tr>
<td >pitch_thresh</td>
<td >list of strings</td>
<td >Range of pitch angle to accept detected faces</td>
</tr>
<tr>
<td >clustering_thresh</td>
<td >string</td>
<td >The threshold value used in hierarchical clustering (Ward linkage)</td>
</tr>
<tr>
<td >known_people_conf_thresh</td>
<td >string</td>
<td >Threshold value on confidence value to recognize visitor in known visitor database</td>
</tr>
<tr>
<td >unknown_people_conf_thresh</td>
<td >string</td>
<td >Threshold value on cosine similarity value to recognize visitor in unknown visitors database </td>
</tr>
<tr>
<td >visit_cnt_gap</td>
<td >list of strings</td>
<td >List of time values (hours- minutes - seconds) to specify the gap time for counting number of visitor 's visit times</td>
</tr>
</table>
