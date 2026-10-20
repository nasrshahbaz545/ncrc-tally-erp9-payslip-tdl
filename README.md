# Tally.ERP 9 Payslip TDL

Built using Tally Developer mode. It is an unofficial, open-source TDL customization for producing structured government-style employee payslips in Tally.ERP 9.

The customization improves individual and multi-employee payslip printing and adds selected employee-master information without intentionally changing native payroll calculations.

## Important Notice

This is an independent community project.

This project is not developed, endorsed, certified, maintained, or supported by Tally Solutions Pvt. Ltd. or any government organization.

Tally, Tally.ERP 9, TallyPrime, and TDL are trademarks or product names associated with their respective owners.

Always test this customization using a backup copy of the company data before using it in a live payroll environment.

---

## Features

### Payslip Header

- Displays the current company name
- Displays an organization or government subtitle
- Retains the native dynamic payslip period
- Removes the duplicate native payslip title
- Removes unnecessary blank space above employee details
- Supports individual payslip printing
- Supports multi-employee payslip printing

### Employee Information

The customized payslip can display:

- Employee Name
- Employee Number
- CNIC
- Employment Status
- Function
- Designation
- Location
- Date of Joining
- Employee Scale or Group
- DDO Code

### Earnings and Deductions

- Retains native Tally payroll calculations
- Displays earnings and deductions separately
- Removes numeric account prefixes from printed pay-head names
- Uses `PaySlipName` when available
- Falls back to the native pay-head name when required
- Retains native gross salary, deductions, and net salary calculations

### Payslip Footer

- Accounts Officer label
- Authorized Signatory area
- Computer-generated payslip disclaimer
- Errors and omissions disclaimer

### Employee Master Customization

An Employment Status field is added to individual Employee Creation and Alteration.

Available Status values include:

- Regular
- Contract
- Deputation
- Daily Wages
- Intern
- Project Employee
- Retired
- Terminated

Existing employees without a saved Employment Status display `Regular` as the fallback value on the payslip.

### Multi Employee Alteration

The Multi Employee Alteration screen supports bulk editing of:

- Designation
- CNIC
- Date of Leaving

CNIC is stored in the native `PassportDetails` method for compatibility with the Employee Master and payslip.

---

## Known Limitation

Employment Status must be entered or changed through the individual Employee Creation or Employee Alteration screen.

Employment Status is intentionally not included in Multi Employee Alteration because the custom Employment Status UDF did not persist reliably through the tested legacy Tally.ERP 9 Multi Master workflow.

Designation, CNIC, and Date of Leaving may still be maintained through Multi Employee Alteration.

---

## Data Mapping

| Payslip Information | Tally Method or Storage |
|---|---|
| Employee Name | Cost Centre Name |
| Employee Number | AdditionalName |
| CNIC | PassportDetails |
| Employment Status | NCRCEmploymentStatus UDF |
| Designation | Designation |
| Function | Function |
| Location | Location or configured text |
| Date of Joining | DateOfJoin |
| Date of Leaving | DeactivationDate |
| Scale | Parent Employee Group |
| Company Name | SVCurrentCompany |

---

## Compatibility

This customization was developed and tested in a legacy Tally.ERP 9 environment.

Compatibility with the following is not guaranteed:

- Other Tally.ERP 9 releases
- TallyPrime
- Different country editions
- Different payroll configurations
- Third-party TDL customizations
- TCP files that alter the same Forms, Parts, Lines, Fields, or Collections
- Other customizations using the same UDF index

Users should independently test the TDL before production deployment.

---

## Installation

### Step 1: Back Up Your Data

Before installing the TDL:

1. Back up the Tally company data.
2. Preserve a copy of the currently working TDL files.
3. If possible, create a separate test company.
4. Do not begin testing in the live payroll company.

### Step 2: Download the TDL

Download the latest `.tdl` or `.txt` file from the repository's Releases section.

Suggested file name:

```text
Tally_ERP9_Payslip_Customization.tdl
