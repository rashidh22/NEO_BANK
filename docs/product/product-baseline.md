# Product baseline and implementation guardrails

Source: submitted `NeoBank_PRD_Final.docx`; engineering context: `NeoBank Final Project.docx`, sprint backlog and supplied HLA diagram. The PRD is the product source of truth; architecture/code/database choices here are proposals, not PRD mandates.

## Capabilities in scope

Accounts; beneficiaries and lifecycle; simulated transfers (own account, other bank, mock UPI); future and recurring transfers; statements; loan applications and EMI calculation; session security; branch admin approvals; fraud assessment; spending insights; loan eligibility pre-assessment; KYC document checks; read-only banking assistant; notifications and audit expectations.

## Non-negotiable constraints

- No real funds, real UPI, real payment processing or production banking-core integration.
- AI supports decisions; it cannot make final loan decisions or execute transfers.
- Banking assistant can answer authorized banking questions but cannot transact.
- Loan final decision belongs to a human Loan Officer.
- Customer session idle timeout is five minutes, per PRD.
- Enforce ownership/authorization and clear loading, empty, error, confirmation and success states.
- Keep unresolved requirements explicitly TBD; do not silently invent rules.

## Roles

Customer, Teller, Loan Officer, Branch Admin. Teller permissions and exact admin/loan-officer boundaries are unresolved; implement authorization only after approval.

## Traceability seeds

| PRD capability | Requirement IDs | Proposed domain folder |
|---|---|---|
| Accounts and transactions | BNK-FR-01 | account-service |
| Beneficiary lifecycle | BNK-FR-02 | beneficiary-service |
| Simulated transfers | BNK-FR-03 | transfer-service |
| Scheduled/recurring transfers | BNK-FR-04 | schedule-service |
| Statements | BNK-FR-05 | statement-service |
| Loans / EMI | BNK-FR-06 | loan-service |
| Session security | BNK-FR-07 | identity-service |
| Branch approvals | BNK-FR-08 | admin-service |
| Fraud assessment | BNK-AI-01 | risk-ai-service |
| Spending insights | BNK-AI-02 | risk-ai-service |
| Loan pre-assessment | BNK-AI-03 | risk-ai-service |
| KYC document checks | BNK-AI-04 | risk-ai-service |
| Read-only assistant | BNK-AI-05 | risk-ai-service |

This mapping is an initial engineering proposal; confirm ownership in the service catalogue.
