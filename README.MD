Cosmin Lavric — Smart Contract Security Researcher
Solidity · Move · Rust/Solana · Vulnerability Triage

Smart contract security researcher focused on exploitable logic flaws, broken accounting invariants, access-control failures, and state-manipulation attacks across EVM and Move-based protocols.

🏆 Rank 3/723 — first Cantina competition · 🛡️ Professional audit and triage experience · 🔍 Critical and High findings across Solidity and Move

Telegram · 
Email
 · GitHub

Available for solo audits, collaborative engagements, vulnerability triage, PoC validation, and report review.

📊 Track Record
Area	Result
Best public placement	Rank 3/723 — Kuru, Cantina
Competitive audit findings	2 High · 3 Medium
Professional audit findings (KannAudits)	2 Critical · 1 High · 5 Medium · 3 Informational
Pashov triage assignments	5 codebases
Security stacks	Solidity · Move · Rust/Solana
🔐 Professional Audits
KannAudits — Security Research Intern
Protocol	Stack	Findings	Report
Fluton	Solidity / FHE · Aave · Diamond	1 Critical · 1 High · 4 Medium	View report
IZKONEN	Solidity / Base	3 Informational	View report
APTree	Move	1 Critical · 1 Medium	Awaiting publication
Fluton is a privacy-focused DeFi protocol using fully homomorphic encryption (FHE) with Aave V3 integration and Diamond proxy architecture. The engagement covered confidential ERC-20 wrapping, cross-chain bridge flows, and encrypted lending operations across 19 contracts.

Pashov Audit Group — Vulnerability Triage
Performed vulnerability triage and severity assessment across five codebases:

Polygon · Monero Wallet · Sui Seal · Aptos Token Account · Wormhole

Reproduced and validated proof-of-concept exploits
Assessed root cause, exploitability, impact, and severity
Filtered duplicates, invalid submissions, and false positives
Reviewed remediation quality and report clarity
🏆 Competitive Audits
Competition	Platform	Stack	Result	Findings	Report
Kuru	Cantina	Solidity / Monad	3/723	1 High	Report
CurrentFinance	Sherlock	Move / Sui	29/509 — Top 5.7%	1 High · 1 Medium	Results
Avon	Cantina	Solidity / MegaETH	23/316 — Top 7.3%	2 Medium	Private
Stump the AI Auditor	CertiK	Smart contracts	9/500+	Confirmed a vulnerability the AI missed	—
The CertiK result led to public recognition and a fast-tracked Security Researcher interview.

🔥 Featured Finding
Kuru — Permissionless Deposit Enables Vault Poisoning and Permanent DoS
Severity: High
Result: Rank 3/723 in my first Cantina competition
Category: Cross-contract accounting · State poisoning · Denial of service

MarginAccount.deposit() allowed any caller to credit tokens to an arbitrary address, including a protocol vault. An attacker could deposit directly on behalf of KuruAMMVault, increasing its recorded reserves without minting LP shares or updating pricing state. This broke the relationship between:

text

vault reserves ↔ LP share supply ↔ market pricing state
Once poisoned, the inconsistent accounting caused arithmetic failures during virtual rebalancing. Deposits, previews, and withdrawals could revert permanently, freezing liquidity-provider funds.

➡️ Read the full Kuru report

🎓 Training
Rektoff Solana Rust Security Bootcamp — Cohort 4
Completed with an A− evaluation on the capstone audit report.

🦅 CodeHawks First Flights
Top performances
Additional competitions
Practice audits
📬 Contact
Available for solo or collaborative audit engagements, private competitions, vulnerability triage, proof-of-concept validation, and security report review.

Telegram: @cosminm53
Email: 
cosminlavric53@gmail.com
