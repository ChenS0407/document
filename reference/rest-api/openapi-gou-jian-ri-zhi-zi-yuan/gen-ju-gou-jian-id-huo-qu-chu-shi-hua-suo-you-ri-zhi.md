# 根据构建ID获取初始化所有日志

### 请求方法/请求路径

#### GET  /apigw-app/v3/projects/{projectId}/pipelines/{pipelineId}/builds/{buildId}/logs/init

### 资源描述

#### 根据构建ID获取初始化所有日志

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| debug | boolean | 否 | 是否包含调试日志 |  |
| tag | string | 否 | 对应elementId |  |
| jobId | string | 否 | 对应jobId |  |
| executeCount | integer | 否 | 执行次数 |  |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-UID | string | 应用态必须 | 用户名 |  |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |
| pipelineId | string | 是 | 流水线ID |  |
| buildId | string | 是 | 构建ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | [数据返回包装模型日志查询模型](gen-ju-gou-jian-id-huo-qu-chu-shi-hua-suo-you-ri-zhi.md) |

#### 请求样例

```javascript
curl -X GET '[请替换为API地址栏请求地址]?debug={debug}&amp;tag={tag}&amp;jobId={jobId}&amp;executeCount={executeCount}&amp;app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-UID: {X-DEVOPS-UID}
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
```

### 返回样例-200

```javascript
{
  "data" : {
    "timeUsed" : 0,
    "hasMore" : true,
    "subTags" : "string",
    "buildId" : "String",
    "finished" : true,
    "logs" : [ {
      "subTag" : "String",
      "jobId" : "String",
      "lineNo" : 0,
      "tag" : "String",
      "message" : "String",
      "priority" : "String",
      "executeCount" : 0,
      "timestamp" : 0
    } ],
    "status" : 0
  },
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型日志查询模型

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | [日志查询模型](gen-ju-gou-jian-id-huo-qu-chu-shi-hua-suo-you-ri-zhi.md) | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 日志查询模型

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| timeUsed | integer | 否 | 所用时间 |
| hasMore | boolean | 否 | 是否有后续日志 |
| subTags | List | 是 | 日志子tag列表 |
| buildId | string | 是 | 构建ID |
| finished | boolean | 是 | 是否结束 |
| logs | List&lt;[日志模型](gen-ju-gou-jian-id-huo-qu-chu-shi-hua-suo-you-ri-zhi.md)&gt; | 是 | 日志列表 |
| status | integer | 否 | 日志查询状态 |

## 日志模型

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| subTag | string | 是 | 日志子tag |
| jobId | string | 是 | 日志jobId |
| lineNo | integer | 是 | 日志行号 |
| tag | string | 是 | 日志tag |
| message | string | 是 | 日志消息体 |
| priority | string | 是 | 日志权重级 |
| executeCount | integer | 是 | 日志执行次数 |
| timestamp | integer | 是 | 日志时间戳 |

