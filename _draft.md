
## MariaDB communicating
#### Information for connecting to MariaDB
```js
{
    "user": 'root',
    "password": 'gridone',
    "host": "docker.gridone.net"
    "port": 3306,
    "database": "visitorChecker"
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

#### Unknown Visitor DataTable information - [client_id]_summary
<table style= width="424">
<tr>
<td style="width: 139px;"><strong>KEY NAME</strong></td>
<td style="width: 139px;"><strong>DATA TYPE</strong></td>
<td style="width: 750px;"><strong>DESCRIPTION</strong></td>
</tr>
<tr>
<td style="width: 139px;">visitor_id</td>
<td style="width: 139px;">string</td>
<td style="width: 750px;">Unknown visitor id. "M" stands for masked-face and "N" stands for no masked-face</td>
</tr>
<tr>
<td style="width: 139px;">sample_image</td>
<td style="width: 139px;">TEXT</td>
<td style="width: 750px;">Sample face with size = 160 x 160, which is encoded to string using base64 encoding method</td>
</tr>
<tr>
<td style="width: 139px;">centroid</td>
<td style="width: 139px;">list of string</td>
<td style="width: 750px;">The centroid of 512D embedding features with same visitor_id in [client_id]_uvdb table. Store as text with SPACE is the delimited symbol</td>
</tr>
</table>

#### Known Visitor DataTable Information - [client_id]_kv_manual
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

#### Example query
###### Retrieve all masked visitors data with client_id = new_test_v1
```js
SELECT visitor_id, img_str, timestamp FROM new_test_v1_uvdb WHERE visitor_id LIKE '%_M' ORDER BY timestamp ASC
```
###### Retrieve visitors data from specific day
```js
SELECT visitor_id, img_str, timestamp FROM new_test_v1_uvdb WHERE timestamp LIKE '20210427-%' ORDER BY timestamp ASC
```
###### Retrieve specific visitor data from specific day
```js
SELECT img_str, timestamp FROM new_test_v1_uvdb WHERE visitor_id="visitor_000_M" AND timestamp LIKE '20210427-%' ORDER BY timestamp ASC
```
###### Retrieve list of unique masked visitor_id from database
```js
SELECT DISTINCT(visitor_id) FROM new_test_v1_uvdb WHERE visitor_id LIKE '%_M'
``` 
###### Note: visit_times today and this week need to be calculate in client side based on visit_gap_time and retrieved timestamps from specific days

<img src="visit_times_count_1.jpg" alt="Visit times counting concept" style="width:600px;" class="center">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
</head>

```js
```

<img src="visit_times_count_2.jpg" alt="Visit times counting concept" style="width:600px;" class="center">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
</head>

```js
```

###### Create known visitor table
```js
CREATE TABLE IF NOT EXISTS new_test_v1_kv_manual (visitor_id VARCHAR(50),img_str TEXT)
```

###### Manually add known visitor information to table
```js
INSERT INTO new_test_v1_kv_manual (visitor_id,img_str) VALUES ("Pham_Tung_Lam", "Base64EncodedString")
```