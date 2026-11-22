### 我把「不确定」做成「可验证」

写代码这些年只坚持一件事：**一件事如果没法验证，就不敢说自己做完了。**

所以我写的项目，README 里都有「已知局限」「当前不包含什么」，没做完的部分标 `PENDING` 摆在状态表里。

---

### 五个项目

**[ontology-kb](https://github.com/lbh-banboo/ontology-kb)** — 本体驱动的个人知识库

关系写进 Markdown frontmatter 成为 typed 数据，于是可被确定性查询、被回归测试、被提交前拦截。零依赖，Python 3.9+ 直接跑。

`check → violation 0` · `test → 10/10 PASS` · Apache-2.0

**[chanlun-v051](https://github.com/lbh-banboo/chanlun-v051)** — A 股缠论买卖点引擎

截断重算 0 差异，19 项突变检验全抓。README 里主动写明：**回测证据不支持买点有优势**，关注池年化 7.4% 跑输等权买入持有的 23.8%。

`mutations caught 19/20` · `truncation diff 0` · MIT

**[skillhub](https://github.com/lbh-banboo/skillhub)** — AI Skill 中台

生成、检索、审核、分发。装 Skill 等于执行别人的代码，所以每一份都要先过门禁：确定性扫描 + 语义扫描 + 内容哈希。

`FastAPI · pgvector · Celery · Docker Compose` · Apache-2.0

**[interview-prompt-board](https://github.com/lbh-banboo/interview-prompt-board)** — 本地实时转写 + 个人题库检索

服务只跑 `127.0.0.1`，无账号体系，数据不出本机。双 ASR 后端统一适配、Silero VAD 分段、FTS5 + 向量 RRF 融合检索。

`local sherpa · 360MB 模型 · 断网可用` · MIT

**[tuwen-content-studio](https://github.com/lbh-banboo/tuwen-content-studio)** — AI Native 图文内容生产

把一条图文拆成八步有状态的流程，每步有产出、能结项。FastAPI + SQLAlchemy + PostgreSQL/pgvector，事件用 Outbox 表 + 任务租约，不依赖 MQ。

**研发中的脱敏快照，不是可上线产品** · MIT

---

### 30 秒试一个

不想读 README，直接跑这个。零依赖，不用装任何东西：

```bash
git clone https://github.com/lbh-banboo/ontology-kb && cd ontology-kb
python3 vault/_kb/kb.py check && python3 vault/_kb/kb.py test
```

会看到 `violation 0` 和 `10/10 PASS`。**知识库有单元测试**，是这个项目唯一想证明的事。

---

### 我在意的东西

| | |
|---|---|
| **可断言** | 关系没被写下来，检索再强也只是在噪音里捞句子 |
| **可证伪** | 不接受「看起来能赚钱」的回测，只接受突变检验抓不住的结论 |
| **可审查** | 装一个 Skill 是在执行别人的代码，这件事不该是盲盒 |
| **不出本机** | 数据默认不上云，外发项要在设置页第一层写清楚 |

---

最想要的贡献：**一个你踩到的失败模式，附上可执行的判据。**

五个仓库的 issue 都开着，报告 bug 不用客气。中文 / English both fine.

<sub>All projects are personal research work unless stated otherwise. chanlun-v051 is research only, not investment advice; all trades are paper-only and no broker integration exists.</sub>
