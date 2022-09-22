# 中控机
中控机相当于蓝鲸、蓝盾的控制台。 bkcli 命令只可以在中控机上执行。
任意蓝鲸/蓝盾机器执行 ```cat /data/install/.controller_ip ```  可以获取中控机的IP

---

# 流水线ID

流水线url中，pipeline后的参数分别为项目id和流水线id。如：http://devops.bktencent.com/console/pipeline/iccentest/p-8f3d1b399897452e901796cf4048c9e2/history 中，iccentest 为项目id，p-xxx 即为流水线id。



# 构建日志

构建日志存放在构建机中，构建日志存放的路径位于：

**私有构建机**：{agent 安装目录}/logs/{构建号}

**公共构建机**：/data/bkce/logs/ci/docker/{构建号}



**私有构建机中，agent安装目录怎么看**：

蓝盾---环境管理---节点---{对应使用的构建机}---安装路径

![agent安装目录](../../.gitbook/assets/build_log_url.png)

**构建号怎么看**：

流水线 URL 中，最后一串以 b- 开头的字符串即为构建号

![构建号](../../.gitbook/assets/build_id.png)

# 服务日志

进入蓝盾后台服务机器

```find /data/bkce/logs/ci/ -name \*-devops.log -o -name \*-devops-error.log |xargs tar zcvf /root/bkci-log.tar.gz```

然后发送打包好的 **/root/bkci-log.tar.gz** 日志



# 页面报错信息

如遇到页面报错，浏览器 F12 打开控制台后再复现一次请求操作，并且：

①、打开 network 标签，点击错误的请求并截图。

![error_request](../../.gitbook/assets/error_request.png)



②、打开 console 标签，并截图。

![error_console](../../.gitbook/assets/weberror_console.png)



