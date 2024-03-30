# nonebot-plugin-kanonbot

KanonBot - nb2 插件版

目前仍在移植中

## 安装

（以下方法三选一）

默认为adapter-qq。如需其他适配器请下载文件，在adapters文件夹找到对应文件，更改名字为`__init__.py` 并覆盖插件文件中的文件

一.使用插件文件安装：（推荐）

1.下载 nonebot\_plugin\_kanonbot 文件夹，放到 plugins 文件夹内。

2.在 pyproject.toml 的 plugin\_dirs 中添加 "plugin" 使其可以顺利加载。

    plugin_dirs = ["plugins"]

二.命令行安装：

    nb plugin install nonebot-plugin-kanonbot

三.pip 安装：

1.执行此命令

    pip install nonebot-plugin-kanonbot

2.修改 pyproject.toml 使其可以加载插件

    plugins = [”nonebot-plugin-kanonbot“]

## 配置

在 nonebot2 项目的`.env`文件中选填配置

1.配置管理员账户

    SUPERUSERS=["12345678"] # 配置 NoneBot 超级用户

2.插件数据存放位置，默认为 “./KanonBot/”。

    kanonbot_basepath="./KanonBot/"

在 KanonBot 文件夹 的 kanon\_config.toml 文件中选填配置

```
[kanon_api]
# KanonAPI的url，非必要无需修改。
url = "http://cdn.kanon.ink"
# 是否开启API来获得完整功能，默认开启。
# （理论上，目前部署kanon必须开启）
state = true

[emoji]
# 是否开启emoji的功能。默认开启。
# 需要下载emoji.db.7z文件并解压至"{kanonbot_basepath}file"文件夹才会生效
state = true
# emoji的加载方式。
# "file"：加载本地文件
mode = "file"

[botswift]
# 是否开启仅1个bot响应功能。默认关闭。
# 开启后，同一个群内仅1个bot会响应。只有在第一个bot在10次没回应的时候，第二个bot才会开始响应。
# 注：10次为所有群总计
state = false
# 忽略该功能的频道号(填写方式参考下面黑白名单的名单规则)
ignore_list = ["channel_qq_123456"]

[plugin]
# 频道黑白名单
# 不在名单内则继续，同时在名单内不会运行
# 名单规则：[f"channel_{platform}_{channel_id}", f"group_{platform}_{group_id}", f"private_{platform}_{user_id}"]
channel_white_list = []
channel_black_list = []
# 用户id，为unity_id，并非真实id。对应id在config.db的id_list表中查看。
# 不在名单内则继续，同时在名单内不会运行
user_black_list = []  # 用户白名单
user_white_list = []  # 用户黑名单
# at消息包含有机器人列表的机器人话，则不运行
bot_list = []
# 记录运行日志
log = false

[image_api]
# 自部署的图床api，部署方法在 /developer/图床/图床部署方法.md 。
url = "http://127.0.0.1:8081"
# 请按照实际填入ip地址与端口。
# 127.0.0.1可填ip或域名都行，需要在外部可访问。
# 8081为端口号，如未修改图床端口则默认8081

[plugin_cck]
# 发送方式
# 为1时，文字和图片分开发送；为2时，文字绘制成图片，和cck图片一起发送
draw_type = 1


```

## 已有功能：

*   [x] 塔罗牌

*   [x] 签到

*   [x] 水母箱

*   [x] emoji

*   [x] 喜报/悲报

*   [x] 表情：一直（仅频道，或绑定qq的用户）

*   [x] 表情：摸摸（仅频道，或绑定qq的用户）

*   [x] 表情：可爱（仅频道，或绑定qq的用户）

*   [x] 表情：结婚（仅频道，或绑定qq的用户）

*   [x] 猜猜看

*   [x] 炸飞机

*   [x] 多bot保活（1个群只相应1个bot，bot寄了就顶上）

*   [x] 指令冷却

## 交流

*   交流群[鸽子窝里有鸽子（291788927）](https://qm.qq.com/cgi-bin/qm/qr?k=QhOk7Z2jaXBOnAFfRafEy9g5WoiETQhy\&jump_from=webapi\&authKey=fCvx/auG+QynlI8bcFNs4Csr2soR8UjzuwLqrDN9F8LDwJrwePKoe89psqpozg/m)

*   有疑问或者建议都可以进群唠嗑唠嗑。

