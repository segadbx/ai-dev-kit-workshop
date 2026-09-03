To implement a **Drilling Rig Predictive Maintenance** solution, an AI coding agent must evolve through four distinct stages. These skills bridge the gap between raw rig-floor telemetry (EDR/SCADA) and the maintenance back office (CMMS).

Here is the formalized skill set for an AI agent tasked with building this system:

---

## 1. Validating: Data Accessibility & Feasibility

The agent must first prove that a complete "health signal" for a critical component exists—from the sensor on the rig floor to a labeled failure record it can learn from.

* **Connectivity Audit:** Confirming the agent can poll high-frequency tags from the **EDR/SCADA Historian** (e.g., mud-pump discharge pressure, top-drive motor current, drawworks vibration, gearbox temperature) and query the **CMMS** for historical work orders and failure records.
* **Label Correlation Testing:** Performing a "Time-Series Alignment" to ensure that a failure logged in the CMMS at a given date maps back to the exact window of sensor data that preceded it—the model can only learn from a failure it can *find* in the telemetry.
* **Feasibility Check:** Determining whether the available sensors have enough **resolution and coverage** (sample rate, instrumented components) to actually detect the failure modes that matter—and confirming the fleet is homogeneous enough that a signal on one rig generalizes to another.

## 2. Scoping: MVP & Component Architecture

The agent defines the "Minimum Viable Product" to prevent high-cost NPT events without trying to instrument every bolt on the rig at once.

* **Component Mapping:** Identifying the "Critical-to-Uptime" assets—specifically the high-cost, high-frequency failure points (mud pumps, top drives, drawworks) that drive the majority of mechanical NPT.
* **Failure-Mode Prioritization:** Defining the boundaries of the MVP by targeting a small set of **detectable, expensive, and recurring** failure modes first (e.g., mud-pump fluid-end washout) rather than chasing rare, one-off events.
* **Interface Design:** Outlining a "Fleet Health Board" for the maintenance planner that shows each rig's critical components ranked by failure risk, with the recommended action and lead time.

## 3. Evaluating: Metrics & Backtesting

Before any alert reaches a rig manager, the model's logic must be stress-tested against historical fleet data to prove it would have caught real failures without drowning crews in false alarms.

* **The "Replay" Backtest:** Running the model against the last 12–18 months of historical telemetry to confirm it would have flagged known failures **with useful lead time**—and quantifying the NPT hours it would have saved.
* **False-Alarm Analysis:** Simulating the alert stream to measure precision/recall trade-offs—an over-sensitive model that generates constant false positives will be ignored, so tuning the alert threshold is as important as the model itself.
* **KPI Dashboarding:** Building the evaluation framework for the COO, focusing on:
  * **Mechanical NPT Reduction (%)**
  * **Average Failure Lead-Time (hours/days)**
  * **Alert Precision (confirmed-finding rate)**

## 4. Confirming: Repeatability & Productionizing

The final stage moves the logic from a "one-off script" to a resilient enterprise service that scores the entire fleet 24/7.

* **Job Orchestration:** Scheduling the scoring pipeline to run on a regular cadence (e.g., every 15 minutes) across all active rigs, triggered by new telemetry batches landing in the historian.
* **Failure Handling:** Coding "Failsafe" modes. If a rig's data feed drops or a sensor goes flatlined/stale, the system must flag the *data* as untrustworthy rather than silently emitting a "healthy" score—a false all-clear is worse than no signal.
* **Documentation & Governance:** Auto-generating a maintenance audit trail for every alert and action—linking the sensor signature, the model score, the raised work order, and the confirmed finding—so the reliability program can prove its ROI and continuously retrain on new labels.

---
