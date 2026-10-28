# software-to-prompt

将已有软件、GitHub 仓库或可观察产品提炼成纯 Markdown 软件配方，记录行为、递归依赖和验收条件。用于软件到提示词、保存重建说明或迁移现有软件的需求。

Read [SKILL.md](SKILL.md) for the workflow and linked resources. This is the canonical standalone skill repository used by [Recipkg](https://github.com/recipkg/recipkg).

## Use as a project submodule

```sh
git submodule add https://github.com/recipkg/software-to-prompt.git .agents/skills/software-to-prompt
git submodule update --init --recursive
```

Keep the same repository across projects. Review upstream changes and local work before checking out a new commit, then explicitly commit the consumer gitlink. Do not copy and hand-maintain a second skill or overwrite custom modifications.

This repository is also a Markdown-only Recipkg skill recipe: validate with `recipkg check .`, then pack it outside this directory. [License](LICENSE.md).

## 中文

本仓库只维护 `software-to-prompt` 技能。不同项目应把此同一仓库作为固定提交的 Git 子模块引用，不复制技能正文。修改先回本仓库，再更新项目指针；注意保护本地改动。技能入口与说明见 [SKILL.md](SKILL.md)。
