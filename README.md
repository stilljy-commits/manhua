# 柏宝绘漫画分镜轻改

为 ST-BaiBai-Image 提供 2～3 格正文漫画插图的提示词与可选模式补丁。适配本次核验的上游 0.3.2。已验证提示词解析和 NAI 请求拼装，尚未实际出图或执行完整项目构建。

## 文件

- `presets/`：NAI 规范、思维链与漫画负面词。
- `patches/baibai-comic-light.patch`：修正固定任务合同，只有规范包含 `[BAIBAI_COMIC_LIGHT_V1]` 时启用。
- `examples/`：测试剧情及提示词样例；样例由本次助手按规范编写，非用户副 API 实测输出。
- `安装与验证.txt`：详细安装、验证及回退说明。

## 使用

1. 在 ST-BaiBai-Image 源码根目录应用补丁：`git apply --ignore-space-change /path/to/baibai-comic-light.patch`。
2. 安装依赖并构建：`pnpm install`、`pnpm build`。把构建后的 `dist/index.js` 放回酒馆扩展目录，刷新酒馆。
3. 在柏宝绘自定义提示词中分别粘贴 `presets/` 中的 NAI 规范和思维链。
4. NAI 开启「生成自然语言」，画幅锁定竖屏。把漫画负面词填到实际生效的画师配方或渠道负面词字段。
5. 重新生成 tag 后检查各格内容，再决定是否出图。

## 更新

本仓库保存补丁和配置，不是可直接填写进酒馆扩展安装框的完整扩展。拉取更新后，提示词需重新粘贴；代码补丁须按新版本检查差异并重新构建。若需要酒馆内一键更新，应维护完整扩展分支并发布构建后的 `dist`。

参考上游：[ST-BaiBai-Image](https://github.com/baibai-git/ST-BaiBai-Image)。
