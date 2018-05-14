# 目录
## 团队api
##### 1. [创建业绩团队(createAchieveGroup)](#1-创建业绩团队)
##### 2. [获取业绩团队列表(getAchieveGroupList)](#2-获取业绩团队列表)
##### 3. [修改业绩团队(modifyAchieveGroup)](#3-修改业绩团队)
##### 4. [删除业绩团队(removeAchieveGroup)](#4-删除业绩团队)

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
---

### 2. [获取业绩团队列表](#2-获取业绩团队列表getachievegrouplist)
- `getAchieveGroupList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |

```js
{
    "success": true,
    "context": {
        "list":[
            {"团队1"},
            {"团队2"}
        ]
    }
}
```
---

### 3. [修改业绩团队](#3-修改业绩团队modifyachievegroup)
- `modifyAchieveGroup`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| groupId | String | 团队ID |
| name | String | 新团队名字 |
| chargeMan | String | 新负责人名字 |

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
---

### 4. [删除业绩团队](#4-删除业绩团队removeachievegroup)
- `removeAchieveGroup`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| groupId | String | 团队ID |

```js
{
    "success": true
}
```
