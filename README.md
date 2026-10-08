# LocalDream-ET 评分数据仓

本仓库仅用于存储 LocalDream ET 官网（https://etc.tw.kg）的匿名评分。

- 公开只读：官网与管理员后台经 GitHub 公开接口匿名读取 summary.json 与 ratings/，无需令牌即可看到实时平均分/人数/分布。
- 写入受控：新增/删除评分只由部署在边缘函数内的服务端逻辑用环境变量令牌完成，前端不含密钥。
- 去重：每台设备一个稳定指纹哈希，一票对应 ratings/<sha256>.json；重复提交不新增、返回原评分。清缓存/换设备视为新设备。
- 字段：{score(1-5), country, prov, model, ua, ts}；只存指纹哈希与粗略地区/机型。

Copyright (C) 2026 etc · ET
