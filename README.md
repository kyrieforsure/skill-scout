# skill-scout

> 一个给 DSH 用的 skill：当已装技能覆盖不了当前任务时，自动去技能市场 / skills.sh / GitHub / npm 找现成的 skill 或插件，按硬门槛评估、做装前审计，装完在真实任务上接入实测，最后汇报来源与风险。

## 它能做什么

一条七步链：

1. **查已装** —— 先做负向检查，避免重复装
2. **写缺口** —— 把缺的能力写成一句话再搜
3. **检索** —— 本地市场 → skills.sh → ClawHub / SkillHub → GitHub → npm
4. **硬门槛** —— 6 条，任一不过就不装
5. **装前审计** —— 指令注入 / 外连 / 敏感读取 / 越界写 / 混淆 / 提权
6. **安装** —— 技能目录 / 市场导入 / 插件，三种形态
7. **接入实测** —— 在真实第一段任务上跑，装没装对以实测为准

外加：按能力缺口计数的安装数量上限、多技能组合、反面清单、自我迭代约定。

## 安装

把 `SKILL.md` 放到 DSH 的技能发现目录之一：

- `~/.agents/skills/skill-scout/SKILL.md`
- 或 `~/.dsh/skills/skill-scout/SKILL.md`

下个会话（或重启 DSH）后，catalog 里就会出现 `skill-scout`。

## 配合的插件（可选）

skill-scout 本身只靠公网 API 就能检索；以下插件能让「搜 + 装 + 审计」更顺手：

- `dsh-skill-hub` —— 市场面板 + GitHub 扫描 + 装前字节审计 + commit pin
- `dsh-skill-market` —— SkillHub + ClawHub 双源搜索

## 其他 agent

这是给 DSH 写的。用在 Claude Code / 其他 agent 上时，路径和工具名要小改（如 `~/.claude/skills`），但流程完全通用。

## License

[MIT](./LICENSE)
