# Cosmin Lavric — Smart Contract Security Researcher

**Solidity · Move · Rust/Solana · Vulnerability Triage · Exploit Development**

I audit smart contracts and investigate exploitable logic flaws, broken accounting invariants, access-control failures, economic attacks, and denial-of-service conditions.

🏆 **Rank 3/723 in my first Cantina competition**  
🛡️ **Professional audit and vulnerability-triage experience**  
🔍 **Critical and High severity findings across Solidity and Move**

[Telegram](https://t.me/cosminm53) · [Email](mailto:cosminlavric53@gmail.com) · [GitHub](https://github.com/cosminmarian53)

> **Available for solo audits, collaborative engagements, vulnerability triage, PoC validation, and report review.**

---

## 📊 Track Record

| Area | Result |
|---|---|
| Best public placement | **Rank 3/723 — Kuru, Cantina** |
| Competitive audit findings | **2 High · 3 Medium** |
| KannAudits internship findings | **2 Critical · 1 High · 5 Medium** |
| Pashov triage assignments | **5 codebases** |
| Security stacks | **Solidity · Move · Rust/Solana** |

---

## 🛡️ Professional Experience

### KannAudits — Security Research Intern

Audited two protocols: one written in Solidity and one written in Move.

| Stack | Critical | High | Medium | Total |
|---|---:|---:|---:|---:|
| Solidity | 1 | 1 | 4 | **6** |
| Move | 1 | 0 | 1 | **2** |
| **Total** | **2** | **1** | **5** | **8** |

> Reports are awaiting publication.

### Pashov Audit Group — Vulnerability Triage

Performed vulnerability triage and severity assessment across five codebases:

**Polygon · Monero Wallet · Sui Seal · Aptos Token Account · Wormhole**

Responsibilities included:

- Reproducing and validating proof-of-concept exploits
- Assessing root cause, exploitability, impact, and severity
- Filtering duplicates, invalid submissions, and false positives
- Reviewing remediation quality and report clarity

---

## 🏆 Competitive Audits

### Public Competitions

| Competition | Platform | Stack | Result | Findings | Report |
|---|---|---|---:|---|---|
| **Kuru** | Cantina | Solidity / Monad | **3/723** | **1 High** | [Read report](audit-competitions/cantina.pdf) |
| **CurrentFinance** | Sherlock | Move / Sui | **29/509 — Top 5.7%** | **1 High · 1 Medium** | [View results](https://audits.sherlock.xyz/contests/1256) |

### Private Competitions and Challenges

| Competition | Platform | Stack | Result | Findings |
|---|---|---|---:|---|
| **Avon** | Cantina | Solidity / MegaETH | **23/316 — Top 7.3%** | **2 Medium** |
| **Stump the AI Auditor** | CertiK | Smart contracts | **9/500+** | Confirmed a genuine vulnerability missed by the AI auditor |

The CertiK result led to public recognition and a fast-tracked Security Researcher interview.

---

## 🔥 Featured Finding

### Kuru — Permissionless Deposit Enables Vault Poisoning and Permanent DoS

**Severity:** High  
**Competition result:** Rank 3/723 in my first Cantina competition  
**Category:** Cross-contract accounting · State poisoning · Denial of service

`MarginAccount.deposit()` allowed any caller to credit tokens to an arbitrary address, including a protocol vault.

An attacker could deposit directly on behalf of `KuruAMMVault`, increasing its recorded reserves without minting LP shares or updating the vault's pricing state. This broke the relationship between:

```text
vault reserves ↔ LP share supply ↔ market pricing state
```

Once poisoned, the inconsistent accounting caused arithmetic failures during virtual rebalancing. Deposits, previews, and withdrawals could revert permanently, freezing liquidity-provider funds.

**Recommended remediation:** prevent direct deposits to registered market addresses and require protocol-owned balances to be updated only through authenticated flows that preserve all accounting invariants.

➡️ **[Read the full Kuru report](audit-competitions/cantina.pdf)**

---

## 🦅 CodeHawks First Flights

### Top Performances

| Competition | Report |
|---|---|
| **Weather Witness** | [View report](first-flights/audit_report_weather_witness.md) |
| **Snowman Merkle Airdrop** | [View report](first-flights/Cosmin-Snowman-Merkle-Airdrop-competitive-audit-report.md) |

### Additional Competitions

| Competition | Report |
|---|---|
| Bid Beasts | [View report](first-flights/Cosmin-Bid-Beasts.md) |
| Hawk High | [View report](first-flights/hawk_high_first_flight_audit_report.pdf) |
| Last Man Standing | [View report](first-flights/Cosmin-Last-Man-Standing.md) |

---

## 🎓 Training

### Rektoff Solana Rust Security Bootcamp — Cohort 4

Completed Cohort 4 and received an **A− evaluation** for the capstone audit report.

---

## 📚 Practice Audits

<details>
<summary><strong>View practice audit reports</strong></summary>

| Protocol | Report |
|---|---|
| Boss Bridge | [View report](first-flights/audit_report_boss_bridge_cyfrin_updraft.pdf) |
| Puppy Raffle | [View report](first-flights/audit_report_puppy_raffle.pdf) |
| Password Store | [View report](first-flights/audit_report_password_store.pdf) |
| TSwap | [View report](first-flights/audit_report_tswap.pdf) |
| Thunder Loan | [View report](first-flights/audit_report_thunder_loan.pdf) |

</details>

---

## 📬 Contact

Available for **solo or collaborative audit engagements**, private competitions, vulnerability triage, proof-of-concept validation, and security report review.

**Telegram:** [@cosminm53](https://t.me/cosminm53)  
**Email:** [cosminlavric53@gmail.com](mailto:cosminlavric53@gmail.com)
