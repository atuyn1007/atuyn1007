# 本地交互式产品说明书

把可操作的 Demo 与详细设计说明放在一起，方便产品经理向后端和 UI/UX 设计师演示、交接与迭代需求。

左侧是可以实际操作的产品原型，右侧是对应的设计与业务说明。点击按钮、打开弹窗或切换页面时，说明随交互切换；也可以通过目录单独查看某一项规格。

## 说明包含什么

- 场景与触发条件：入口、前置条件和操作限制。
- 页面组成与交互：页面层级、弹窗、遮罩、按钮文案和跳转。
- 状态与异常：加载、成功、失败、空状态及恢复方式。
- 业务与数据规则：需要读写的数据、权限、状态含义和后端校验。
- 验收标准：可观察的预期行为，以及需要真实接口验证的内容。

示例行为、建议方案和待确认规则会在相关正文中区分，避免把原型行为误当成正式业务规则。界面保留主要内容和功能，不添加重复的小字、标签或教学提示。

## 本地编辑与版本分享

1. 打开编辑版，操作左侧 Demo，并点击「编辑说明」修改右侧文字。
2. 点击「保存新版本」，生成包含最新说明的编辑版 HTML。
3. 文件内记录版本号和更新时间，文件名可以自行重命名。
4. 点击「导出查看版」，把对应保存版本的文件发给同事。

查看版保留 Demo、说明目录和版本信息，隐藏编辑工具。文件内嵌所需内容，用浏览器直接打开，无需部署网站。已经发送的文件保留当次版本；后续修改后重新保存、导出和发送。

保存默认通过浏览器下载新文件，不会静默覆盖原文件，也不依赖浏览器缓存保存说明。查看版隐藏编辑入口，不提供防篡改或保密保证。

## Codex Skill

Skill 名称为 `local-interaction-spec`，仅在明确选择或点名时启用。未选择时，普通 Demo 按正常方式制作。

调用示例：

> 使用 $local-interaction-spec，根据这份需求制作一个左侧可操作、右侧可编辑说明的本地 Demo，支持保存版本和导出查看版。

当前提供活动报名小样，演示报名确认、成功反馈、失败重试和空记录状态。小样没有连接真实后端；演示报名记录只存在于当前页面内存，说明文件版本与业务记录分别处理。


## 安装到 Codex

这是一个 Codex Skill 指令包，安装后用于指导 Codex 制作文件，不是安装后直接打开的独立编辑器。

### 方法一：让 Codex 帮你安装（推荐）

把下面这句话复制给 Codex：

> 使用 $skill-installer，从 https://github.com/atuyn1007/atuyn1007/tree/main/skills/local-interaction-spec 安装 local-interaction-spec Skill。

安装完成后，在下一轮对话中选择该 Skill；若当前客户端尚未显示它，可重新打开 Codex。

### 方法二：手动下载

1. [下载仓库 ZIP](https://github.com/atuyn1007/atuyn1007/archive/refs/heads/main.zip) 并解压。
2. 找到 `skills/local-interaction-spec` 文件夹，将整个文件夹复制到 Codex 的个人 Skills 目录：
   - Windows：`%USERPROFILE%\.codex\skills\local-interaction-spec`
   - macOS / Linux：`~/.codex/skills/local-interaction-spec`
   - 如果设置了 `CODEX_HOME`，使用 `$CODEX_HOME/skills/local-interaction-spec`。
3. 确认 `SKILL.md` 位于该文件夹第一层，不要多套一层文件夹；已有同名 Skill 时先备份再替换。
4. 在下一轮对话中选择 Skill；未显示时重新打开 Codex。

完整安装文件结构：

```text
local-interaction-spec/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── local-files.md
    └── spec-content.md
```

### 安装后使用

选择“本地交互式产品说明书”，或在消息里输入：

> 使用 $local-interaction-spec，帮我做一个活动报名小 Demo，左侧可以操作，右侧有可编辑的详细说明，支持保存新版本和导出查看版。

它仅在明确选择或点名时启用；普通 Demo 请求不会自动套用这个格式。无需额外安装第三方包。生成与验证 Demo 需要 Codex 当前环境支持相应文件和浏览器操作。

[查看完整 Skill 文件](skills/local-interaction-spec/SKILL.md)
