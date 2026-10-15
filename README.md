# 烬火之门

一个可直接在手机浏览器或微信内打开的回合制战斗原型。页面仅显示游戏、血条和操作按钮。

点击右下角技能，或在电脑上按 1–4。普通攻击回蓝积怒，守势抵御首领每第 3 回合的重击，满怒后可释放终式。

## 发布

本项目为静态网站。GitHub Pages 的发布源设为默认分支的根目录。无需构建、服务器或 API Key。

## 视频素材

战斗视频通过 assets/videos.json 自动加载。将视频放入 assets/videos/，再在清单的 clips 中配置：

```json
{"idle":{"src":"videos/idle.mp4","impact":0.5},"attack":{"src":"videos/attack.mp4","impact":0.47}}
```

clips 支持 idle、attack、fire、guard、ultimate、enemy_attack、enemy_heavy、victory、defeat。src 相对于素材清单地址；impact 为命中时刻占视频总时长的比例。素材自动加载，不需要玩家手动导入。没有可用视频画面时才使用程序占位动画，该占位动画并非 AI 生成视频。

视频默认静音并在网页内播放；首次触摸后的播放行为仍取决于手机浏览器。竖屏使用完整视频画面，避免裁掉左右角色。切换时保留上一帧，缺失或失败的片段不会闪回占位动画。

所有战斗规则在客户端执行，适合单机原型，不包含账号、付费或排行榜。
