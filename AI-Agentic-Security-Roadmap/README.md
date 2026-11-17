# ServiceNow + Staff AI Agentic Security Engineer

How my ServiceNow stack (AI Control Tower, IRM, SecOps) fits with PAM (CyberArk / Entra), Armis and enterprise API gateways to secure AI agents, and the streamlined path I'm following to get there.

> 🎯 **Target role:** Remote PAM / Identity Security Engineer in **healthcare or banking**, with **AI agent security** as my edge: controlling who and what (people, vendors and AI agents) gets into critical systems, hands-on in Linux, Python and the CLI.

The hands-on security side (OWASP, APIs, IAM, PAM, AI agent labs) lives in my [AI Agentic Security Roadmap](https://github.com/atoz-guy/ai-agentic-security-roadmap). This page is the ServiceNow side: **the labs teach the attacks, and ServiceNow enforces the controls.**

---

## 🛡️ The security guard: Who, What, When, Why

Every request, whether from a person, a vendor or an AI agent, has to pass four checks.

| Check | Control | Example (hospital) |
|---|---|---|
| **Who** | Identity & authentication | Is this a real vendor technician, an internal clinician, or a specific autonomous AI agent? No shared or anonymous accounts. |
| **What** | Least-privilege scope | Only the exact machine, table or API needed. A scheduling bot can read appointment slots; a vendor technician can patch one specific MRI machine, with zero access to the rest of the network. |
| **When** | Just-in-time / PIM | High-level privileges are off by default, unlocked for a strict window (e.g. 2 hours for a maintenance ticket), and revoked automatically when the timer ends. |
| **Why** | Governance & audit trail | A valid business or clinical reason, like an approved Change Request or Incident, before the PAM vault releases credentials. Every keystroke and AI action is recorded for HIPAA and FDA auditors. |

---

## ⚙️ Where ServiceNow sits

My certs (CIS-RC, CIS-DF, CIS-SIR, CIS-VR) put me at the control switch where IAM/PIM/PAM rules get triggered.

| Role | ServiceNow piece | What it does |
|---|---|---|
| **The "Why" engine** | IRM + Change Management | Before CyberArk, SailPoint or Entra PIM unlocks privileged access for a vendor or AI agent, ServiceNow checks that an approved ticket exists and the device passes compliance checks. |
| **The kill switch** | SecOps (CIS-SIR) | If a vulnerability scanner or AI monitoring spots a rogue action, SIR tells the IAM/PAM system to revoke the session and lock the account automatically. |

---

## 🧠 The 4 AI security concepts

I don't need to build AI models. I need to know what tricks attackers use on AI, and how ServiceNow stops them.

| Concept | Plain English | What I need to do |
|---|---|---|
| **Prompt injection** | Hidden instructions inside normal text (a patient form, an email) trick an agent into ignoring its rules | Spot where untrusted text enters an AI workflow |
| **Non-human identity** | Every AI agent gets its own ID badge, like an employee or vendor | Restrict what the badge unlocks, so a scheduling bot can't open payroll or lab equipment controls |
| **Tool & API misuse** | Agents can push buttons: send emails, update records, run commands | Put a human-in-the-loop approval gate in front of dangerous actions |
| **Data poisoning & leakage** | Agents pull answers from company files and databases | Make sure they only read approved, clean sources and never share one patient's or department's data with another user |

---

## 🔧 The ServiceNow tools

| Tool | Role |
|---|---|
| **Flow Designer + Integration Hub** | The automated security guard. Classic Orchestration has evolved into these. Low-code rules such as "if an AI agent tries to access a restricted database, trigger CyberArk or Entra to lock its access and alert SecOps." |
| **AI Control Tower + Now Assist Guardian** | The AI command center. Every agent is registered, risk-scored and tied into SIR workflows. Guardian adds runtime guardrails against prompt injection and sensitive data leaks. |

---

## 🗺️ My streamlined roadmap

### Phase 1: AI governance & automation (high ROI)

- [ ] **Super Intelligence Control Tower** learning path
- [ ] **AI Control Tower (AICT) Implementation Bootcamp** (builds on CIS-RC and CIS-DF)
- [ ] **Now Assist Guardian: Introduction and Implementation** (runtime guardrails for prompt injection and PII/HIPAA masking)
- [ ] **Flow Designer & Integration Hub** (connecting risk and incident triggers to PAM/IAM tools)

### Phase 2: Technical depth & security boundaries

- [ ] **CAD** Certified Application Developer: scoped apps, scripting and API security, so I can govern what developers and AI agents build. Keeps the door open to ArchX or CTA later.

---

## 🛠️ Starter builds (PDI)

| Build | Status |
|---|---|
| Read the OWASP Top 10 for LLM Applications (the "most wanted" poster for AI attacks) | 🔲 Planned |
| Flow Designer rule: security alert → approval or access revocation | 🔲 Planned |
| Explore how Now Assist Guardian blocks prompt injection and data leaks | 🔲 Planned |
