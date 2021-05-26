#### C2D ::  time condition
```js
{
    "reqid": "gridonesurveillance",
    "input": {
        "items": [
            {
                "query_type": "select",
                "params": {
                    "keys": [
                        "DISTINCT(visitor_id)",
                        "timestamp"
                    ],
                    "table_name": "door_client_uvdb",
                    "conditions": [
                        "timestamp>'20210525-173500'",
                        "timestamp<'20210525-174000'"
                    ]
                }
            }
        ]
    }
}

```