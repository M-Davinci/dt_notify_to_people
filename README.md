# Sentry DingTalk Notify People

Sentry 集成钉钉机器人通知，并且通知人员 <br>
本插件是基于[sentry-dingtalk-notify](https://github.com/lanxuexing/sentry-dingtalk-notify) 进行的二次开发，加上了自定义的需求。这也是本人第一次开发的插件，很开心，Python功力又提升一丢丢。

## Requirments 
- sentry >= 21.5.1

## 特性
- 发送异常通知到钉钉
- 支持钉钉机器人webhook设置关键字
- 支持通知到具体的用户
- 配置环境变量
  - DINGTALK_WEBHOOK: Optional(string)
  - DINGTALK_CUSTOM_KEYWORD: Optional(string)
  - DINGTALK_PHONES: Optional(string)
## 快速使用
### 安装
1. 使用 `pip` 命令
    ```bash
    $ pip install dt-notify-to-people
    ```

2. 写入依赖文件 `onpremise-xxx/sentry/requirements.txt`
    ```bash
    $ echo dt-notify-to-people >> requirements.txt
    ```

### 钉钉机器人
[配置](https://developers.dingtalk.com/document/app/custom-robot-access)钉钉机器人并拿到对应的 webhook, 可以对机器人设置 关键词、签名、IP限制

### 配置
1. Sentry安装项目下的requirements.txt，添加dt-notify-to-people==1.0.2；
2. 在 Sentry 面板 Settings > Integrations 中找到 DingTalk 并配置 webhook、关键词等信息，添加项目，创建告警规则；

#### 关于插件编写

1. 具体教程可以阅读这边文章[《如何开发自己的Python库》](https://zhuanlan.zhihu.com/p/60836179?utm_source=wechat_session&utm_medium=social&s_r=0)；

2. 编写自己的插件代码；

3. 打包自己的插件代码：

   ```
   python setup.py sdist bdist_wheel
   ```

4. 上传自己的插件：

   ```
   twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
   ```

   
