```
lastupdate:: 21/05/26

```

#### sql query example
```js
`query_type` `keys` FROM `table_name` WHERE `conditions`
```

#### summary
```js
table_name = {
   "[client_id]_uvdb": " All information collected " ,
   "[client_id]_predicted": "Combined real-time information of kvdb and uvdb  " ,
   "[client_id]_summary": "Summary information " ,
   "[client_id]_kvdb": "Information updated by the user" ,
}

keys = {
   "[client_id]_uvdb"      : {idx,visitor_id,img_str,centroid,timestamp}
   "[client_id]_predicted" : {visitor_id,img_str,timestamp},
   "[client_id]_summary" : {visitor_id,sample_image,visit_cnt_1,visit_cnt_7},
   "[client_id]_kvdb" : {visitor_id,img_str},
}

where = {

}

```
#### Unknown Visitor DataTable information - [client_id]_uvdb
<table style= width="424">
<tr>
<td style="width: 150px;"><strong>KEY NAME</strong></td>
<td style="width: 300px;"><strong>DATA TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 300px;">idx</td>
<td style="width: 300px;">INT</td>
<td style="width: 750px;">The index of face image within corresponding subset of database (masked or unmasked subset), based on ascending order of timestamp. Start from 0.</td>
</tr>
<tr>
<td style="width: 300px;">visitor_id</td>
<td style="width: 300px;">VARCHAR(50)</td>
<td style="width: 750px;">Unknown visitor id. "M" stands for masked-face and "N" stands for no masked-face</td>
</tr>
<tr>
<td style="width: 300px;">img_str</td>
<td style="width: 300px;">TEXT</td>
<td style="width: 750px;">Face image (160x160) which is encode to string using Base64Encoding.</td>
</tr>
<tr>
<td style="width: 139px;">centroid</td>
<td style="width: 139px;">TEXT</td>
<td style="width: 750px;">The 512D embedding feature of face image. Store as text with SPACE is the delimited symbol</td>
</tr>
<tr>
<td style="width: 139px;">timestamp</td>
<td style="width: 139px;">VARCHAR(50)</td>
<td style="width: 750px;">The timestamp of each face image in format "YYYYMMDD-HHMMSS"</td>
</tr>
</table>

#### Unknown Visitor DataTable information - [client_id]_predicted
<table style= width="424">
<tr>
<td style="width: 139px;"><strong>KEY NAME</strong></td>
<td style="width: 139px;"><strong>DATA TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 139px;">visitor_id</td>
<td style="width: 139px;">VARCHAR(50)</td>
<td style="width: 750px;">Known or Unknown visitor id. For unknown visitor case, "M" stands for masked-face and "N" stands for no masked-face</td>
</tr>
<tr>
<td style="width: 139px;">img_str</td>
<td style="width: 139px;">TEXT</td>
<td style="width: 750px;">Face image (160x160) which is encode to string using Base64Encoding.</td>
</tr>
<tr>
<td style="width: 139px;">timestamp</td>
<td style="width: 139px;">VARCHAR(50)</td>
<td style="width: 750px;">The timestamp of each face image in format "YYYYMMDD-HHMMSS</td>
</tr>
</table>

#### Unknown Visitor DataTable information - [client_id]_summary
<table style= width="424">
<tr>
<td style="width: 139px;"><strong>KEY NAME</strong></td>
<td style="width: 139px;"><strong>DATA TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 139px;">visitor_id</td>
<td style="width: 139px;">VARCHAR(50)</td>
<td style="width: 750px;">Unknown visitor id. "M" stands for masked-face and "N" stands for no masked-face</td>
</tr>
<tr>
<td style="width: 139px;">sample_image</td>
<td style="width: 139px;">TEXT</td>
<td style="width: 750px;">Sample face with size = 160 x 160, which is encoded to string using base64 encoding method</td>
</tr>
<tr>
<td style="width: 139px;">visit_cnt_1</td>
<td style="width: 139px;">INT</td>
<td style="width: 750px;">Number of visit times within today</td>
</tr>
<tr>
<td style="width: 139px;">visit_cnt_7</td>
<td style="width: 139px;">INT</td>
<td style="width: 750px;">Number of visit times within nearest 7 days (this week)</td>
</tr>
</table>

#### Known Visitor DataTable Information - [client_id]_kvdb
<table style= width="424">
<tr>
<td style="width: 139px;">visitor_id</td>
<td style="width: 139px;">VARCHAR(50)</td>
<td style="width: 750px;">Known visitor id.</td>
</tr>
<tr>
<td style="width: 139px;">img_str</td>
<td style="width: 139px;">TEXT</td>
<td style="width: 750px;">Face image (160x160) which is encode to string using Base64Encoding.</td>
</tr>
</table>
