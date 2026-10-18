# investigate-first

动手前先查"已经有什么"的通用 agent skill：写代码前、遇到问题时，先摸一遍项目文档 / GitHub 相似仓库 / 用户参考 / 公开源码（或 REA 逆向）/ 自己代码库，再决定怎么做。

## 它做什么

- **触发强度分三档**：遇到问题（报错/卡住/行为异常）**必须**先查；要写代码/改项目**推荐**先查（小改动可跳）；纯问答、纯文字任务、用户说"不用查"时**不用**
- **检查五问**（有就先读，查到够支撑决策就停）：
  1. 这个项目有说明书吗（README/docs/AGENTS.md，项目内规则优先级最高）
  2. GitHub 上有相同/类似功能的仓库吗（轮子 + issues 里别人踩的坑）
  3. 用户给过参考吗（对话里贴的链接/文档/示例/口述偏好）
  4. 是在改公开项目吗（是 → 直接读源码；拿不到源码的二进制 → REA 逆向）
  5. 是自己的代码库吗（相关模块、git log、已有注释/测试）
- **输出侦察结论**（5~10 行）：找到了什么（标来源）、没找到什么、对手头方案的影响——查是为了决策，不是为了写报告
- 所有规则是推荐基线，token 余量紧时先窄后宽；查不动的一问答"没查"就行，不阻塞动手

## 安装

本仓库布局即 skill 目录布局（`SKILL.md` 在根目录），**clone/拷到 skills 目录下的 `investigate-first/`** 即可：

| 工具 | 装到哪 |
|---|---|
| ZCode（全局） | `~/.agents/skills/investigate-first/` |
| 其他支持 `.agents/skills` 的工具 | `<skills目录>/investigate-first/` |

```bash
git clone https://github.com/xlb276/investigate-first-skill ~/.agents/skills/investigate-first
```

放不进去时按 SKILL.md 里"通用性说明"一节处理。

## 目录

```
investigate-first/
├── SKILL.md                     # 触发三档 + 五问 + 输出要求
└── references/
    └── checklist-detail.md      # 各信息源查法细则（GitHub 搜法/读文档/REA/git log/token 经济）
```

## 许可

未附 LICENSE。如需复用请自行协商；欢迎 PR。
