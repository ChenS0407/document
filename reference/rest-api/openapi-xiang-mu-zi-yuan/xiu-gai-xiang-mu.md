# 修改项目

### 请求方法/请求路径

#### PUT  /apigw-app/v3/projects/{projectId}

### 资源描述

#### 修改项目

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |
| X-DEVOPS-UID | string | 是 | userId |  |
| X-DEVOPS-ACCESS-TOKEN | string | 否 | access\_token |  |

#### Body参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| body | [项目-修改模型]() | 是 | 项目信息 |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型Boolean]() |

#### 请求样例

```javascript
curl -X PUT '[请替换为API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
X-DEVOPS-UID: {X-DEVOPS-UID}
X-DEVOPS-ACCESS-TOKEN: {X-DEVOPS-ACCESS-TOKEN}
```

### 返回样例-200

```javascript
{
  "data" : true,
  "message" : "String",
  "status" : 0
}
```

## 项目-修改模型

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| centerId | integer | 否 | 中心ID |
| deptName | string | 否 | 部门名称 |
| englishName | string | 否 | 英文缩写 |
| ccAppName | string | 否 | cc app name |
| kind | integer | 否 | 容器选择， 0 是不选， 1 是k8s, 2 是mesos |
| projectType | integer | 否 | 项目类型 |
| deptId | integer | 否 | 部门ID |
| description | string | 否 | 描述 |
| bgId | integer | 否 | 事业群ID |
| secrecy | boolean | 否 | 是否保密 |
| bgName | string | 否 | 事业群名字 |
| projectName | string | 否 | 项目名称 |
| ccAppId | integer | 否 | cc app id |
| centerName | string | 否 | 中心名称 |

## 数据返回包装模型Boolean

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | boolean | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

