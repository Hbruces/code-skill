# Code Skill — CodeWhale 编码规范技能包

CodeWhale 技能集合，为 AI 编码提供系统化的约束框架和可操作规则。

## 包含内容

- **[CodeConstitution](./CodeWhale/CodeConstitution/SKILL.md)** — 编码宪法。以 Karpathy 工程哲学为根基，定义「安全 → 可观测 → 可读 → 性能 → 极简」五层优先级栈，提供约束仲裁、审查锚点、遗留代码适配等元规则。
- **[CodeRules](./CodeWhale/CodeRules/SKILL.md)** — 编码规则速查。覆盖 250+ 条可操作的工程编码约束，按编码流程、代码风格、安全合规、架构模块、分布式运维、产业专项等维度表格化组织。
- **[frontend-design](./CodeWhale/frontend-design/SKILL.md)** — 前端设计指南。覆盖设计方向选择、字体搭配、色彩系统、动效动画、空间构图、响应式布局、无障碍和反模式规避，指导生成辨识度高的生产级前端界面。
- **[karpathy-guidelines](./CodeWhale/karpathy-guidelines/SKILL.md)** — Karpathy 编码行为指南。以 Andrej Karpathy 的 LLM 编码观察为基础，提供"先思考再编码"、"极简优先"、"外科手术式修改"、"目标驱动执行"四项行为准则，减少常见 AI 编码错误。
- **[Skill 安装成本估算](./CodeWhale/Skill安装成本估算.md)** — 加载该技能包对响应速度、上下文占用和 API 成本的量化分析。

## 使用场景

- 生成任何面向生产环境的代码
- 修改/重构现有代码时确保不改坏既有逻辑
- 编写测试用例、CI/CD 配置、Dockerfile、脚本
- 架构设计和技术方案输出

## 核心理念

```
安全/正确性 > 可观测性 > 可读性 > 性能 > 极简性
```

低优先级让步时须注释豁免理由。
