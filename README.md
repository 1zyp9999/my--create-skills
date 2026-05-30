# my-create-skills

这里存放我自己编写的 Claude Code Skills 合集，持续更新中。

## Skills 列表

### [write-skill](./write-skill)

从零创建高质量 Skill 文件的脚手架工具。通过引导式问答收集 Skill 的触发场景、核心行为和约束边界，自动生成符合规范的 SKILL.md 文件，包含 frontmatter、HARD-GATE 强制阻断、You MUST/Do NOT 纪律声明、流程图和 PASS/FAIL 判定标准。与 eval-skill 组成 Write→Eval 闭环工作流。

**触发词**：写个 skill、创建 skill、新建 skill、帮我写一个 skill、skill 脚手架

---

### [eval-skill](./eval-skill)

对 Skill 文件执行完整红队压力测试的评测工具。按 TDD 循环（RED → GREEN → REFACTOR）工作：先用弹药库对 Skill 发起攻击并逐字记录 Agent 回复，再按四维评分体系（Description 路由、Token 工程、防绕过强度、结构可读性，满分 14）打分，最后针对失败场景做最小 Patch 并复测验证，输出 HTML 可视化报告（雷达图 + 场景卡片 + 前后对比）。

**触发词**：评测 skill、测试我的 skill、skill 评分、跑一下这个 skill

---

### [cpp-code-review](./cpp-code-review)

C++ 代码审查与调试 Skill。按 P0→P1→P2→P3 优先级逐项扫描代码，每发现一个问题立即暂停报告并等待用户确认后再修复，严禁批量处理或擅自改动。覆盖内存错误（越界/use-after-free/double free）、未定义行为（悬垂指针/未初始化变量）、资源泄漏、线程安全、逻辑错误、异常安全等问题，内置借口反制表应对"紧急/直接改/信任你"等绕过尝试，禁止 pragma 压制警告等治标方案。

**触发词**：review 这段 C++ 代码、帮我调试、检查内存问题、C++ bug

---

## 更新记录

| 日期 | Skill | 变更内容 |
|------|-------|---------|
| 2026-05-30 | cpp-code-review | eval-skill 评测后 Patch：补全 You MUST/Do NOT/Process Flow/PASS-FAIL 五元素，删除与借口反制表重叠的「常见陷阱」节，减少约 30% 冗余 token |
| 2026-05-30 | cpp-code-review | 初始上传 |
| 2026-05-30 | write-skill | 初始上传 |
| 2026-05-30 | eval-skill | 初始上传 |
