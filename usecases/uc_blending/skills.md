To implement a **Midstream Blending Optimization** solution, an AI coding agent must evolve through four distinct stages. These skills bridge the gap between raw telemetry (SCADA) and financial settlement (CTRM).

Here is the formalized skill set for an AI agent tasked with building this system:

---

## 1. Validating: Data Accessibility & Feasibility

The agent must first prove that the "digital thread" of a barrel exists from the moment it enters the terminal to the moment it is pumped into a downstream pipeline.

* **Connectivity Audit:** Confirming the agent can poll tags from the **SCADA Historian** (e.g., flow rates, valve positions) and query the **LIMS** (Lab Information Management System) for sulfur and gravity assays.
* **Correlation Testing:** Performing a "Time-Series Alignment" to ensure that a lab sample taken at 2:00 PM matches the physical batch passing through the manifold at that same timestamp.
* **Feasibility Check:** Determining if the current blending manifold has enough "control granularity" (e.g., Variable Frequency Drives on pumps) to actually execute the precision recipes the AI might suggest.

## 2. Scoping: MVP & Component Architecture

The agent defines the "Minimum Viable Product" to prevent $4M+ losses without over-engineering the initial rollout.

* **Component Mapping:** Identifying the "Critical-to-Quality" (CTQ) streams—specifically the high-variability "Swing Streams" that cause most off-spec events.
* **Constraint Logic:** Defining the hard boundaries for the MVP, such as **Pipeline Tariff Limits** (e.g., Max RVP of 9.0 psia) and **Tank Heel Minimums** to prevent pump cavitation.
* **Interface Design:** Outlining a "Head-Up Display" for the Terminal Operator that shows "Predicted vs. Actual" blend quality in real-time.

## 3. Evaluating: Metrics & Backtesting

Before the AI is allowed to "close the loop" and move a physical valve, its logic must be stress-tested against historical terminal data.

* **The "Shadow" Backtest:** Running the AI's optimized blend recipes against the last six months of historical inbound data to calculate the theoretical **Margin Uplift** (e.g., "If we had used this logic in November, we would have saved $0.35/bbl").
* **Sensitivity Analysis:** Simulating "Sensor Drift"—what happens if the Sulfur analyzer is off by 5%? Does the system fail gracefully or produce a "slug" of off-spec oil?
* **KPI Dashboarding:** Building the evaluation framework for the COO, focusing on:
* **On-Spec Rate (%)**
* **Giveaway Cost ($/bbl)**
* **Reblend Volume (BPD)**



## 4. Confirming: Repeatability & Productionizing

The final stage moves the logic from a "one-off script" to a resilient enterprise service that runs 24/7.

* **Job Orchestration:** Scheduling the "Optimizer" to run every 15 minutes, triggered by new lab assays or significant changes in inbound flow rates.
* **Failure Handling:** Coding "Failsafe" modes. If the AI loses connection to the LIMS, it must automatically signal the SCADA system to revert to a "Conservative/Safe" blend recipe.
* **Documentation & Governance:** Auto-generating a "Compliance Log" for every batch, creating a digital audit trail that proves to the downstream refinery exactly why their "Quality Bank" credit is justified.

---