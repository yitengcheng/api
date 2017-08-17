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
##### 14. [获取发货单列表(getSendOrderList)](#14-获取发货单列表)
##### 15. [获取收货单列表(getReceiveOrderList)](#15-获取收货单列表)
##### 16. [获取货单详情(getOrderDetail)](#16-获取货单详情)
##### 17. [修改预下单货单(modifyPreOrder)](#17-修改预下单货单)
##### 18. [删除预下单货单(removePreOrder)](#18-删除预下单货单)
##### 19. [发送货单线上支付(payForOrderWhenSend)](#19-发送货单线上支付)
##### 20. [结束货单现金支付(finishOrder)](#20-结束货单现金支付)
##### 21. [结束货单线上支付(payForOrderWhenReceive)](#21-结束货单线上支付)
##### 22. [获取订单物流信息(getLogisticsList)](#22-获取订单物流信息)
##### 23. [物流公司开始装车(startScanOrder)](#23-物流公司开始装车)
##### 24. [物流公司扫描货单(scanOrder)](#24-物流公司扫描货单)
##### 25. [物流公司结束扫描货单(finishScanOrder)](#25-物流公司结束扫描货单)
##### 26. [物流公司继续扫描货单(continueScanOrder)](#26-物流公司继续扫描货单)
##### 27. [库管扫描入库(placeStorage)](#27-库管扫描入库)
## 货物api
##### 28. [获取货物列表(getCargoList)](#28-获取货物列表)
##### 29. [获取货物详情(getCargoDetail)](#29-获取货物详情)
## 搬运队api
##### 30. [修改搬运部信息(modifyOwnPartment)](#30-修改搬运部信息)
##### 31. [获取货搬运队列表(getCarryPartmentList)](#31-获取货搬运队列表)
##### 32. [选择搬运队(selectCarryPartment)](#32-选择搬运队)
##### 33. [付搬运费(payForCarryPartment)](#33-付搬运费)
## 卡车api
##### 34. [创建卡车(createTruck)](#34-创建卡车)
##### 35. [保安检查卡车状态(checkTruckPass)](#35-保安检查卡车状态)
##### 36. [确认卡车认证通过(passExamineTruck)](#36-确认卡车认证通过)
##### 37. [获取卡车详情(getTruckDetail)](#37-获取卡车详情)
##### 38. [获取卡车列表(getWorkTruckList)](#38-获取卡车列表)
## 司机api
##### 39. [通过司机手机号获取司机信息(getDriverInfoByPhone)](#39-通过司机手机号获取司机信息)
## 路线api
##### 40. [发布路线(publishRoadmap)](#40-发布路线)
##### 41. [修改路线(modifyRoadmap)](#41-修改路线)
##### 42. [删除路线(removeRoadmap)](#42-删除路线)
##### 43. [修改路线价格(setRoadmapPrice)](#43-修改路线价格)
##### 44. [获取路线列表(getRoadmapList)](#44-获取路线列表)
##### 45. [获取路线详情(getRoadmapDetail)](#45-获取路线详情)
##### 46. [获取分店路线列表(getRoadmapListInShop)](#46-获取分店路线列表)
##### 47. [获取收货点路线列表(getRoadmapListInAgent)](#47-获取收货点路线列表)
## 协议文档
##### 48. [用户协议(user)](#48-用户协议)
##### 49. [获取软件许可协议(software)](#49-获取软件许可协议)
##### 50. [关于(about)](#50-关于)

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
    "phone": "18685192480",
    "email": "42550564@qq.com",
    "registerTime": "2017-08-08 19:43:00",
    "createTime": "2017-08-17T02:46:25.879Z",
    "authority": [
      30000,
      30001,
      30002,
      30003,
      30004,
      10005,
      10006
    ],
    "sex": 0,
    "shipper": {
      "name": "广顺达物流公司",
      "logo": "http://192.168.1.111:3000/api/image?id=5989a3c5b48db929e46ad6c4",
      "image": "http://192.168.1.111:3000/api/image?id=5989a3c5b48db929e46ad6c9",
      "sign": "这是一家非常专业的物流公司",
      "phoneList": "0851-86190987;18185192480",
      "address": "贵阳市花果园",
      "legalName": "方运江",
      "legalPhone": "18085192480",
      "createTime": "2017-08-08 19:43:01",
      "legalIDCard": [
        "http://192.168.1.111:3000/api/image?id=5989a3c5b48db929e46ad6cd",
        "http://192.168.1.111:3000/api/image?id=5989a3c5b48db929e46ad6ca"
      ],
      "acountAmount": 99930000,
      "capital": 10000000,
      "descriptList": [
        {
          "img": "http://192.168.1.111:3000/api/image?id=5989a3c5b48db929e46ad6cc",
          "text": "这是我们公司的车队"
        }
      ],
      "chairMan": {
        "phone": "18685192480",
        "id": "5989a3c4b48db929e46ad6b0",
        "phoneList": ""
      },
      "id": "5989a3c5b48db929e46ad6ce",
      "registerShopList": [
        {
          "shop": {
            "name": "华通物流超市",
            "address": {
              "name": "贵州省贵阳市南明区花果园街道花果园L2区"
            },
            "id": "5989a3c0b48db929e46ad68d"
          },
          "id": "5989a3c6b48db929e46ad6d0"
        }
      ]
    },
    "phoneList": "",
    "userId": "5989a3c4b48db929e46ad6b0"
  }
}

```
###### authority的说明：
```
authority为用户权限:
(1)总部权限
    0:创建分店的权限
    1:修改分店信息的权限
    2:删除分店的权限
    3:查看分店列表的权限
    4:修改设置的权限
    5:创建收货点的权限
    6:修改收货点的权限
    7:删除收货点的权限
    8:查看收货点的权限
(2)公共权限
    10000:修改所在物流超市信息的权限
    10001:创建成员的权限
    10002:修改成员信息的权限
    10003:删除成员的权限
    10004:查看成员的权限
    10005:充值的权限
    10006:提现的权限
    10007:修改路线的提成的权限
(3)分店权限
    20000:创建物流公司的权限
    20001:修改物流公司的权限
    20002:删除物流公司的权限
    20003:查看物流公司的权限
    20004:创建部门的权限
    20005:修改部门信息的权限
    20006:删除部门的权限
    20007:查看部门的权限
    20008:收货的权限(收货部人员)
    20009:库管的权限(库管部人员)
    20010:搬货的权限(搬运部人员)
    20011:安检的权限(保安部人员)
    20012:配送的权限(配送部人员)
(4)物流公司
    30000:修改物流公司信息的权限
    30001:修改物流公司成员权限的权限
    30002:创建路线的权限
    30003:修改路线的权限
    30004:删除路线的权限
    30005:查看路线的权限
(5)收货点
    40000:修改收货点信息的权限
    40001:修改收货点成员权限的权限
    40002:收货点下单的权限

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
### 14. [获取发货单列表](#14-获取发货单列表getsendorderlist)
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
### 15. [获取收货单列表](#15-获取收货单列表getreceiveorderlist)
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
### 16. [获取货单详情](#16-获取货单详情getorderdetail)
- `getOrderDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 货单Id |

```js
{
  "success": true,
  "context": {
    "shopId": "这个订单隶属于哪家分店（预下单的情况下为指定的某家分店）",
    "senderId": "发货的客户 Id (如果是物流公司，就是物流公司的负责人，如果是收货点，就是收货点的负责人)",
    "endPoint": "终点，精确到镇",
    "receivePartmentId": "收货的部门",
    "receiveMemberId": "具体收货制单的人员的Id",
    "modifyTime": "修改时间",
    "shipperChairManId": "物流公司董事长Id",
    "shipperId": "物流公司 Id",
    "startPoint": "省市（只对预下单有用，如果有 shopId 或 agentId 时，该字段无效）",
    "receiverName": "订单使用的收货人姓名",
    "createTime": "下单时间",
    "stateList": [
      {
        "count": 5,
        "state": 8,
        "_id": "598d495c108bc60cd2237d11"
      }
    ],
    "needPayInsuanceFee": '132,需要现场付的保险',
    "needPayTransportFee": '120,需要现场付的运费',
    "proxyCharge": '0,代收货款金额',
    "designatedFee": '0,指定收款 (只有payMode为到付的情况下，才可能有指定收款)',
    "totalDesignatedFee": '1200,全程总的指定收款(只有payMode为到付的情况下有效，实际为到付时向收货人收的运费)',
    "realFee": '1320,屏幕显示价格 fee+masterProfit+branchProfit',
    "branchProfit": '110,分部的提成',
    "masterProfit": '110,总部的提成',
    "fee": '1100,运输价格（物流公司实际价格，没有经过加价）（自动计算）',
    "payTool": '现付的情况下支付工具 0：现金支付（PT_CASH），1：支付宝（PT_ALIPAY），2：微信（PT_WEIXIN），3：银行卡（PT_BANK）',
    "payMode": '支付方式 0：现付（PM_IMMEDIATE），1：到付（PM_REACH），2：混合支付（PM_MIXED 指定收款的部分到付，其余的现付）',
    "isReachPay": '是否是到付',
    "insuanceFee": '132,担保保险的费用（客户实际付的钱）(必须现付)[初始订单]',
    "insuanceMount": '13200,担保保险额度（需要赔偿用户的钱）[初始订单]',
    "isInsuance": '是否保价 [初始订单]，如果保价，保价个度为运费的setting.insuanceMountRate倍',
    "isSendToDoor": '是否送货上门',
    "size": '方量',
    "weight": '重量',
    "totalNumbers": '总的货物的件数（具体的数量以这个数量为准）',
    "roadmapRankIndex": '该订单选择的路线在选择时的排序名次，交易成功后，需要根据这个名次修改 RoadmapMaskModel 的数据',
    "isSenderRepresentShipper": '发货人是否代表一家物流公司，如果是，需要更新物流公司的账目',
    "roadmap": {
      "shipperId": "物流公司 Id",
      "endPoint": "遵义市湄潭县新南镇",
      "branchDefaultProfitRate": '分部对路线的提成',
      "masterDefaultProfitRate": '总部对路线的提成 ',
      "id": "路线Id"
    },
    "receiver": {
      "phone": "18885192480",
      "email": "42550564@qq.com",
      "name": "方运江",
      "head": "http://192.168.1.111:3000/api/image?id=598aaa2d14573c3611f265fb",
      "id": "5989a3ccb48db929e46ad724",
      "phoneList": ""
    },
    "id": "598a67b8616e822a6131feaa"
  }
}

```
###### stateList.state的说明：
```
货主把货拉倒分店收货部，收货部对其点数，称重，量方量后填单，然后调用 < placeOriginOrder > 成功后为待选线路状态
0：待选线路（安装所填的数据，给货主显示路线排名，让货主选择一条路线，付款方式，是否交保险，是否代收货款，是否送货上门，选择后显示运费和其他费用的列表和总的费用，点击确认按钮，调用接口 < confirmSelectRoadmap >后，如果是需要付钱的进入待付款状态，否则进入待库存状态）。
1：待付款状态（1.货主在手机上刷新，使用支付宝等付款，成功后告知收货员，收货员刷新订单，显示收款成功，2.货主将现金给收货员，收货员点击代付款按钮，付款成功后，显示收款成功；之后进入待库存状态）
2：待库存（指收款成功后搬运人员将货物运到库管处的状态，交给库管成功后，状态进入待装车状态）
3：待装车（货物送到库管处，每收5吨货就通知物流公司，物流公司自己看有一车的时候会生成一个货车实例<包括司机和货车信息>到检查部审核，审核成功后，将车开到库管处，物流公司会通过竞价联系搬运部，搬运部搬运货物上车，物流公司需要一件一件的扫描，装车完成，需要给库管确认，库管确认之后，进入待出发状态）
4：待出发 （物流公司将车开到门卫处，门卫扫描驾驶员的二维码，点击放行按钮，进入运输中状态）
5：运输中 （运输过程中，驾驶员需要开启app，自动上传位置信息）
6：交货成功 （司机将货物送到目的地之后，会劝说收货人安装app或者扫描小程序，然后让他扫描货物，确认收货的件数，完成交接）
```

---
### 17. [修改预下单货单](#17-修改预下单货单modifypreorder)
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
### 18. [删除预下单货单](#18-删除预下单货单removepreorder)
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
### 19. [发送货单线上支付](#19-发送货单线上支付payfororderwhensend)
- `payForOrderWhenSend`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单Id |

```js
{
  "success": true
}
```

---
### 20. [结束货单现金支付](#20-结束货单现金支付finishorder)
- `finishOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单Id |

```js
{
  "success": true
}
```

---
### 21. [结束货单线上支付](#21-结束货单线上支付payfororderwhenreceive)
- `payForOrderWhenReceive`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单Id |

```js
{
  "success": true
}
```

---
### 22. [获取订单物流信息](#22-获取订单物流信息getlogisticslist)
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
### 23. [物流公司开始装车](#23-物流公司开始装车startscanorder)
- `startScanOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |

```js
{
  "success": true
}
```

---
### 24. [物流公司扫描货单](#24-物流公司扫描货单scanorder)
- `scanOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |
| orderId | ID | 货单Id |
| count | Number | 件数 |

```js
{
  "success": true,
  "context": {
    "truck": {
      "shipperId": "59954973d1df03410425a946",
      "shopId": "5995496cd1df03410425a904",
      "plateNo": "贵A-778899",
      "drivingLicense": "A71236717",
      "truckType": "4.5米 高栏",
      "driverId": "59954975d1df03410425a94e",
      "carryPartmentId": "59954970d1df03410425a91d",
      "scannerId": "59954972d1df03410425a928",
      "createTime": "2017-08-17 16:07:20",
      "unloadAllOrderList": [
        "59954981d1df03410425a953"
      ],
      "totalSize": 1,
      "totalWeight": 10,
      "totalNumber": 1,
      "orderCount": 1,
      "orderList": [
        "59954981d1df03410425a953"
      ],
      "state": 4,
      "locationList": [],
      "insuanceMount": 1000000,
      "carryPrice": 100,
      "id": "59954eb8d1df03410425a95f"
    }
  }
}
```

---
### 25. [物流公司结束扫描货单](#25-物流公司结束扫描货单finishscanorder)
- `finishScanOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |

```js
{
  "success": true
}
```

---
### 26. [物流公司继续扫描货单](#26-物流公司继续扫描货单continuescanorder)
- `continueScanOrder`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |

```js
{
  "success": true
}
```

---
### 27. [库管扫描入库](#27-库管扫描入库placestorage)
- `placeStorage`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| orderId | ID | 订单Id |
| count | Number | 货物件数 |

```js
{
  "success": true,
  "order": {
    "storeScannerId": "59954970d1df03410425a91a",
    "shopId": "5995496cd1df03410425a904",
    "senderId": "59954981d1df03410425a951",
    "receiverId": "59954981d1df03410425a952",
    "receiverName": "18885192481",
    "endPoint": "北京市东城区景山街道",
    "endPointLastCode": 110101002,
    "receivePartmentId": "59954970d1df03410425a917",
    "receiveMemberId": "59954970d1df03410425a916",
    "roadmapId": "59954975d1df03410425a94c",
    "shipperChairManId": "59954972d1df03410425a928",
    "shipperId": "59954973d1df03410425a946",
    "createTime": "2017-08-17 15:45:05",
    "stateList": [
      {
        "state": 5,
        "count": 1,
        "_id": "59954d7dd1df03410425a95e"
      },
      {
        "state": 4,
        "count": 4,
        "_id": "59954982d1df03410425a95a"
      }
    ],
    "needPayInsuanceFee": 0,
    "needPayTransportFee": 1200,
    "proxyChargeProfit": 0,
    "proxyCharge": 0,
    "designatedFee": 0,
    "totalDesignatedFee": 1200,
    "realFee": 1200,
    "branchProfit": 100,
    "masterProfit": 100,
    "fee": 1000,
    "payTool": 0,
    "payMode": 2,
    "isReachPay": false,
    "insuanceFee": 0,
    "insuanceMount": 0,
    "isInsuance": false,
    "isSendToDoor": false,
    "size": 1,
    "weight": 10,
    "totalNumbers": 5,
    "roadmapRankIndex": 0,
    "isSenderRepresentShipper": false,
    "id": "59954981d1df03410425a953"
  }
}
```
---

## 货物api

---
### 28. [获取货物列表](#28-获取货物列表getcargolist)
- `getCargoList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---
### 29. [获取货物详情](#29-获取货物详情getcargodetail)
- `getCargoDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| oldPassword | String | 旧密码 |
| newPassword | String | 新密码 |

---

## 搬运队api

---
### 30. [修改搬运部信息](#30-修改搬运部信息modifyownpartment)
- `modifyOwnPartment`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| partmentId | ID | 部门Id |
| price | Number | 单价 |
| enable | Bool | 是否在线 |

```js
{
  "success": true,
  "context": {
    "name": "搬运部",
    "descript": "我们活着的意义就是移动",
    "phoneList": "0851-98989000;0851-98989001",
    "price": 100,
    "enable": true,
    "chargeMan": {
      "phone": "18385192480",
      "name": "搬运工负责人",
      "id": "59954970d1df03410425a91c",
      "phoneList": ""
    },
    "id": "59954970d1df03410425a91d"
  }
}
```

---
### 31. [获取货搬运队列表](#31-获取货搬运队列表getcarrypartmentlist)
- `getCarryPartmentList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |


```js
{
  "success": true,
  "context": {
    "partmenList": [
      {
        "shopId": "5995496cd1df03410425a904",
        "chargeManId": "59954970d1df03410425a91c",
        "name": "搬运部",
        "type": 2,
        "descript": "我们活着的意义就是移动",
        "phoneList": "0851-98989000;0851-98989001",
        "price": 100,
        "modifyTime": "2017-08-17 16:23:00",
        "createTime": "2017-08-17 15:44:48",
        "isBusy": false,
        "enable": true,
        "id": "59954970d1df03410425a91d"
      }
    ]
  }
}
```

---
### 32. [选择搬运队](#32-选择搬运队selectcarrypartment)
- `selectCarryPartment`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |
| carryPartmentId | ID | 搬运队Id |


```js
{
  "success": true
}
```

---
### 33. [付搬运费](#33-付搬运费payforcarrypartment)
- `payForCarryPartment`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |

```js
{
  "success": true
}
```

---

## 卡车api

---
### 34. [创建卡车](#34-创建卡车createtruck)
- `createTruck`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| shopId | ID | 分店Id |
| plateNo | String | 车牌号 |
| drivingLicense | String | 驾照号 |
| truckType | String | 卡车类型 |
| insuanceMount | Number | 保险 |
| driverId | ID | 司机Id |

```js
{
  "success": true,
  "context": {
    "plateNo": "贵A-778899",
    "drivingLicense": "A71236717",
    "truckType": "4.5米 高栏",
    "driverId": null,
    "locationList": [],
    "insuanceMount": 1000000,
    "driver": null,
    "id": "59954eb8d1df03410425a95f"
  }
}
```

### 35. [保安检查卡车状态](#35-保安检查卡车状态checktruckpass)
- `checkTruckPass`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| driverId | ID | 司机Id |

```js
{
  "success": true,
  "context": {
    "isEnter": true
  }
}
```

---
### 36. [确认卡车认证通过](#36-确认卡车认证通过passexaminetruck)
- `passExamineTruck`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |

```js
{
  "success": true
}

```

---
### 37. [获取卡车详情](#37-获取卡车详情gettruckdetail)
- `getTruckDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |

```js
{
  "success": true,
  "context": {
    "shipperId": "59954973d1df03410425a946",
    "shopId": "5995496cd1df03410425a904",
    "plateNo": "贵A-778899",
    "drivingLicense": "A71236717",
    "truckType": "4.5米 高栏",
    "driverId": null,
    "createTime": "2017-08-17 16:07:20",
    "unloadAllOrderList": [],
    "totalSize": 0,
    "totalWeight": 0,
    "totalNumber": 0,
    "orderCount": 0,
    "orderList": [],
    "state": 1,
    "locationList": [],
    "insuanceMount": 1000000,
    "carryPrice": 0,
    "driver": null,
    "id": "59954eb8d1df03410425a95f"
  }
}

```
---
### 38. [获取卡车列表](#38-获取卡车列表getworktrucklist)
- `getWorkTruckList`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| truckId | ID | 卡车Id |
| keyword | String | 关键字 |
| pageNo | Number | 页码 |
| pageSize | Number | 每一页大小 |

```js
没开始装车时：
{
  "success": true,
  "context": {
    "count": 2,
    "truckList": [
      {
        "plateNo": "贵A-778899",
        "drivingLicense": "A71236717",
        "truckType": "4.5米 高栏",
        "driverId": null,
        "state": 1,
        "locationList": [],
        "insuanceMount": 1000000,
        "driver": null,
        "id": "59954eb8d1df03410425a95f"
      },
      {
        "plateNo": "贵A-778899",
        "drivingLicense": "A71236717",
        "truckType": "4.5米 高栏",
        "driverId": null,
        "state": 0,
        "locationList": [],
        "insuanceMount": 1000000,
        "driver": null,
        "id": "59954976d1df03410425a94f"
      }
    ]
  }
}

没装完车时：
{
  "success": true,
  "context": {
    "truck": {
      "shipperId": "59954973d1df03410425a946",
      "shopId": "5995496cd1df03410425a904",
      "plateNo": "贵A-778899",
      "drivingLicense": "A71236717",
      "truckType": "4.5米 高栏",
      "driverId": "59954975d1df03410425a94e",
      "carryPartmentId": "59954970d1df03410425a91d",
      "scannerId": "59954972d1df03410425a928",
      "createTime": "2017-08-17 16:07:20",
      "unloadAllOrderList": [
        "59954981d1df03410425a953"
      ],
      "totalSize": 1,
      "totalWeight": 10,
      "totalNumber": 1,
      "orderCount": 1,
      "orderList": [
        "59954981d1df03410425a953"
      ],
      "state": 4,
      "locationList": [],
      "insuanceMount": 1000000,
      "carryPrice": 100,
      "id": "59954eb8d1df03410425a95f"
    }
  }
}

```


---

## 司机api

---
### 39. [通过司机手机号获取司机信息](#39-通过司机手机号获取司机信息getdriverinfobyphone)
- `getDriverInfoByPhone`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| phone | String | 司机手机号 |

```js
{
  "success": true,
  "context": {
    "phone": "18985192480",
    "email": "42550564@qq.com",
    "name": "方运江",
    "head": "http://192.168.1.111:3000/api/image?id=599577a97aad4147a4f845db",
    "birthday": "1982-02-25",
    "address": "贵州省贵阳市",
    "license": "599577a97aad4147a4f845db",
    "licenseNo": "123123123",
    "registerTime": "2017-08-17 18:54:04",
    "sex": 0,
    "age": 35,
    "id": "599575cc277608472d636e97",
    "phoneList": ""
  }
}
```

---

## 路线api

---
### 40. [发布路线](#40-发布路线publishroadmap)
- `publishRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| shopId | ID | 分店Id |
| endPoint | String | 终点 |
| endPointLastCode | Number | 终点编码 |
| price | Number | 运费单价 |
| minFee | Number | 运费起价 |
| sendToDoorPrice | Number | 送货上门单价 |
| sendToDoorMinFee | Number | 送货上门起价 |
| remark | String | 备注 |

---
### 41. [修改路线](#41-修改路线modifyroadmap)
- `modifyRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| roadmapId | ID | 路线Id |
| endPoint | String | 终点 |
| endPointLastCode | Number | 终点编码 |
| price | Number | 运费单价 |
| minFee | Number | 运费起价 |
| sendToDoorPrice | Number | 送货上门单价 |
| sendToDoorMinFee | Number | 送货上门起价 |
| remark | String | 备注 |

```js
{
  "success": true
}
```

---
### 42. [删除路线](#42-删除路线removeroadmap)
- `removeRoadmap`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| roadmapId | ID | 路线 |

```js
{
  "msg": "你没有删除路线的权限"
}
```

---
### 43. [修改路线价格](#43-修改路线价格setroadmapprice)
- `setRoadmapPrice`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| userId | ID | 用户Id |
| roadmapIdList | Array | 路线Id列表 |
| typeList | Array | 修改类型列表（0：长途运费单价  1：长途运费起价  2：送货上门单价  3：送货上门起价） |
| mode | Number | 修改模式 （0: 按照价格调整  1: 按照百分比调整  2: 按照名次调整）|
| value | Number | 修改量（如果mode为0和1时，正数为增加，负数为减少） |

```js
{
  "success": true
}
```
---
### 44. [获取路线列表](#44-获取路线列表getroadmaplist)
- `getRoadmapList`
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
    "roadmapList": [
      {
        "endPoint": "北京市东城区景山街道",
        "endPointLastCode": 110101002,
        "selfSignRate": 0,
        "duration": 0,
        "sendToDoorMinFee": 50,
        "sendToDoorPrice": 100,
        "minFee": 50,
        "price": 100,
        "startPoint": "贵州省贵阳市南明区花果园街道花果园L2区",
        "masterDefaultProfitRate": 0.1,
        "id": "59954975d1df03410425a94c"
      }
    ]
  }
}
```

---
### 45. [获取路线详情](#45-获取路线详情getroadmapdetail)
- `getRoadmapDetail`
- 请求方式：`POST`

| 参数名称 | 参数类型  | 描述 |
| :- |:-:| :-:|
| roadmapId | ID | 路线 |

```js
{
  "success": true,
  "context": {
    "shipperId": "59954973d1df03410425a946",
    "shipperInBranchShopId": "59954974d1df03410425a948",
    "endPoint": "北京市东城区景山街道",
    "endPointLastCode": 110101002,
    "createTime": "2017-08-17 15:44:53",
    "monthTradeTimes": 0,
    "tradeTimes": 0,
    "selfSignRate": 0,
    "duration": 0,
    "updateSendToDoorMinFeeTime": "2017-08-17T07:44:53.230Z",
    "sendToDoorMinFee": 51,
    "updateSendToDoorPriceTime": "2017-08-17T07:44:53.230Z",
    "sendToDoorPrice": 101,
    "updateMinPriceTime": "2017-08-17T07:44:53.230Z",
    "minFee": 51,
    "updatePriceTime": "2017-08-17T07:44:53.230Z",
    "price": 101,
    "enable": true,
    "shop": {
      "name": "华通物流超市",
      "address": {
        "name": "贵州省贵阳市南明区花果园街道花果园L2区"
      },
      "id": "5995496cd1df03410425a904"
    },
    "startPoint": "贵州省贵阳市南明区花果园街道花果园L2区",
    "masterDefaultProfitRate": 0.1,
    "id": "59954975d1df03410425a94c"
  }
}
```

---
### 46. [获取分店路线列表](#46-获取分店路线列表getroadmaplistinshop)
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
### 47. [获取收货点路线列表](#47-获取收货点路线列表getroadmaplistinagent)
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

### 48. [用户协议](#48-用户协议user)
- `user`
- url: `protocals/user.html`

---

### 49. [获取软件许可协议](#49-获取软件许可协议software)
- `software`
- url: `protocals/software.html`

---

### 50. [关于](#50-关于about)
- `about`
- url: `protocals/about.html`
