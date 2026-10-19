# Cosmin Lavric — Smart Contract Security Researcher

**Solidity · Move · Rust/Solana · Vulnerability Triage**

Smart contract security researcher focused on exploitable logic flaws, broken accounting invariants, access-control failures, and state-manipulation attacks across EVM and Move-based protocols.

🏆 **Rank 3/723 — first Cantina competition** <br> 🛡️ **Professional audit and triage experience** <br> 🔍 **Critical and High findings across Solidity and Move**

[Telegram](https://t.me/cosminm53) · [Email](mailto:cosminlavric53@gmail.com) · [GitHub](https://github.com/cosminmarian53)

> **Available for solo audits, collaborative engagements, and vulnerability triage.**

---

## 📊 Track Record

| Area | Result |
| --- | --- |
| Best public placement | **Rank 3/723 — Kuru, Cantina** |
| Competitive audit findings | **2 High · 3 Medium** |
| Professional audit findings (KannAudits) | **1 Critical · 2 High · 5 Medium · 3 Informational** |
| Pashov triage assignments | **5 codebases** |
| Security stacks | **Solidity · Move · Rust/Solana** |

---

## 🔐 Professional Audits

### KannAudits — Security Research Intern

| Protocol | Stack | Findings | Report |
| --- | --- | --- | --- |
| **Fluton** | Solidity / FHE · Aave · Diamond | **1 Critical · 1 High · 4 Medium** | [View report](https://github.com/Kann-Audits/Kann-Audits/blob/main/reports/pdf-format/Fluton-security-review-2026-08-20.pdf) |
| **IZKONEN** | Solidity / Base | **3 Informational** | [View report](https://github.com/Kann-Audits/Kann-Audits/blob/main/reports/pdf-format/IZKONEN-security-review-2026-08-18.pdf) |
| **APTree** | Move | **1 High · 1 Medium** | [View report](https://github.com/Kann-Audits/Kann-Audits/blob/main/reports/pdf-format/APTree-security-review-2026-04-13.pdf) |

> Fluton is a privacy-focused DeFi protocol using fully homomorphic encryption (FHE) with Aave V3 integration and Diamond proxy architecture. The engagement covered confidential ERC-20 wrapping, cross-chain bridge flows, and encrypted lending operations across 19 contracts.

### Pashov Audit Group — Vulnerability Triage

Performed vulnerability triage and severity assessment across five codebases:

**Polygon · Monero Wallet · Sui Seal · Aptos Token Account · Wormhole**

- Reproduced and validated proof-of-concept exploits
- Assessed root cause, exploitability, impact, and severity
- Filtered duplicates, invalid submissions, and false positives
- Reviewed remediation quality and report clarity

---

## 🏆 Competitive Audits

| Competition | Platform | Stack | Result | Findings | Report |
| --- | --- | --- | --- | --- | --- |
| **Kuru** | Cantina | Solidity / Monad | **3/723** | **1 High** | [Report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/audit-competitions/cantina.pdf) |
| **CurrentFinance** | Sherlock | Move / Sui | **29/509 — Top 5.7%** | **1 High · 1 Medium** | [Results](https://audits.sherlock.xyz/contests/1256) |
| **Avon** | Cantina | Solidity / MegaETH | **23/316 — Top 7.3%** | **2 Medium** | Private |
| **Stump the AI Auditor** | CertiK | Smart contracts | **9/500+** | Confirmed a vulnerability the AI missed | — |

> The CertiK result led to public recognition and a fast-tracked Security Researcher interview.

---

## 🔥 Featured Finding

### Kuru — Permissionless Deposit Enables Vault Poisoning and Permanent DoS

**Severity:** High  
**Result:** Rank 3/723 in my first Cantina competition  
**Category:** Cross-contract accounting · State poisoning · Denial of service

`MarginAccount.deposit()` allowed any caller to credit tokens to an arbitrary address, including a protocol vault. An attacker could deposit directly on behalf of `KuruAMMVault`, increasing its recorded reserves without minting LP shares or updating pricing state. This broke the relationship between:

```text
vault reserves ↔ LP share supply ↔ market pricing state
```

Once poisoned, the inconsistent accounting caused arithmetic failures during virtual rebalancing. Deposits, previews, and withdrawals could revert permanently, freezing liquidity-provider funds.

➡️ **[Read the full Kuru report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/audit-competitions/cantina.pdf)**

---

## 🎓 Training

**Rektoff Solana Rust Security Bootcamp — Cohort 4**  
Completed with an **A− evaluation** on the capstone audit report.

---

## 🦅 CodeHawks First Flights

<details>
<summary><strong>Top performances</strong></summary>

| Competition | Report |
| --- | --- |
| **Weather Witness** | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_weather_witness.md) |
| **Snowman Merkle Airdrop** | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/Cosmin-Snowman-Merkle-Airdrop-competitive-audit-report.md) |

</details>

<details>
<summary><strong>Additional competitions</strong></summary>

| Competition | Report |
| --- | --- |
| Bid Beasts | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/Cosmin-Bid-Beasts.md) |
| Hawk High | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/hawk_high_first_flight_audit_report.pdf) |
| Last Man Standing | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/Cosmin-Last-Man-Standing.md) |

</details>

<details>
<summary><strong>Practice audits</strong></summary>

| Protocol | Report |
| --- | --- |
| Boss Bridge | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_boss_bridge_cyfrin_updraft.pdf) |
| Puppy Raffle | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_puppy_raffle.pdf) |
| Password Store | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_password_store.pdf) |
| TSwap | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_tswap.pdf) |
| Thunder Loan | [View report](https://github.com/cosminmarian53/security-audit-portfolio/blob/main/first-flights/audit_report_thunder_loan.pdf) |

</details>

---

## 📬 Contact

Available for **solo or collaborative audit engagements**, private competitions, vulnerability triage, proof-of-concept validation, and security report review.

**Telegram:** [@cosminm53](https://t.me/cosminm53)  
**Email:** [cosminlavric53@gmail.com](mailto:cosminlavric53@gmail.com)
