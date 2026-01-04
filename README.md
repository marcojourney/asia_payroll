# **@asia-payroll/cambodia**

A reusable **TypeScript/JavaScript payroll calculation library** for companies operating in Cambodia.
Designed with a **modular architecture** to support future Asian countries (Vietnam, Thailand, Laos, etc.) through a plugin-style system.

---

## 🚀 **Overview**

`@asia-payroll/cambodia` provides accurate and up-to-date salary calculations based on Cambodian labor regulations, including:

* Tax on Salary (ToS)
* NSSF (Employee & Employer)
* Dependent deduction
* Overtime rules
* Seniority (Backpay & ongoing 2.5%)
* Probation salary logic
* Public holiday & weekend compensation
* Common allowances and deductions

This package is part of the future **Asia Payroll Suite**, starting first with Cambodia.

---

## 📦 **Install**

```bash
npm install @asia-payroll/cambodia
# or
yarn add @asia-payroll/cambodia
```

---

## 🧩 **Architecture (Expandable Design)**

This library is designed to scale into a full regional solution:

```
@asia-payroll/core         → Shared interfaces, types, utilities
@asia-payroll/cambodia     → Cambodia rules
@asia-payroll/vietnam      → (future)
@asia-payroll/thailand     → (future)
```

Country rules are isolated, making maintenance and updates clean and safe.

---

## 📝 **Features Included**

### ✔ Salary Components

* Gross → Net
* Net → Gross (reverse calculation)
* Bonuses, overtime, and allowances
* Seniority payment calculation

### ✔ Legal Compliance

* Monthly ToS calculation
* NSSF employee + employer contributions
* Dependent deduction rules
* Holiday pay (200–300%)
* Night shift calculation

### ✔ Utility Functions

* Salary breakdown report
* Payslip-friendly structure
* Validations & rounding helpers

---

## 🔧 **Usage Example**

### **Basic Salary Calculation**

```ts
import { calculatePayroll } from "@asia-payroll/cambodia";

const result = calculatePayroll({
  grossSalary: 1200000,
  dependents: 1,
  includeNSSF: true,
  seniorityEnabled: true,
});

console.log(result);
```

### **Output Example**

```json
{
  "grossSalary": 1200000,
  "taxOnSalary": 20000,
  "nssfEmployee": 12000,
  "nssfEmployer": 24000,
  "seniority": 30000,
  "netSalary": 1158000
}
```

---

## 📘 **API Reference**

### `calculatePayroll(options)`

| Field            | Type    | Required | Description            |
| ---------------- | ------- | -------- | ---------------------- |
| grossSalary      | number  | ✓        | Monthly gross salary   |
| dependents       | number  | ✗        | Number of dependents   |
| includeNSSF      | boolean | ✗        | Default = true         |
| seniorityEnabled | boolean | ✗        | Include seniority 2.5% |

More APIs like `calculateToS`, `calculateNSSF`, and `reversePayroll` are documented in `/docs`.

---

## 🌏 **Why Cambodia First?**

Although the long-term vision is **Asia-wide payroll**, each country has unique regulations:

* Tax brackets
* Social security rules
* Employer/employee contributions
* Termination & severance laws
* Public holidays

Starting with Cambodia ensures:

1. **High accuracy**
2. **Deep reliability**
3. **A clean, modular structure**
4. **A stable foundation for future countries**

---

## 🛣️ **Roadmap**

### **Phase 1 — Cambodia (current)**

* ✔ Tax on Salary
* ✔ NSSF
* ✔ Seniority
* ✔ Public holidays
* ☐ Complete payslip generator
* ☐ Historical law versions

### **Phase 2 — Core Engine**

* ☐ Publish `@asia-payroll/core`
* ☐ Shared country-agnostic interfaces

### **Phase 3 — Asia Expansion**

* ☐ Vietnam package
* ☐ Thailand package
* ☐ Laos package
* ☐ Malaysia package

---

## 🤝 **Contributing**

PRs and issues are welcome!
We want to make this the most reliable payroll calculation suite for Asian SMEs.

---

## 📄 **License**

MIT License — free for commercial and personal use.

---
