# 目录
## 团队api
##### 1. [创建业绩团队(createAchieveGroup)](#1-创建业绩团队)

---

## 团队api

---

### 1. [创建业绩团队](#1-创建业绩团队createachievegroup)
- `createAchieveGroup`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| name | String | 团队名称 |
| chargeMan | String | 负责人 |

```js
{
    "success": true,
    "context": {
        "name":"团队1",
        "chargeMan":"负责人1",
        "organizeId": "团队ID",
        "members": [ "负责人1","成员" ],
    }
}
```
