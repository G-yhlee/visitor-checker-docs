
#### Example query
```js
// example
SELECT col1, col2 FROM db WHERE {컬럼명,비교연산자,비교컬럼명,표현식..} LIKE 검색 ORDER BY timestamp ASC

// Retrieve with { id }
SELECT visitor_id, img_str, timestamp FROM new_test_v1_uvdb WHERE visitor_id LIKE '%_M' ORDER BY timestamp ASC

// Retrieve with { timestamp }
SELECT visitor_id, img_str, timestamp FROM new_test_v1_uvdb WHERE timestamp LIKE '20210427-%' ORDER BY timestamp ASC

// Retrieve with { id , timestamp }
SELECT img_str, timestamp FROM new_test_v1_uvdb WHERE visitor_id="visitor_000_M" AND timestamp LIKE '20210427-%' ORDER BY timestamp ASC

// Retrieve with { id } |> unique
SELECT DISTINCT(visitor_id) FROM new_test_v1_uvdb WHERE visitor_id LIKE '%_M'

```



```js
// sudo code ... dont need to read this 
// {visitor_id, img_str, timestamp} = new_test_v1_uvdb.{visitor_id ~ '%_M' }
// {visitor_id, img_str, timestamp} = new_test_v1_uvdb.{timestamp ~ '20210427-%'}
// {visitor_id, img_str, timestamp} = new_test_v1_uvdb.{visitor_id =='visitor_000_M' , timestamp ~ '20210427-%' }
```
