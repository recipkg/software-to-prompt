# software-to-prompt

将已有软件、GitHub 仓库或可观察产品提炼成纯 Markdown 软件配方，记录行为、递归依赖和验收条件。用于软件到提示词、保存重建说明或迁移现有软件的需求。

Read [SKILL.md](SKILL.md) for the workflow and linked resources. This is the canonical standalone skill repository used by [Recipkg](https://github.com/recipkg/recipkg).

For stateful updates, observe the complete before-and-after state using isolated data, including relevant omitted or empty fields, permissions and persistence. Record the tested interface and leave untested cases unknown.

For stateful startup and recovery, distinguish a live process, a reachable listener and readiness after data loading. Wait only for observed transient states within a bound; unexpected errors and timeouts remain failures. A normal restart does not prove crash recovery.

For agent tools and skills, compare declared read-only or idempotent hints with isolated actual calls, repeated effects, errors and what the model receives. Record conflicts and security mechanisms that were not tested.

For recoverable agent tasks, check observable effects and model context when failures happen before and after tool execution and around result persistence. A model that does not repeat a call cannot establish idempotency or exactly-once execution.

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

验证有状态服务启动和恢复时，区分进程存活、监听可连接和数据加载完成后可服务请求。只对已观察的临时状态做有界等待；意外错误和超时仍是失败，正常重启不证明崩溃恢复。

对 Agent 工具和技能，用隔离调用检查声明的只读、幂等属性与真实副作用、重复执行、错误及模型可见结果是否一致；记录冲突和未测试的安全机制。

对可恢复的 Agent 任务，检查工具执行前后及结果持久化边界的失败、副作用和模型上下文；模型没有重复调用不能证明幂等或恰好执行一次。

对多用户或机器身份工作流，分别检查各入口的身份、租户绑定和权限；管理和聊天接口可能不同。使用隔离账户，明确标记仅有源码证据或尚未测试的情况。

涉及编码、二进制或数值精度时，保留相关输入字节和构建配置，比较时避免抹掉可观察的类型或精度差异。
