# Skill Assessment Scenarios for Role-Based Virtual OJT

> ⚠️ This branch (`extended-architecture`) contains a more advanced and modular design for the skill assessment platform.
>
> The current main branch has shifted to a simplified MVP due to practical constraints on ChatGPT’s behavior and network reliability.
> This version remains preserved here as an exploratory prototype for future reuse.
>
> 👉 **For the rationale behind this transition, see [ADR-0016](./docs/adr/0016-mvp-rollback.md).**

## 🧩 About This Branch

This branch implements a fully modular and structured version of the ChatGPT-based skill assessment application. It was developed as an advanced prototype to explore flexible, phase-driven facilitation within ChatGPT sessions.

### Key Features

- **Prompt Routing**  
  A centralized router (`role_router.md`) detects trigger words (e.g., `PO`, `!debug`) to switch modes dynamically.

- **Phase-Based Prompt Injection**  
  Prompts are split by phase (`prompt_intro.md`, `prompt_roleplay.md`, etc.), and explicitly re-injected to mitigate ChatGPT’s memory drift.

- **Facilitator Mode Enforcement**  
  `facilitator_prompt.md` maintains neutral tone, avoids meta-commentary, and constrains ChatGPT’s behavior during roleplay phases.

- **Config-Driven Architecture**  
  Files like `config/po.yaml` and `config/lang/jp.yaml` map all relevant resources (prompts, characters, product briefs) to support role-specific logic.

- **Reflection Phase with Report Output**  
  After roleplay ends, a dedicated prompt (`prompt_report_generation.md`) is used to generate a markdown report with strengths and improvement points.

### Status

Due to practical constraints (e.g., unstable GitHub fetches, prompt completion bias), this version was scaled down for the MVP. See [ADR-0016](../../docs/adr/0016-mvp-scale-down.md) for the full decision rationale.

However, this design may be reintroduced in future advanced versions—especially for more complex roles like Enterprise Architect.

---

> **For ChatGPT: Please read [README_chat.md](https://raw.githubusercontent.com/skijima404/skill-assessment/refs/heads/main/shared/chat_landing/README_chat.md) instead of this file.

This repository provides ChatGPT-ready skill assessment templates for virtual OJT (On-the-Job Training) by role.

本リポジトリは、ChatGPTを使ってロール別にバーチャルOJT形式のスキルアセスメントを行うためのテンプレート集です。

このアセスメントは、バーチャルOJT形式で実施され、ChatGPTとの対話を通じてロール別の判断力・対応力を測定・学習します。

対応ロール（例）：

- プロダクトオーナー（PO）
- エンタープライズアーキテクト（EA）... Coming Soon
- ソリューションアーキテクト（SA）... Coming Soon

## 🧭 利用手順（参加者向け）

以下のメッセージを **ChatGPT（Plus or Proプラン）にコピー＆ペースト**してください：

```
このリポジトリを使ってPOアセスメントを開始します。

https://github.com/skijima404/skill-assessment

PO
```

※ChatGPTがアセスメントの説明を始めたら、そのまま案内に従って進めてください。  
※起動前に詳細な説明を読みたい方は、[こちらのガイド](./docs/user_howto.md)をご参照ください。

---

## 🛠️ For Developers and Contributors

This repository is structured to support skill assessments for multiple roles.  
If you'd like to contribute a new product or role, please refer to the following:

- [`docs/repository_overview.md`](./docs/repository_overview.md)
- [`CONTRIBUTING.md`](./CONTRIBUTING.md)

Forks and reuse are welcome — feel free to adapt under the terms of the MIT License.

---

Built with the help of AssistA, our tireless virtual facilitator.

