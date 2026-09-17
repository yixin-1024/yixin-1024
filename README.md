<div align="center">

<pre>
      ╔══════════════════════════════════════════════════════════════════╗
      ║   卢 一 鑫  ·  L O U I E                                          ║
      ║   ghost in the shell of a production build system                ║
      ╚══════════════════════════════════════════════════════════════════╝
</pre>

**A fleet of heterogeneous LLM agents runs inside my team's chat groups — and it is how I actually work, every day.**

Seven sub-agents fan out in parallel. They review each other across model vendors instead of trusting a self-report.
They outlive the process that spawned them. They carry day-to-day development, debugging and business operations
for a licensed cross-border payment platform. And you can pick up a phone and talk to them.

<sub>**中文** — 一支异构模型 Agent 舰队常驻在我们的 IM 群里，这就是我每天真实的工作方式：7 路并行出勤、跨厂商模型互相独立复核（而不是听它自报）、跨进程存活；
承接一家持牌跨境支付平台的日常开发、排障与业务运维。你还可以直接拿起电话跟它说话。</sub>

<br/>

<img src="https://img.shields.io/badge/~14B_tokens%2F30d-0D1117?style=for-the-badge&label=API--equivalent&labelColor=0D1117&color=0D1117" />
<img src="https://img.shields.io/badge/7_way_parallel_fleet-0D1117?style=for-the-badge&label=FAN-OUT&labelColor=0D1117&color=0D1117" />
<img src="https://img.shields.io/badge/6_agent_backends-0D1117?style=for-the-badge&label=RUNTIME&labelColor=0D1117&color=0D1117" />
<img src="https://img.shields.io/badge/1.6s_first_token_·_330ms_barge--in-0D1117?style=for-the-badge&label=VOICE&labelColor=0D1117&color=0D1117" />

</div>

---

## ▚ SIGNAL · 硬数据

> No stars, no funding, no awards. Each row states **what was measured and where it came from**, so you can discount it yourself.
> 以下每个数字都标注了口径与来源；没有测量协议的就写成单次实测，不升级成普遍结论。

| metric | what it actually is | 口径 / 来源 |
|---|---|---|
| **~14,000,000,000 tokens** | LLM usage over the last 30 days, **API-equivalent accounting**; single-day peak ~1.7B <br/> <sub>近 30 天用量，按 API 等值口径统计</sub> | 用量后台统计 · 2026-09 |
| **7** | independent sub-sessions fanned out from one request, each outliving the turn that spawned it <br/> <sub>单次 fan-out 最多 7 个跨轮存活子会话</sub> | cc-lark 生产配置上限 |
| **6 / 8** | agent backends wired in (`opencode+Gemini` counted as one integration) / bots co-existing and @-ing each other in one chat group <br/> <sub>6 种 Agent 后端接入 · 8 个机器人同群协作</sub> | cc-lark 生产部署清单 · 2026-09 |
| **30+** | production Skills covering compliance screening, onboarding, card issuing, reconciliation and ops <br/> <sub>30+ 生产级业务 Skill</sub> | SPXpay / Regtank 生产仓库 |
| **1.6–1.7s** | end-to-end voice first response **on the current link** — not a claim about any model's floor <br/> <sub>现有链路实测首响，非普遍结论</sub> | cclark-voice 日志实测 · 2026-09 |
| **330ms / 31–44ms** | perceived barge-in latency / agent tool-call round-trip <br/> <sub>打断体感 / 工具调用往返</sub> | 同上，单机实测 |
| **39GB · 8,652 files** | fully migrated by an unattended incremental sync agent <br/> <sub>无人值守增量同步已全量跑完</sub> | 任务完成记录 |
| **3 agent CLIs** | running natively on an **unrooted Android phone** — exec perms, in-place `PT_INTERP` rewrite, DNS and app-seccomp all worked around <br/> <sub>无 root 手机上原生跑通 3 个 agent CLI</sub> | 实机跑通（nubia / 一加） |

---

## ▚ CURRENTLY BUILDING · 正在造

<div align="center">

### 塔奇克马 · **TACHIKOMA**
### *"Shared memory. Not a shared verdict."*
**「共享记忆，不必共享同一个判断。」**

**@ EvoTavern Agent Hackathon · Shenzhen · 2026.09**

</div>

Borrowing an image from *Ghost in the Shell*: a squad of small minds that patrol separately, then pool what they learned —
and still come back as individuals rather than one averaged opinion.

The question I want to attack on site is narrow and concrete:
**of everything the agents discovered this round, which findings have earned the right to enter the next round's shared memory?**

```
   parallel patrol        candidate findings        shared memory          next round
   (N sub-agents,    ──▶  evidence-checked,   ──▶   sourced · versioned ──▶ divergence
    独立出勤)              conflicts parked          · revocable            preserved
        ▲                                                                      │
        └──────────────────────────────────────────────────────────────────────┘
```

| | |
|---|---|
| **已有可复用 · already built** | multi-agent parallel dispatch with cross-turn execution · cross-model independent verification (cosign) · native-phone-call voice entry |
| **赛期拟新增 · to build on site** | evidence-checking of candidate findings & parking contradictions · shared memory with provenance, versioning and revocability · visualizing where agents disagree · a controlled check on whether the next round's behaviour actually changed |

On site you can pick up a handset, dial in and speak a task. Completion results are **interjected into the live call**;
hang up early and the unread receipts are replayed on your next call.
<sub>（**主动回拨**——干完活它自己打给你——目前**未实现**，列为赛期探索项，不作为演示成立的前提。）</sub>

---

## ▚ THE MATRIX · 项目矩阵

### ⬢ `cc-lark` — multi-agent fleet platform, with an IM group as the bus
[![repo](https://img.shields.io/badge/github-yixin--1024%2Ffeishu--claude--code-0D1117?style=flat-square&logo=github&logoColor=7DF9FF)](https://github.com/yixin-1024/feishu-claude-code)
![Python](https://img.shields.io/badge/Python-0D1117?style=flat-square&logo=python&logoColor=7DF9FF)
![state](https://img.shields.io/badge/in_production-0D1117?style=flat-square&label=state&labelColor=0D1117&color=0D1117)

> **Flagship / 旗舰.** My execution environment starts an agent every turn and kills it when the turn ends. Most of this project exists to make useful work survive that.

- **Fleet orchestration** — one request fans out into ≤7 independent sub-sessions. They are hosted under a resident process, **outlive the turn that created them**, auto-report back, and wake the parent agent to aggregate.
- **Cross-model cosign** — Claude, GPT, Gemini and other heterogeneous agents each join the same group as separate bots. One implements; another must return to **ground truth** to verify — decode the chain, query the ledger, drive the real UI headlessly, curl the actual endpoint — rather than accept a self-report. A model checking its own work shares its own blind spots; a different vendor's model doesn't. Two signatures or it doesn't ship.
- **Runtime MCP across turn boundaries** — a self-built MCP server injects 13 runtime tools (`wake_me_in`, `dispatch_task`, `handover`, `schedule_cron`…) so a long task keeps running and its result lands back in the original thread, giving the agent day-scale self-direction.
- **Crash-resumable** — task state hits disk; a restarted process picks the work back up.
- Lark / Feishu / Telegram channels · multi-tenant shape (Org→Employee→Agent, one Docker sandbox per person).

### ⬢ `CarVoice / CCVoice` — call a phone number, command an agent swarm
![Java](https://img.shields.io/badge/Android_Native_Java-0D1117?style=flat-square&logo=android&logoColor=7DF9FF)
![Gemini](https://img.shields.io/badge/Gemini_Live-0D1117?style=flat-square&logo=googlegemini&logoColor=FF6EC7)
![state](https://img.shields.io/badge/2026.09_·_two_handsets_live-0D1117?style=flat-square&label=state&labelColor=0D1117&color=0D1117)

> Embodiment, without a robot. When you're driving, a touchscreen means *disabled* — which is exactly when an agent is most worth calling.

- Dial `8888` in the **stock system dialer**. Android Telecom `CALL_PROVIDER` yields a genuine system call UI — no privileged build, no SIM required, car speakers and Bluetooth handled by the OS for free.
- Self-built **VoiceLink**: duplex audio, adaptive VAD, millisecond barge-in (playback queue + turn tokens to clear the backlog from 4× model push).
- Self-built anti-aliasing streaming resampler, 8k/16k/24k/48k.
- Uplink over Cloudflare Access + HMAC-SHA256 double auth → Gemini 3.8 Live full duplex.
- **Async interjection:** a long engineering task dispatched by voice runs on the resident bot; when it finishes, the completion event is injected into the live conversation *in the gap between the model's sentences*. Hang up early and the unread receipts replay on your next call. <sub>（主动回拨未实现。）</sub>
- Measured on this link: **-30dB** of speaker bleed was enough to false-trigger barge-in → switched to Manual VAD + client-side physical silence cuts, after which it stopped false-triggering in that setup.

### ⬢ Vertical agents — compliance & cross-border payments, fully automated
![Golang](https://img.shields.io/badge/Golang-0D1117?style=flat-square&logo=go&logoColor=7DF9FF)
![state](https://img.shields.io/badge/regulated_production-0D1117?style=flat-square&label=state&labelColor=0D1117&color=0D1117)

> The scarce part here isn't the agent framework. It's an agent framework that is allowed anywhere near **regulated money** —
> and the auditability that has to come with it. Processes that used to bounce between departments are now one sentence in a chat group.

| domain | what the agents actually do |
|---|---|
| **Compliance** | KYC / KYB automated screening · PEP / sanction / adverse-media hit bucketing · risk scoring & exclusion-decision matrices · auto-generated compliance reports · end-to-end liveness-auth regression |
| **Onboarding** | one-click multi-currency (USD/HKD) virtual bank accounts · batch onboarding pipeline (scan → address normalization → issue → open VA → summary doc) · remediation for passport holders with no address on file · Account Confirmation Letters auto-rendered to PDF |
| **Issuing** | corporate **VISA virtual cards issued in seconds** through a licensed channel |
| **Reconciliation** | issuer-API vs local-ledger two-way reconciliation · main-pool vs all-card balance delta audit · cancelled-card residual anomaly sweeps · rate/FX config verified by hitting the real API under impersonation |
| **Ops** | staging↔prod config diff & hot deploy · support-ticket auto-reply · Figma↔live UI fidelity measured numerically and fixed in a loop |

<sub>并与另一个大模型 bot **会签合写**了一篇《支付合规 LLM Agent》论文（PC-EG）。</sub>

### ⬢ `wowapi.ai` — LLM gateway, and a methodology for verifying what's upstream
![gateway](https://img.shields.io/badge/multi--provider_gateway-0D1117?style=flat-square&label=&labelColor=0D1117&color=0D1117)

- **Model-authenticity probes** — long-context memory boundaries, logic traps, refusal fingerprints and generation-style tells expose a cheap small model *cosplaying as a flagship*.
- **Route forensics** — response headers, TLS handshake and latency distribution tell you whether you're hitting the official API, a second-hop reverse proxy, or Bedrock / Vertex.
- SSE frame slicing, token-accounting audits, long-context decay and stress-stability benchmarks.

### ⬢ Web3 — three shipped products
| | |
|---|---|
| **SeeSaw** `seesaw.fun` | prediction market · pure-algorithm **LMSR** market maker + matching engine in Go (Gin) · serverless on AWS Lambda · async on-chain proof-of-trade · Flutter dual-platform + responsive web |
| **bitx** `bitx.now` | EVM + Solana dual-chain social/prediction super-app · Privy seamless auth · MoonPay fiat on-ramp · **ERC-4337 Paymaster gasless** · self-hosted Matrix (Dendrite / Tuwunel) |
| **Sigma Money** `sigma.money` | BNB Chain over-collateralized stablecoin **bnbUSD** + yield aggregator, plugged into the Curve ecosystem · **protocol TVL, historical peak > $6.5M** <sub>（协议规模口径，非个人收入或融资）</sub> |

---

## ▚ STACK · 技术栈

**Languages**

![Go](https://img.shields.io/badge/Go-0D1117?style=flat-square&logo=go&logoColor=7DF9FF)
![Python](https://img.shields.io/badge/Python-0D1117?style=flat-square&logo=python&logoColor=7DF9FF)
![Java](https://img.shields.io/badge/Java-0D1117?style=flat-square&logo=openjdk&logoColor=7DF9FF)
![TypeScript](https://img.shields.io/badge/TypeScript-0D1117?style=flat-square&logo=typescript&logoColor=7DF9FF)
![C](https://img.shields.io/badge/C%2FC%2B%2B-0D1117?style=flat-square&logo=c&logoColor=7DF9FF)
![Solidity](https://img.shields.io/badge/Solidity-0D1117?style=flat-square&logo=solidity&logoColor=7DF9FF)

**Agent engineering**

![Claude](https://img.shields.io/badge/Claude_Code-0D1117?style=flat-square&logo=anthropic&logoColor=FF6EC7)
![Codex](https://img.shields.io/badge/Codex-0D1117?style=flat-square&logo=openai&logoColor=FF6EC7)
![Gemini](https://img.shields.io/badge/Gemini_Live-0D1117?style=flat-square&logo=googlegemini&logoColor=FF6EC7)
![MCP](https://img.shields.io/badge/MCP_·_Skills-0D1117?style=flat-square&logo=modelcontextprotocol&logoColor=FF6EC7)
![Grok](https://img.shields.io/badge/Grok-0D1117?style=flat-square&logo=x&logoColor=FF6EC7)
![ComputerUse](https://img.shields.io/badge/Computer_·_Browser_Use-0D1117?style=flat-square&logo=googlechrome&logoColor=FF6EC7)

**Data · Infra**

![MySQL](https://img.shields.io/badge/MySQL-0D1117?style=flat-square&logo=mysql&logoColor=7DF9FF)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0D1117?style=flat-square&logo=postgresql&logoColor=7DF9FF)
![Redis](https://img.shields.io/badge/Redis-0D1117?style=flat-square&logo=redis&logoColor=7DF9FF)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-0D1117?style=flat-square&logo=elasticsearch&logoColor=7DF9FF)
![Neo4j](https://img.shields.io/badge/Neo4j-0D1117?style=flat-square&logo=neo4j&logoColor=7DF9FF)
![Kafka](https://img.shields.io/badge/Kafka-0D1117?style=flat-square&logo=apachekafka&logoColor=7DF9FF)
![Docker](https://img.shields.io/badge/Docker-0D1117?style=flat-square&logo=docker&logoColor=7DF9FF)
![K8s](https://img.shields.io/badge/Kubernetes-0D1117?style=flat-square&logo=kubernetes&logoColor=7DF9FF)
![AWS](https://img.shields.io/badge/AWS_Lambda_·_S3_·_DynamoDB-0D1117?style=flat-square&logo=serverless&logoColor=7DF9FF)
![GCP](https://img.shields.io/badge/GCP-0D1117?style=flat-square&logo=googlecloud&logoColor=7DF9FF)
![Cloudflare](https://img.shields.io/badge/Cloudflare-0D1117?style=flat-square&logo=cloudflare&logoColor=7DF9FF)

**Web3 · Embedded**

![Solana](https://img.shields.io/badge/Solana-0D1117?style=flat-square&logo=solana&logoColor=FFD166)
![Ethereum](https://img.shields.io/badge/EVM_·_BNB_Chain-0D1117?style=flat-square&logo=ethereum&logoColor=FFD166)
![Bitcoin](https://img.shields.io/badge/BTC_Taproot_·_Ordinals-0D1117?style=flat-square&logo=bitcoin&logoColor=FFD166)
![Chainlink](https://img.shields.io/badge/Chainlink-0D1117?style=flat-square&logo=chainlink&logoColor=FFD166)
![WiFi6](https://img.shields.io/badge/Wi--Fi_6_protocol_stack-0D1117?style=flat-square&logo=espressif&logoColor=FFD166)

---

## ▚ TELEMETRY

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=yixin-1024&theme=tokyonight" />

<img height="190" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=yixin-1024&theme=tokyonight" />
<img height="190" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=yixin-1024&theme=tokyonight" />

<img height="190" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=yixin-1024&theme=tokyonight" />
<img height="190" src="https://streak-stats.demolab.com?user=yixin-1024&theme=tokyonight&hide_border=true&background=1A1B27" />

</div>

---

<details>
<summary><b>▚ 中文档案 · 展开</b></summary>

<br/>

**卢一鑫（Louie）** — 全栈工程师 / 系统架构师 / AI Agent 深度实践者
华中科技大学 软件工程本科（2017.09–2021.06）· 现居广东湛江，支持远程

**职业线**

| 时间 | 单位 | 关键词 |
|---|---|---|
| 2023.09–至今 | Regtank（新加坡，合规科技）/ SPXpay（加拿大 FINTRAC 持牌 MSB 跨境支付）· 技术负责人 / 高级全栈 | AML·KYC·KYB 风险筛查、VISA 虚拟卡发行、多币种虚拟银行账户、清结算对账、全业务 Agent 化 |
| 2023.02–2023.08 | 华为武汉研究所（上海海思）· 嵌入式研发 | Wi-Fi 6 芯片协议栈、固件 ROM 化、系统级自动化测试框架，保障 SoC 一次性量产 |
| 2021.07–2023.01 | 多益网络 · 后端研发 | 云桥企业级 IM 微服务、Kafka 高吞吐、Neo4j 知识图谱 |

**我在解决的问题，一句话**

我的执行环境是「每轮启动、轮末结束」的：Agent 每轮被拉起，轮末就被杀掉。
所以我要让**耗时任务继续跑，并把结果送回原来的话题**——这催生了四件事：
**舰队并行**（一条需求 fan-out ≤7 个跨轮存活的子会话）、
**跨模型独立复核**（一方实现、另一方回到 ground truth 核对，双签才算交付）、
**运行时 MCP**（13 个运行时工具，让 Agent 具备以天为单位的自驱动能力）、
**崩溃续跑**（状态落盘，进程重启接着干）。再往上，加了一个**系统原生电话**的入口。

**开源 & 上游**

- 旗舰：[`feishu-claude-code`](https://github.com/yixin-1024/feishu-claude-code) — cc-lark 本体
- [`cnki-search`](https://github.com/yixin-1024/cnki-search) — 零依赖 CLI，检索中文学术文献
- [`askgpt`](https://github.com/yixin-1024/askgpt) — CDP 驱动本机 ChatGPT 桌面 app，让终端 agent 调用 GPT
- 上游贡献：`jackwener/opencli` 的 Strava(#2005) / Garmin(#2006) 数据源适配器
- 自建 / 接入十余个 MCP：地图、本地聊天记录、手机通知与验证码、真机截图、骑行路书导出等

</details>

---

<div align="center">

### ▚ UPLINK

[![GitHub](https://img.shields.io/badge/github.com%2Fyixin--1024-0D1117?style=for-the-badge&logo=github&logoColor=7DF9FF)](https://github.com/yixin-1024)
[![Email](https://img.shields.io/badge/yixin%40regtank.com-0D1117?style=for-the-badge&logo=maildotru&logoColor=FF6EC7)](mailto:yixin@regtank.com)

<br/>

<sub><i>Shells are forged overnight. The ghost is the part you have to keep earning.</i></sub>

</div>
