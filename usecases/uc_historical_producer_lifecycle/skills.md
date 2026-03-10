To formalize the capabilities of an AI coding agent within the **Midstream Producer Performance & MVC Optimization** domain, we define its skillset through four progressive stages of development.

These skills ensure the agent doesn't just "write code," but solves the underlying business problem by bridging the gap between contractual legalese and physical flow data.

---

### 1. Validating

**Objective:** Prove data accessibility and verify the feasibility of the "Producer Scorecard" concept.

* **Data Discovery:** Programmatically probe the **CTRM** (Commodity Trading and Risk Management) database and the **Flow/Ticketing** system to confirm the existence of shared keys (e.g., Producer ID, LEI, or API numbers).
* **Gap Analysis:** Detect missing data intervals or "orphan" production streams that lack associated contract metadata.
* **Feasibility Testing:** Run a "Correlation Check" on a 30-day sample to ensure that field-captured volumes can be accurately mapped to specific contractual Minimum Volume Commitments (MVCs).

### 2. Scoping

**Objective:** Shape the Minimum Viable Product (MVP) and its architectural components.

* **Metric Definition:** Formalize the calculation logic for **Commitment Variance** ($\% \text{ Variance} = \frac{\text{Actual} - \text{Committed}}{\text{Committed}}$) and **Deficiency Exposure**.
* **Boundary Setting:** Define the "Dedicated Area" logic—ensuring the agent understands how to attribute volumes only to the specific geographical acreage defined in the contract.
* **User Persona Alignment:** Design the output schema to serve two distinct views: a high-level **Executive Scorecard** for leadership and a granular **Audit Log** for the Finance and Legal teams.

### 3. Evaluating

**Objective:** Implement evaluation frameworks, historical backtests, and performance metrics.

* **Historical Backtesting:** Process 3–5 years of historical throughput data against archived contract terms to quantify "Commercial Leakage" (uncollected fees).
* **Model Validation:** Calculate the **Reliability Index** for each producer—using standard deviation to identify which counterparties are consistently volatile vs. those that are predictable.
* **Sensitivity Analysis:** Simulate different MVC structures (e.g., "Take-or-Pay" vs. "Fixed Fee") against historical data to determine which contract type would have yielded the highest margin.

### 4. Confirming

**Objective:** Package the logic into repeatable, production-grade services and documentation.

* **Job Orchestration:** Wrap the analysis logic into a scheduled container (e.g., Docker/Kubernetes) that updates the Producer Performance View automatically every month-end.
* **API/Service Deployment:** Expose the "Producer Scorecard" via a REST API so it can be ingested by the Commercial team's CRM or BI tools (like PowerBI or Tableau).
* **Automated Documentation:** Generate a "Data Lineage" report for every calculation, ensuring that if a producer disputes a deficiency fee, the Commercial team can prove exactly where the numbers originated.

---
