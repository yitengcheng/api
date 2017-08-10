# 目录
## 基础api
##### 1. [登录(login)](#1-登录)
##### 2. [注册(register)](#2-注册)
##### 3. [获取账户余额(getRemainAmount)](#3-获取账户余额)
##### 4. [账户充值(recharge)](#4-账户充值)
##### 5. [账户提现(withdraw)](#5-账户提现)
##### 6. [获取个人信息(getPersonalInfo)](#6-获取个人信息)
##### 7. [修改个人信息(modifyPersonalInfo)](#7-修改个人信息)
##### 8. [修改密码(modifyPassword)](#8-修改密码)
##### 9. [意见反馈(submitFeedback)](#9-意见反馈)
##### 10. [获取交易记录(getBillList)](#10-获取交易记录)
##### 11. [获取中国区划地址(getRegionAddress)](#11-获取中国区划地址)
##### 12. [获取发货点地址(getStartPointAddress)](#12-获取发货点地址)
## 货单api
##### 13. [预下单(placePreOrder)](#13-预下单)
##### 14. [下初始单(placeOriginOrder)](#14-下初始单)
##### 15. [下中转单(placeTransferOrder)](#15-下中转单)
##### 16. [获取发货单列表(getSendOrderList)](#16-获取发货单列表)
##### 17. [获取收货单列表(getReceiveOrderList)](#17-获取收货单列表)
##### 18. [获取货单详情(getOrderDetail)](#18-获取货单详情)
##### 19. [修改预下单货单(modifyPreOrder)](#19-修改预下单货单)
##### 20. [删除预下单货单(removePreOrder)](#20-删除预下单货单)
##### 21. [货主使用app支付货单(payForOrderWhenSend)](#21-货主使用app支付货单)
##### 22. [结束货单(finishOrder)](#22-结束货单)
##### 23. [获取订单物流信息(getLogisticsList)](#23-获取订单物流信息)
## 货物api
##### 24. [获取货物列表(getCargoList)](#24-获取货物列表)
##### 25. [获取货物详情(getCargoDetail)](#25-获取货物详情)
## 路线api
##### 26. [发布路线(publishRoadmap)](#26-发布路线)
##### 27. [修改路线(modifyRoadmap)](#27-修改路线)
##### 28. [删除路线(removeRoadmap)](#28-删除路线)
##### 29. [获取路线列表(getRoadmapList)](#29-获取路线列表)
##### 30. [获取路线详情(getRoadmapDetail)](#30-获取路线详情)
##### 31. [获取分店路线列表(getRoadmapListInShop)](#31-获取分店路线列表)
##### 32. [获取收货点路线列表(getRoadmapListInAgent)](#32-获取收货点路线列表)
## 协议文档
##### 33. [用户协议(user)](#33-用户协议)
##### 34. [获取软件许可协议(software)](#34-获取软件许可协议)
##### 35. [关于(about)](#35-关于)

---

## 基础api

---

### 1. [登录](#1-登录login)
- `login`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| phone | String | 登录手机号码 |
| password | String | 登录密码 |

```js
{
    "success": true,
    "context": {
        "userId": "10000"
    }
}
```

---

### 2. [注册](#2-注册register)
- `register`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| phone | String | 登录手机号码 |
| email | String | 找回密码的邮箱 |
| password | String | 登录密码 |


```js
{
    "success": true
}
```

---

### 3. [获取账户余额](#3-获取账户余额getremainamount)
- `getRemainAmount`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |


```js
{
  "success": true,
  "context": {
    "amount": 98800
  }
}
```


---

### 4. [账户充值](#4-账户充值recharge)
- `recharge`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| amount | Number | 充值金额 |
| thirdpartyAccount | Number | 充值账户平台（第三方的账号  0：支付宝(A)， 1：财付通(C)，2：工商银行(G)，3：建设银行(J)， 4：中国银行（Z）， 5：农业银行(N)，规则，给定的缩写字母+账号） |


```js
{
  "success": true,
  "context": {
    "amount": 99097
  }
}
```

---

### 5. [账户提现](#5-账户提现withdraw)
- `withdraw`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| amount | Number | 提现金额 |
| thirdpartyAccount | Number | 提现账户平台（第三方的账号  0：支付宝(A)， 1：财付通(C)，2：工商银行(G)，3：建设银行(J)， 4：中国银行（Z）， 5：农业银行(N)，规则，给定的缩写字母+账号） |


```js
{
  "success": true,
  "context": {
    "amount": 99097
  }
}
```

---

### 6. [获取个人信息](#6-获取个人信息getpersonalinfo)
- `getPersonalInfo`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |


```js
{
    "success": true,
    "context": {
        "phone": "手机号码",
        "name": "用户名",
        "head": "头像",
        "position": "职位",
        "authority": [1],
        "sex": 1
    }
}
```
###### authority的说明：
```
authority为用户权限， 1：普通权限 2：拥有领导权限，4：拥有综合部权限，8：拥有监督者权限
```
---

### 7. [修改个人信息](#7-修改个人信息modifypersonalinfo)
- `modifyPersonalInfo`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| phone | String | 登录手机号码 |
| name | String | 用户名 |
| head | String | 头像 |
| position | String | 职位 |


```js
{
    "success": true,
}
```

---

### 8. [修改密码](#8-修改密码modifypassword)
- `modifyPassword`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

```js
{
    "success": true,
}
```

---

### 9. [意见反馈](#9-意见反馈submitfeedback)
- `submitFeedback`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| content | String | 内容 |
| email | String | 联系邮箱 |

```js
{
    "success": true,
}
```

---

### 10. [获取交易记录](#10-获取交易记录getbilllist)
- `getBillList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |

```js
{
  "success": true,
  "context": {
    "count": 1,
    "billList": [
      {
        "tradeAmountYuan": 100000,
        "tradeTime": "2017-08-08 19:43:09",
        "tradeAmount": 10000000,
        "thirdpartyAccount": "A支付宝测试账号",
        "orderId": null,
        "remark": "个人充值"
      }
    ]
  }
}

```
---

### 11. [获取中国区划地址](#11-获取中国区划地址getregionaddress)
- `getRegionAddress`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| parentCode | Number | 上级编码 |

```js
{
  "success": true,
  "context": {
    "addressList": [
      {
        "id": 1,
        "code": 11,
        "parentCode": 0,
        "name": "北京市",
        "level": 1
      }
    ]
  }
}
```
---

### 12. [获取发货点地址](#12-获取发货点地址getstartpointaddress)
- `getStartPointAddress`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| parentCode | Number | 上级编码 |
| region | String | 区划地址 |

```js
{
  "success": true,
  "context": {
    "addressList": [
      {
        "name": "华通物流超市",
        "address": {
          "name": "贵阳市石板镇"
        },
        "id": "59841315ad007024a2c0ce9b",
        "isShop": true
      }
    ]
  }
}
```
---

## 货单api

---
### 13. [预下单](#13-预下单placepreorder)
- `placePreOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单号 |
| shopId | ID | 指定的某家分店 |
| agentId | ID | 指定的某家收货点 |
| startPoint | String | 始发地 |
| receiverPhone | String | 收货人电话 |
| receiverName | String | 收货人姓名 |
| endPoint | String | 货到地 |
| totalNumbers | Number | 一票货总的件数 |
| weight | Number | 一票货总的重量 |
| size | Number | 一票货总的方量 |
| isSendToDoor | Bool | 是否送货上门 |
| proxyCharge | Bool | 代收货款金额 |
| isInsuance | Bool | 是否保价 |
| isReachPay | Bool | 是否到付 (如果是到付，并且设置了totalDesignatedFee，为指定向收货人收totalDesignatedFee的运费，否则向收货人收初始单计算出来的运费)|
| totalDesignatedFee | Number | 指定收款金额 |
| photo | String | 货单照片 |


```js
{
    "success": true,
}
```

---
### 14. [下初始单](#14-下初始单placeoriginorder)
- `placeOriginOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 15. [下中转单](#15-下中转单placetransferorder)
- `placeTransferOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 16. [获取发货单列表](#16-获取发货单列表getsendorderlist)
- `getSendOrderList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| type | String | 类型 (preorder,waitpay,onway,complete)|
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |


```js
{
  "success": true,
  "context": {
    "orderList": [
      {
        "endPoint": "遵义市湄潭县新南镇",
        "createTime": "2017-08-03 10:51:53",
        "needPayInsuanceFee": 0,
        "needPayTransportFee": 600,
        "realFee": 0,
        "payTool": 0,
        "size": 1,
        "weight": 10,
        "totalNumbers": 5,
        "receiver": {
          "phone": "18885192481",
          "id": "59827a100bbe270ec8d9b4ab"
        },
        "id": "59828fc90bbe270ec8d9b4ae"
      }
    ]
  }
}

```
---
### 17. [获取收货单列表](#17-获取收货单列表getreceiveorderlist)
- `getReceiveOrderList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| type | String | 类型(all,onway,complete) |
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |


```js
{
  "success": true,
  "context": {
    "orderList": [
      {
        "endPoint": "遵义市湄潭县新南镇",
        "embraceTime": "2017-08-03 10:51:53",
        "createTime": "2017-08-03 10:51:53",
        "needPayInsuanceFee": 0,
        "proxyCharge": 20000,
        "realFee": 0,
        "payMode": 2,
        "isSendToDoor": false,
        "size": 1,
        "weight": 10,
        "totalNumbers": 5,
        "receiver": {
          "phone": "18885192481",
          "id": "59827a100bbe270ec8d9b4ab"
        },
        "sender": {
          "phone": "18885192480",
          "id": "59827a100bbe270ec8d9b4aa"
        },
        "id": "59828fc90bbe270ec8d9b4ae"
      }
    ]
  }
}
```

---
### 18. [获取货单详情](#18-获取货单详情getorderdetail)
- `getOrderDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 19. [修改预下单货单](#19-修改预下单货单modifypreorder)
- `modifyPreOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单号 |
| shopId | ID | 指定的某家分店 |
| agentId | ID | 指定的某家收货点 |
| startPoint | String | 始发地 |
| receiverPhone | String | 收货人电话 |
| receiverName | String | 收货人姓名 |
| endPoint | String | 货到地 |
| totalNumbers | Number | 一票货总的件数 |
| weight | Number | 一票货总的重量 |
| size | Number | 一票货总的方量 |
| isSendToDoor | Bool | 是否送货上门 |
| proxyCharge | Bool | 代收货款金额 |
| isInsuance | Bool | 是否保价 |
| isReachPay | Bool | 是否到付 (如果是到付，并且设置了totalDesignatedFee，为指定向收货人收totalDesignatedFee的运费，否则向收货人收初始单计算出来的运费)|
| totalDesignatedFee | Number | 指定收款金额 |
| photo | String | 货单照片 |

```js
{
  "success": true
}
```

---
### 20. [删除预下单货单](#20-删除预下单货单removepreorder)
- `removePreOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单号 |

```js
{
  "success": true
}
```
---
### 21. [货主使用app支付货单](#21-货主使用app支付货单payfororderwhensend)
- `payForOrderWhenSend`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 22. [结束货单](#22-结束货单finishorder)
- `finishOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 23. [获取订单物流信息](#23-获取订单物流信息getlogisticslist)
- `getLogisticsList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单Id |

```js
{
  "success": true,
  "logisticsList": [
    {
      "shopName": "华通物流超市",
      "address": "贵州省贵阳市南明区花果园街道花果园L2区",
      "locateTime": "2017-08-09T02:17:55.848Z"
    }
  ]
}
```
---

## 货物api

---
### 24. [获取货物列表](#24-获取货物列表getcargolist)
- `getCargoList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 25. [获取货物详情](#25-获取货物详情getcargodetail)
- `getCargoDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---

## 路线api

---
### 26. [发布路线](#26-发布路线publishroadmap)
- `publishRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 27. [修改路线](#27-修改路线modifyroadmap)
- `modifyRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 28. [删除路线](#28-删除路线removeroadmap)
- `removeRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 29. [获取路线列表](#29-获取路线列表getroadmaplist)
- `getRoadmapList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 30. [获取路线详情](#30-获取路线详情getroadmapdetail)
- `getRoadmapDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 31. [获取分店路线列表](#31-获取分店路线列表getroadmaplistinshop)
- `getRoadmapListInShop`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| region | String | 地址 |
| branchShopId | String | 分店Id |
| location | Array | 坐标 |
| orderBy | Number | 排序类型 |
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |

```js
{
  "success": true,
  "context": {
    "roadmapList": [
      {
        "endPoint": "遵义市湄潭县新南镇",
        "selfSignRate": 0,
        "duration": 0,
        "sendToDoorPrice": 10,
        "price": 20,
        "id": "598965bfbdfa331feb32ce12",
        "shipper": {
          "name": "广顺达物流公司"
        },
        "shop": {
          "_id": "598965b8bdfa331feb32cdb6",
          "name": "华通物流超市",
          "distance": 10.888834907682734
        }
      },
      {
        "endPoint": "遵义市湄潭县新南镇",
        "selfSignRate": 0,
        "duration": 0,
        "sendToDoorPrice": 10,
        "price": 100,
        "id": "598965bdbdfa331feb32cdef",
        "shipper": {
          "name": "广顺达物流公司"
        },
        "shop": {
          "_id": "598965b6bdfa331feb32cda8",
          "name": "华通物流超市",
          "distance": 0.6651347015721002
        }
      }
    ]
  }
}

```

---
### 32. [获取收货点路线列表](#32-获取收货点路线列表getroadmaplistinagent)
- `getRoadmapListInAgent`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| region | String | 地址 |
| agentId | String | 收货点Id |
| location | Array | 坐标 |
| orderBy | Number | 排序类型 |
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |

```js
{
  "success": true,
  "context": {
    "roadmapList": [
      {
        "endPoint": "遵义市湄潭县新南镇",
        "selfSignRate": 0,
        "duration": 0,
        "sendToDoorPrice": 15,
        "price": 150,
        "shipper": {
          "name": "广顺达物流公司",
          "id": "598965bbbdfa331feb32cde9"
        },
        "id": "598965bdbdfa331feb32cdef",
        "distance": 18.138418524923516,
        "agent": {
          "name": "后巢乡收货点"
        }
      },
      {
        "endPoint": "遵义市湄潭县新南镇",
        "selfSignRate": 0,
        "duration": 0,
        "sendToDoorPrice": 15,
        "price": 150,
        "shipper": {
          "name": "广顺达物流公司",
          "id": "598965bbbdfa331feb32cde9"
        },
        "id": "598965bdbdfa331feb32cdef",
        "distance": 18.138418524923516,
        "agent": {
          "name": "后巢乡收货点"
        }
      }
    ]
  }
}
```

---

## 协议文档

---

### 33. [用户协议](#33-用户协议user)
- `user`
- url: `protocals/user.html`

---

### 34. [获取软件许可协议](#34-获取软件许可协议software)
- `software`
- url: `protocals/software.html`

---

### 35. [关于](#35-关于about)
- `about`
- url: `protocals/about.html`
