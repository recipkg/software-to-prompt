# software-to-prompt

将已有软件、GitHub 仓库或可观察产品提炼成纯 Markdown 软件配方，记录行为、递归依赖和验收条件。用于软件到提示词、保存重建说明或迁移现有软件的需求。

Read [SKILL.md](SKILL.md) for the workflow and linked resources. This is the canonical standalone skill repository used by [Recipkg](https://github.com/recipkg/recipkg).

For stateful updates, observe the complete before-and-after state using isolated data, including relevant omitted or empty fields, permissions and persistence. Record the tested interface and leave untested cases unknown.

For multi-user or machine-authenticated workflows, check identity, tenant binding and permissions per entry point; management and chat APIs may differ. Use isolated accounts and mark source-only or untested cases clearly.

When encoding, binary data or numeric precision matters, preserve the relevant input bytes and build configuration, and compare without erasing observable type or precision differences.

## Use as a project submodule

```sh
git submodule add https://github.com/recipkg/software-to-prompt.git .agents/skills/software-to-prompt
git submodule update --init --recursive
```

Keep the same repository across projects. Review upstream changes and local work before checking out a new commit, then explicitly commit the consumer gitlink. Do not copy and hand-maintain a second skill or overwrite custom modifications.

This repository is also a Markdown-only Recipkg skill recipe: validate with `recipkg check .`, then pack it outside this directory. [License](LICENSE.md).

## 中文

本仓库只维护 `software-to-prompt` 技能。不同项目应把此同一仓库作为固定提交的 Git 子模块引用，不复制技能正文。修改先回本仓库，再更新项目指针；注意保护本地改动。技能入口与说明见 [SKILL.md](SKILL.md)。

对有状态更新，用隔离数据观察完整的更新前后状态，并按需检查省略或空字段、权限和持久化；记录实际测试的接口，未测的情况保持未知。

对多用户或机器身份工作流，分别检查各入口的身份、租户绑定和权限；管理和聊天接口可能不同。使用隔离账户，明确标记仅有源码证据或尚未测试的情况。

涉及编码、二进制或数值精度时，保留相关输入字节和构建配置，比较时避免抹掉可观察的类型或精度差异。
