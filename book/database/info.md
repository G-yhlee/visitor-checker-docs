
## connect info
```js
{
    "user": "root",
    "password": "gridone",
    "host": "docker.gridone.net"
    "port": 3306,
    "database": "visitorChecker"
}
```

## Nodejs example
```js
import mariadb from 'mariadb';
const pool = mariadb.createPool({
  "user": 'root',
  "password": 'gridone',
  "host": "docker.gridone.net",
  "port": 3306,
  "database": "visitorChecker",
  connectionLimit: 5
});

async function asyncFunction() {
  let conn;
  try {
	conn = await pool.getConnection();
	const mask = await conn.query("SELECT visitor_id, timestamp FROM new_test_v1_uvdb WHERE visitor_id LIKE '%_M' ORDER BY timestamp ASC");
  log(mask[0])
  } catch (err) {
	throw err;
  } finally {
	if (conn) conn.release(); //release to pool
  }
}

asyncFunction()
```

<!-- ```js
const col = ["visitor_id" , "timestamp" , "img_str" ]
const db = ["new_test_v1_uvdb"]
const where = ["visitor_id" ]
const like = { masked: "%_M" }
const order = [ "timestamp ASC" ]
``` -->