# DSH Agent Presets · 灵犀 & 天工

DeepSeek Harness 的 Agent 预设集合：一个人格化伙伴「灵犀」，一个多智能体编排者「天工」。

## 预设一览

| 预设 | 类型 | 特点 |
|---|---|---|
| 灵犀 lingxi | 人格模式 | 长线搭档：记忆纪律（开工回忆 / 干活记录 / 收工留档）、语气锚点（先结论、三层确定性、口头禅）、边界条款 |
| 天工 tiangong | 编排模式 | Supervisor：拆解 → 并行委派 → 汇总 → 复核；规模选择表；任务书模板；交付格式 |

## 快速开始

1. 安装 DeepSeek Harness。
2. 把预设目录复制到用户预设根：

   ```bash
   cp -R presets/lingxi ~/.dsh/.agent-presets/lingxi
   cp -R presets/tiangong ~/.dsh/.agent-presets/tiangong
   ```

3. 新建会话时，在预设选择器中选择「灵犀」或「天工」。

## 灵犀的记忆依赖（可选）

灵犀的记忆纪律基于灵枢认知图（`@furongjun1999/dsh-memory`）。未安装时灵犀照常工作，只是记忆笔记功能不可用。

## 目录结构

```
presets/
  lingxi/                      # 人格化伙伴（开源版）
    agent.cordis.yml           # persona + 标准工具 + 自定义技能目录
    preset.yml
    skills/lingxi-memory/SKILL.md          # 记忆工作流
  tiangong/                    # 多智能体编排者
    agent.cordis.yml
    preset.yml
    skills/tiangong-orchestration/SKILL.md # 编排手册
```

## 说明

- 灵犀开源版为通用版；作者私人部署中的个性化教练层（含个人履历与合作锚点）有意未包含。
- 想蒸馏自己的专属人格？推荐 [花叔 nuwa-skill](https://github.com/alchaincyf/nuwa-skill)（MIT）。
- 两个预设均基于 DeepSeek Harness 出厂 `standard` 预设定制，仅改动 persona 文本与技能目录。

## 使用场景

**灵犀 — 陪伴与精进**
- 需要长期记忆的搭档：动手前先回忆认知图里的约定与踩过的坑，边干活边沉淀
- 学习陪练与复盘：先结论、三层确定性（实测 / 文档 / 推断分得开）、给地图不给碎片
- 日常技术讨论与多格式交付（Markdown / HTML / Excel / PDF）

**天工 — 复杂任务编排**
- 需要拆解的大任务：审计一整个项目、并行调研多个主题、多文件迁移
- 交付风格：总览 → 结论 → 分项 → 遗留问题；结论标注 verified / inferred / unverified
- 规模判断：小活自己干；1-2 个包 subagent 并行；多包多阶段 workflow；多轮迭代 ralph

**两者怎么配合**
- 开「天工」会话跑大任务，开「灵犀」会话做规划、复盘与个人精进
- 灵犀沉淀进认知图的约定与坑，天工做拆解与交付——同一套记忆工具，两个视角

## License

MIT
