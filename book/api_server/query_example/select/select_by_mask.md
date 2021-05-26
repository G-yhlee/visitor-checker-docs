#### C2D :: select by mask
```js
{
    "reqid": "gridonesurveillance",
    "input": {
        "items": [
            {
                "query_type": "select",
                "params": {
                    "keys": [
                        "visitor_id",
                        "sample_image",
                        "visit_cnt_1",
                        "visit_cnt_7"
                    ],
                    "table_name": "door_client_summary",
                    "conditions": [
                        "visitor_id LIKE '%_N'"
                    ]
                }
            },
            {
                "query_type": "create_table",
                "params": {
                    "table_name": "door_client_kvdb",
                    "keys": [
                        "visitor_id",
                        "img_str"
                    ],
                    "conditions": [
                        "VARCHAR(50)",
                        "TEXT"
                    ]
                }
            }
        ]
    }
}
```

#### D2C :: select by mask
```js
{
    "result": 0,
    "reqid": "gridonesurveillance",
    "status": "success",
    "output": {
        "items": [
            {
                "status": "select success",
                "results": [
                    {
                        "visitor_id": "visitor_000_N",
                        "sample_image": "base64 str",
                        "visit_cnt_1": 1,
                        "visit_cnt_7": 2
                    },
                    {
                        "visitor_id": "visitor_001_N",
                        "sample_image": "base64 str",
                        "visit_cnt_1": 1,
                        "visit_cnt_7": 1
                    }
                ]
            },
            {
                "status": "create success",
                "results": []
            }
        ]
    }
}
```
