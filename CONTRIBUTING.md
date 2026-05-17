# 🌟 贡献指南

感谢你对 **念念 (NianNian)** 的关注！

无论你是发现了 bug、有功能建议，还是想提交代码，都欢迎参与。

---

## 🐛 报告 Bug

1. 先搜索 [Issues](https://github.com/BlakeYa/niannian/issues) 看看是否已被报告
2. 如果不存在，[新建一个 Issue](https://github.com/BlakeYa/niannian/issues/new)
3. 描述中请包括：
   - 使用的浏览器和版本
   - 重现步骤
   - 期望行为和实际行为
   - 控制台的错误信息（如果有）

## 💡 功能建议

在 [Issues](https://github.com/BlakeYa/niannian/issues/new) 中描述你的想法，包括：

- 这个功能解决什么问题
- 使用场景是什么
- 你期望的交互方式

## 🛠️ 提交 PR

1. Fork 本仓库
2. 创建你的特性分支：`git checkout -b feat/my-feature`
3. 提交你的改动
4. 确保单 HTML 文件在浏览器中能正常工作
5. 推送到你的 Fork：`git push origin feat/my-feature`
6. 创建一个 Pull Request

### 开发注意事项

- 念念是 **单 HTML 文件** 应用，所有代码（HTML/CSS/JS）都在 `index.html` 中
- 农历转换库 `solarlunar` 内联在 HTML 中，修改后需重新内联
- 避免引入外部依赖（CDN、字体、分析脚本等），以保持隐私优先的定位
- 使用系统字体栈，不要添加 Google Fonts 等远程字体
- 测试时可用 `file://` 协议直接在本地打开 HTML 文件
- 提交前确认 `solarlunar` 库能正确加载（`window.solarlunar.default.lunar2solar`）

### 代码风格

- HTML 属性顺序：`id` > `class` > `data-*` > 其他属性
- CSS 类名使用 kebab-case
- JavaScript 使用 camelCase，`const` > `let` > `var`
- 字符串使用单引号
- 不要移除 section 标记注释（`<!-- ======== Xxx ======== -->`），它们帮助在 1600+ 行单文件中导航

---

## 📜 行为准则

### 我们的承诺

为了营造开放和友好的社区，我们承诺尊重所有贡献者，无论其经验水平、性别、种族、宗教等。

### 我们的标准

**积极的行为：**
- 使用友好和包容的语言
- 尊重不同的观点和经验
- 优雅地接受建设性批评

**不可接受的行为：**
- 性骚扰或性别歧视语言
- 人身攻击或煽动性评论
- 未经明确许可发布他人的隐私信息

### 执行

项目维护者有权删除、编辑或拒绝不符合本行为准则的 Issue、PR 和评论。

---

## 🙏 致谢

念念始于一个简单的愿望：不要再忘记妈妈的生日。每一个贡献者都在帮助更多人记住他们重要的人。

> **念念不忘，必有回响。**
