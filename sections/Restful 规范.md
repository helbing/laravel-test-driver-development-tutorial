下面是我写 restful 接口所遵循的规范，你可以拿来借鉴下，也可以借鉴下 [Github 的 REST API 规范](https://developer.github.com/v3/)

## 获取单条数据

```json
// status code: 200
{
    "id": 1,
    "name": "helbing"
}
```

## 获取列表数据

```json
// status code: 200
[
    {
        "id": 1,
        "name": "helbing"
    },
    {
        "id": 2,
        "name": "tom"
    }
]
```

## 获取分页数据

```json
// status code: 200
{
    "data": [
        {
            "id": 1,
            "name": "helbing"
        },
        {
            "id": 2,
            "name": "tom"
        }
    ],
    "pagination": {
        "current_page": 1,
        "last_page": 1,
        "next_url": null,
        "previous_url": null,
        "per_page": 10,
        "total:: 2
    }
}
```

分页数据这块有两个特殊参数字段

- page: 用于页数
- per_page: 用于每页数量

```
/api?page=2&per_page=20
```

## 创建数据

```json
// status code: 201
{
    "id": 1,
    "name": "helbing"
}
```

## 更新数据

```json
// status code: 200
{
    "id": 1,
    "name": "helbing"
}
```

## 删除数据

```
// status code: 204
```

## 表单验证失败

```json
// status code: 422
{
    "sort_by": [
        "排序字段非法"
    ],
    "keyword": [
        "查询字段过长", "查询字段非法"
    ]
}
```

## 其他

```json
// status code: 400
// status code: 401
// status code: 500
{
    "message": ""
}
```
