# json-schema-demos
Json schema demo
Schema inventory

## Invoice
Line-item billing with grandTotal = subtotal + taxTotal - discountTotal. Conditional on discountType (percentage vs fixed). $ref party/address/contact/lineItem.

## Annual Report
Balance sheet, income statement, cash flow, footnotes. totalAssets = liabilities + equity. Conditional: auditor status qualified/adverse requires qualification notes.

## Loan Agreement
Tranche structure with amortization schedules, covenant package, collateral register. Lender commitmentPct sum = 100. Conditional on interestType (fixed → rate, floating → index + spread). Conditional on loanType = revolving → credit facility details.

## Fund NAV Report
Holdings with model-priced assets (if pricingSource = model → modelInputs required). NAV = grossAssets - totalLiabilities, and share class NAV totals must reconcile back to fund NAV.

## Trade Confirmation
allOf with four if/then branches discriminating on instrumentType to swap in equity, bond, FX, or derivative sub-schemas. netConsideration = gross + commission + tax.
## Insurance Policy
Coverage schedule with per-coverage beneficiary allocation summing to 100%. Premium total = annualised sum of coverages. Conditional: policyType = life requires medical underwriting.

## Payroll Run
Per-employee netPay = grossPay + totalDeductions. Run totals aggregate across all employees. Conditional: employmentType = contractor requires ABN/contract fields.

## KYC/AML Profile
PEP check with nested if isPEP → pepDetails. Sanctions screening with multi-list results. Conditional: entityType = legal_entity requires UBO register. Adverse media sub-object.

## Budget Plan
Three-level hierarchy: budgetLine → costCentre → department → grandTotal. Monthly phasing array (12 items summing to annual). Conditional: capex = true requires assetClass.

## Regulatory Capital Report
Basel III capital tiers, RWA by exposure class, LCR, leverage ratio. Multiple sum chains: totalRWA = creditRWA + marketRWA + opRWA + CVA. Conditional: gsibCategory = G-SIB enforces gsibSurcharge on the ratios object.
