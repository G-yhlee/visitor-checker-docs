# 일렉트론-설치하기
```erlang
Manual Guide of 일렉트론-설치하기

Command 1 : 깃-시작하기 
g0 electron-app
Command 2 : 일렉트론-설치하기
npm init -y
npm i --save--dev electron electron-reload

INFO: 설치된 내용을 살펴보면 다음과 같다.

일렉트론 설치
npm i --save--dev electron electron-reload

=> 일렉트론 관련 라이브러리를 설치한다
```


## Client to Server JSON format
```js
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

<table style="height: 600px;" width="424">
<tr>
<td style="width: 139px;"><strong>NAME</strong></td>
<td style="width: 139px;"><strong>TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 139px;">client_id</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Any predefined text to specify client name</td>
</tr>
<tr>
<td style="width: 139px;">src</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Camera id ("0", "1", "2", ...) or video directory.</td>
</tr>
<tr>
<td style="width: 139px;">frames</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">List of base64 encoded strings, which is encoded from camera/video frames</td>
</tr>
<tr>
<td style="width: 139px;">edge_filter</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">"1" if use, "0" if not use. Use to filter faces which are collapse with edge of frame</td>
</tr>
<tr>
<td style="width: 139px;">eye_dist2min_size_ratio</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">(Threshold) The ratio between eyes distance and minimum size of face bounding box. Use to filter out unqualified face poses </td>
</tr>
<tr>
<td style="width: 139px;">yaw_thresh</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">Range of yaw angle to accept detected faces</td>
</tr>
<tr>
<td style="width: 139px;">pitch_thresh</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">Range of pitch angle to accept detected faces</td>
</tr>
<tr>
<td style="width: 139px;">clustering_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">The threshold value used in hierarchical clustering (Ward linkage)</td>
</tr>
<tr>
<td style="width: 139px;">known_people_conf_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Threshold value on confidence value to recognize visitor in known visitor database</td>
</tr>
<tr>
<td style="width: 139px;">unknown_people_conf_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Threshold value on cosine similarity value to recognize visitor in unknown visitors database </td>
</tr>
<tr>
<td style="width: 139px;">visit_cnt_gap</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">List of time values (hours- minutes - seconds) to specify the gap time for counting number of visitor 's visit times</td>
</tr>
</table>

<table style="height: 600px;" width="424">
<tr>
<td style="width: 139px;"><strong>NAME</strong></td>
<td style="width: 139px;"><strong>TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 139px;">client_id</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Any predefined text to specify client name</td>
</tr>
<tr>
<td style="width: 139px;">src</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Camera id ("0", "1", "2", ...) or video directory.</td>
</tr>
<tr>
<td style="width: 139px;">frames</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">List of base64 encoded strings, which is encoded from camera/video frames</td>
</tr>
<tr>
<td style="width: 139px;">edge_filter</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">"1" if use, "0" if not use. Use to filter faces which are collapse with edge of frame</td>
</tr>
<tr>
<td style="width: 139px;">eye_dist2min_size_ratio</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">(Threshold) The ratio between eyes distance and minimum size of face bounding box. Use to filter out unqualified face poses </td>
</tr>
<tr>
<td style="width: 139px;">yaw_thresh</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">Range of yaw angle to accept detected faces</td>
</tr>
<tr>
<td style="width: 139px;">pitch_thresh</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">Range of pitch angle to accept detected faces</td>
</tr>
<tr>
<td style="width: 139px;">clustering_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">The threshold value used in hierarchical clustering (Ward linkage)</td>
</tr>
<tr>
<td style="width: 139px;">known_people_conf_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Threshold value on confidence value to recognize visitor in known visitor database</td>
</tr>
<tr>
<td style="width: 139px;">unknown_people_conf_thresh</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Threshold value on cosine similarity value to recognize visitor in unknown visitors database </td>
</tr>
<tr>
<td style="width: 139px;">visit_cnt_gap</td>
<td style="width: 139px;">list of strings</td>
<td style="width: 750px;">List of time values (hours- minutes - seconds) to specify the gap time for counting number of visitor 's visit times</td>
</tr>
</table>
