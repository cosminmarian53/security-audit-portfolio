# Cosmin Lavric — Smart Contract Security Researcher

**Solidity · Move · Rust | Smart Contract Auditing, Vulnerability Triage, and Adversarial Testing**

I am a smart contract security researcher focused on uncovering exploitable logic flaws, broken accounting invariants, access-control failures, and state-manipulation attacks across EVM and Move-based protocols.

My experience includes public and private audit competitions, professional vulnerability triage, and audit work across Solidity, Move, and Rust codebases.

[Email](mailto:cosminlavric53@gmail.com) · [Telegram](https://t.me/cosminm53) · [GitHub](https://github.com/cosminmarian53) · [Cantina](https://cantina.xyz/u/cosminmarian53) · [X](https://x.com/cosminm53)

> **Available for solo audits, collaborative engagements, private competitions, vulnerability triage, and report review.**

**Navigate:** [Experience](#professional-security-experience) · [Training](#specialized-security-training) · [Competitions](#competitive-audit-results) · [Featured Finding](#featured-vulnerability--kuru-vault-poisoning) · [First Flights](#selected-codehawks-first-flights) · [Practice Audits](#practice-audits-and-technical-development) · [Contact](#engagements)

---

## Track Record at a Glance

| Area | Result |
|---|---:|
| Best public competition placement | **Tied Rank #3 / 723 — Cantina Kuru** |
| Public competitive findings | **2 High · 3 Medium** |
| KannAudits internship findings | **2 Critical · 1 High · 5 Medium** |
| Professional triage assignments | **5 codebases** |
| Rektoff capstone evaluation | **A−** |
| Primary security stacks | **Solidity · Move · Rust** |

> Findings from the KannAudits engagements are currently private and will be linked after publication.

---

## Professional Security Experience

### KannAudits — Security Research Intern

Audited two protocols during my internship: one Solidity codebase and one Move codebase. Across both engagements, I identified eight Critical/High/Medium-severity issues. The corresponding reports are awaiting publication.

| Stack | Critical | High | Medium | C/H/M Total |
|---|---:|---:|---:|---:|
| Solidity | 1 | 1 | 4 | **6** |
| Move | 1 | 0 | 1 | **2** |
| **Total** | **2** | **1** | **5** | **8** |

### Pashov Audit Group — Vulnerability Triage, Contract

Performed vulnerability triage and severity assessment across five codebases. Responsibilities included validating security submissions, reproducing proof-of-concept exploits, assessing exploitability and impact, and filtering false positives.

| Codebase | Stack | Work Performed |
|---|---|---|
| Polygon | Solidity | Vulnerability triage and severity assessment |
| Monero — Wallet | Rust | Vulnerability triage and severity assessment |
| Sui Seal | Move | Vulnerability triage and severity assessment |
| Aptos — Token Account | Move | Vulnerability triage and severity assessment |
| Wormhole | Move | Vulnerability triage and severity assessment |


---

## Specialized Security Training

### Rektoff — Solana Rust Security Bootcamp, Cohort 4

Completed Rektoff's intensive Rust and Solana security program, covering secure systems programming, Solana's execution and account model, vulnerability research, exploit development, and audit methodology.

- **Capstone:** End-to-end security review and professional audit report
- **Evaluation:** **A−**
- **Focus:** Rust · Solana programs · Threat modeling · Proof-of-concept development · Security reporting

[Bootcamp overview](https://www.rektoff.xyz/bootcamp)

---

## Competitive Audit Results

### Public Competitions

| Competition | Platform | Ecosystem / Stack | Placement | Valid Findings | Evidence |
|---|---|---|---:|---:|---|
| **Kuru** | Cantina | Monad / Solidity | **Tied #3 / 723 — Top 0.5%** | **1 High** | [Finding report](audit-competitions/cantina.pdf) · [Leaderboard](https://cantina.xyz/competitions/cdce21ba-b787-4df4-9c56-b31d085388e7/leaderboard) |
| **Current Finance** | Sherlock | Sui / Move | **#29 / 509 — Top 5.7%** | **1 High · 1 Medium** | [Contest results](https://audits.sherlock.xyz/contests/1256) |

### Private Competitions and Security Challenges

| Competition | Platform | Ecosystem / Stack | Placement | Result |
|---|---|---|---:|---|
| **Avon** | Cantina | MegaETH / Solidity | **Tied #23 / 316 — Top 7.3%** | **2 Medium findings** — [leaderboard](https://cantina.xyz/competitions/708eecf5-a6a0-46c1-a949-277f7408decc/leaderboard); report private |
| **Stump the AI Auditor** | CertiK | Security challenge | **#9 / 500+** | Submitted a genuine vulnerability missed by the AI auditor; recognition led to a fast-tracked Security Researcher interview |

---

## Featured Vulnerability — Kuru Vault Poisoning

### Permissionless Margin Deposit Desynchronizes Vault Accounting and Permanently Freezes Funds

**Competition:** Kuru, Cantina  
**Severity:** High  
**Result:** Rank #3 in my first Cantina competition  
**Category:** Cross-contract accounting failure · State poisoning · Denial of service

#### Root Cause

`MarginAccount.deposit(address _user, ...)` allowed any caller to credit an arbitrary account, including a registered market or vault address. The `KuruAMMVault` treated its balance inside `MarginAccount` as authoritative reserves, but a direct third-party deposit increased those reserves without minting corresponding LP shares or updating the vault's pricing state.

This violated a core accounting invariant:

```text
vault reserves ↔ LP share supply ↔ market pricing state
```

#### Exploit Path

1. The attacker initializes the vault with a highly skewed asset ratio, establishing a manipulated price.
2. The attacker bypasses the vault and calls `MarginAccount.deposit()` directly, crediting the vault with a large one-sided “donation.”
3. The vault's reserves become desynchronized from its LP share supply and pricing state.
4. Subsequent preview, deposit, or withdrawal calculations overflow or revert during virtual rebalancing.
5. Core vault functionality becomes permanently unavailable, freezing liquidity-provider funds.

#### Impact

A permissionless attacker can poison any affected vault instance and cause a permanent denial of service. Deposits and withdrawals become unusable, leaving liquidity-provider capital locked in the protocol.

#### Recommended Fix

Prevent arbitrary users from depositing directly to registered market addresses:

```solidity
function deposit(address _user, address _token, uint256 _amount)
    external
    payable
    protocolActive
{
    require(_user != address(0), MarginAccountErrors.ZeroAddressNotAllowed());
    require(!verifiedMarket[_user], MarginAccountErrors.CannotDepositToMarket());

    // Existing deposit logic...
}
```

A stronger architectural defense is to ensure that protocol-owned accounting balances can only be mutated through authenticated protocol flows that update every dependent accounting variable atomically.

[Read the full finding](audit-competitions/cantina.pdf)

---

## Selected CodeHawks First Flights

### Top-Five Performances

| Competition | Report |
|---|---|
| Weather Witness | [View report](first-flights/audit_report_weather_witness.md) |
| Snowman Merkle Airdrop | [View report](first-flights/Cosmin-Snowman-Merkle-Airdrop-competitive-audit-report.md) |

### Additional Competitions

| Competition | Report |
|---|---|
| Bid Beasts | [View report](first-flights/Cosmin-Bid-Beasts.md) |
| Hawk High | [View report](first-flights/hawk_high_first_flight_audit_report.pdf) |
| Last Man Standing | [View report](first-flights/Cosmin-Last-Man-Standing.md) |

---

## Practice Audits and Technical Development

<details>
<summary><strong>View practice audit reports</strong></summary>

These reviews were completed as structured security exercises to deepen coverage of common vulnerability classes, exploit construction, invariant analysis, and professional report writing.

| Protocol | Report |
|---|---|
| Boss Bridge | [View report](first-flights/audit_report_boss_bridge_cyfrin_updraft.pdf) |
| Puppy Raffle | [View report](first-flights/audit_report_puppy_raffle.pdf) |
| Password Store | [View report](first-flights/audit_report_password_store.pdf) |
| TSwap | [View report](first-flights/audit_report_tswap.pdf) |
| Thunder Loan | [View report](first-flights/audit_report_thunder_loan.pdf) |

</details>

---

## Security Focus Areas

- Cross-contract accounting and invariant violations
- Access control, authorization, and privilege boundaries
- Economic attacks, vault manipulation, and share-price abuse
- Denial-of-service and permanent fund-lock scenarios
- Move object ownership, capabilities, and resource-safety issues
- Proof-of-concept development with Foundry / Forge
- Vulnerability triage, severity assessment, and false-positive elimination
- Smart contract and application penetration testing

---

## Engagements

I am available for:

- Solo smart contract audits
- Collaborative audit engagements
- Solidity and Move protocol reviews
- Rust codebase triage and security review
- Vulnerability triage and severity assessment

**Telegram:** [@cosminm53](https://t.me/cosminm53)  
**Email:** [cosminlavric53@gmail.com](mailto:cosminlavric53@gmail.com)
