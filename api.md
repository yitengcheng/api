# 目录
## 团队api
##### 1. [创建业绩团队(createAchieveGroup)](#1-创建业绩团队)
##### 2. [获取业绩团队列表(getAchieveGroupList)](#2-获取业绩团队列表)
##### 3. [修改业绩团队(modifyAchieveGroup)](#3-修改业绩团队)
##### 4. [删除业绩团队(removeAchieveGroup)](#4-删除业绩团队)
## 成员api
##### 5. [添加业绩成员(addAchieveMember)](#5-添加业绩成员)
##### 6. [获取业绩成员列表(getAchieveMemberList)](#6-获取业绩成员列表)
##### 7. [删除业绩成员(removeAchieveMember)](#7-删除业绩成员)
## 组织api
##### 8. [创建业绩小组(createAchieveOrganize)](#8-创建业绩小组)
##### 9. [获取业绩小组列表(getAchieveOrganizeList)](#9-获取业绩小组列表)
##### 10. [修改业绩小组(modifyAchieveOrganize)](#10-修改业绩小组)
##### 11. [删除业绩小组(removeAchieveOrganize)](#11-删除业绩小组)
## 个人api
##### 12. [获取个人信息(getPersonalInfo)](#12-获取个人信息)
## 业绩api
##### 13. [设置业务成绩(setAchievePoints)](#13-设置业务成绩)
##### 14. [修改业务成绩(modifyAchievePoints)](#14-修改业务成绩)
##### 15. [获取一个组内的业绩排名列表(getAchievePointsList)](#15-获取一个组内的业绩排名列表)
##### 16. [获取组间的业绩排名列表(getGroupAchievePointsList)](#16-获取组间的业绩排名列表)

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

---

## 成员api

---

### 5. [添加业绩成员](#5-添加业绩成员addachievemember)
- `addAchieveMember`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| member | String | 成员 |

```js
{
    "success": true,
    "context": {
        "organizeId": "所属组织",
        "name": "组名称",
        "chargeMan": "组长的微信的openId(一个人只能管理一个组)",
        "members": [{ "成员的微信的openId" }],
        "createTime": "创建时间",
        "modifyTime": "修改时间",
    }
}
```
---

### 6. [获取业绩成员列表](#6-获取业绩成员列表getachievememberlist)
- `getAchieveMemberList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |

```js
{
    "success": true,
    "context": {
        "list":[
            {"成员1"},
            {"成员2"}
        ]
    }
}
```

---

### 7. [删除业绩成员](#7-删除业绩成员removeachievemember)
- `removeAchieveMember`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| member | String | 成员 |

```js
{
    "success": true
}
```
---

## 组织api

---

### 8. [创建业绩小组](#8-创建业绩小组createachieveorganize)
- `createAchieveOrganize`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| name | String | 小组名称 |
| chargeMan | String | 负责人 |

```js
{
    "success": true,
    "context": {
        "name":"小组1",
        "chargeMan":"负责人1",
        "creator": "创建人",
    }
}
```
---

### 9. [获取业绩小组列表](#9-获取业绩小组列表getachieveorganizelist)
- `getAchieveOrganizeList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |

```js
{
    "success": true,
    "context": {
        "list":[
            {"小组1"},
            {"小组2"}
        ]
    }
}
```
---

### 10. [修改业绩小组](#10-修改业绩小组modifyachieveorganize)
- `modifyAchieveOrganize`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| organizeId | String | 小组ID |
| name | String | 新团队名字 |
| chargeMan | String | 新负责人名字 |

```js
{
    "success": true,
    "context": {
        "name":"小组1",
        "chargeMan":"负责人1",
        "creator": "创建人",
        "groups": [ "团队1","团队2" ],
    }
}
```
---

### 11. [删除业绩小组](#11-删除业绩小组removeachieveorganize)
- `removeAchieveOrganize`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| organizeId | String | 小组id |

```js
{
    "success": true
}
```
---

## 个人api

---

### 12. [获取个人信息](#12-获取个人信息getpersonalinfo)
- `getPersonalInfo`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |

```js
{
    "success": true,
    "context": {
        "role":"0",
    }
}
"role: 0: 无角色，1： 组织创建者，2：组织负责人，3：组长，4：组成员"
```
---

## 业绩api

---

### 13. [设置业务成绩](#13-设置业务成绩setachievepoints)
- `setAchievePoints`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| points | String | 业绩 |
| date | String | 日期(YYYY-MM-DD) |

```js
{
    "success": true,
    "context": {
        "wxOpenId":"微信id",
        "groupId": "团队ID",
        "points": "业绩",
        "date": "日期",
    }
}
```
---

### 14. [修改业务成绩](#14-修改业务成绩modifyachievepoints)
- `modifyAchievePoints`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| achieveId | String | 业绩id |
| points | String | 业绩 |

```js
{
    "success": true,
    "context": {
        "wxOpenId":"微信id",
        "groupId": "团队ID",
        "points": "业绩",
        "date": "日期",
    }
}
```
---

### 15. [获取一个组内的业绩排名列表](#15-获取一个组内的业绩排名列表getachievepointslist)
- `getAchievePointsList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| achieveGroupId | String | 团队ID |
| date | String | 日期 |
| pageNo | Int | 页号 |
| pageSize | Int | 页容量 |

```js
{
    "success": true,
    "context": {
        "list":[
            {"小组1"},
            {"小组2"}
        ]
    }
}
```
---

### 16. [获取组间的业绩排名列表](#16-获取组间的业绩排名列表getgroupachievepointslist)
- `getGroupAchievePointsList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| wxOpenId | String | 微信openid |
| achieveGroupId | String | 父级组的Id |
| date | String | 日期 |

```js
{
    "success": true,
    "context": {
        "list":[
            {
                "groupName": "团队名称",
                "groupChargeMan": "团队负责人",
                "totalCount": "总单数",
                "totalPoints": "总业绩",
                "realCount": "真实单数",
            }
        ]
    }
}
```
