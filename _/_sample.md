
# DataBase
```erlang
Manual Guide of DataBase to Server

INFO : 데이터베이스에서 서버의 요청에 따라 필요한 정보를 제공해 줍니다. (...작성 대기 중 ...)
```
## DataBase to Server JSON format
```json
{
  "none": "..."
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
