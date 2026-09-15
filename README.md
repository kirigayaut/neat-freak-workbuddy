# neat-freak（洁癖）— WorkBuddy 版

> 干完活跑一下 `/neat`，把这次会话改的东西跟项目文档、AGENTS.md、WorkBuddy 项目记忆全部对齐一遍，最后给你一份变更摘要。

本仓库是 [卡兹克 neat-freak v3.0.0](https://github.com/KKKKhazix/khazix-skills/tree/main/neat-freak)（MIT）的 WorkBuddy 适配版。上游的五步流程、变更影响矩阵、毕业机制、清场 gate 全部原样保留，只改了与 WorkBuddy 平台咬合的 4 个接口点。

## 和上游的差异

| 位置 | 适配内容 |
|---|---|
| `SKILL.md` | 新增「WorkBuddy 平台事实」专节：日记（`.workbuddy/memory/YYYY-MM-DD.md`）**只追加**、过期条目用 `> superseded` 标注；`MEMORY.md` 蒸馏层 ≤3000 字符/会话；禁区清单（`.workbuddy/` 结构、automations、个人目录）；声明与 WorkBuddy 内建写记忆机制的关系（洁癖是收尾审查增强版，不重复记录） |
| `references/agent-paths.md` | 新增 WorkBuddy 路径速查表：AGENTS.md / 日记 / 蒸馏层 / 用户级记忆（`~/.workbuddy/MEMORY.md` ≤4000 字符）/ 技能目录 / 身份文件，以及三分法在 WorkBuddy 下的落位 |
| `references/sync-matrix.md` | 记忆路由表新增 3 行：日记过期 → superseded 标注；日记超 30 天 → 蒸馏后列入删除候选；蒸馏层超预算 → 先压缩再新增 |
| `references/governance.md` | 只读报告清单加入 WorkBuddy 禁区 |
| `scripts/audit-inventory.sh` | 新增 `workbuddy-memory` 盘点段：列出记忆文件体量 + 超 30 天日记计数 |

## 安装

```bash
# 用户级（全项目可用）
git clone https://github.com/kirigayaut/neat-freak-workbuddy.git
cp -R neat-freak-workbuddy ~/.workbuddy/skills/neat-freak

# 或项目级
cp -R neat-freak-workbuddy <你的项目>/.workbuddy/skills/neat-freak
```

也可以直接把本仓库地址丢给 WorkBuddy，让它帮你装。

## 使用

任务收尾时说任意一句即可触发：

```
/neat
洁癖
整理一下 / 同步一下 / sync up
```

轻量路径五步：盘点 → 对齐事实 → 补 AGENTS.md → 清点会话残留 → 汇报。有发布流程的项目自动走完整路径（0–7 步）。

## 许可证

MIT — 上游版权归 数字生命卡兹克（KKKKhazix），WorkBuddy 适配部分归 kirigayaut。详见 [LICENSE](LICENSE)。
