In the midstream sector, blending is less about chemical manufacturing and more about **value-added logistics**. Midstream companies act as the "gatekeepers" of quality between the wellhead and the refinery.

The core challenge is managing **Common Stream Integrity**: ensuring that as various grades of crude or NGLs (Natural Gas Liquids) are gathered, the resulting "blend" meets the strict tariff specifications of downstream pipelines and the "Quality Bank" requirements of refineries.

---

## Use Case: Midstream Crude Grade Optimization & Transmix Management

### 1. The Business Drivers: "The Quality Bank"

In a pipeline system, shippers are often compensated or penalized based on the quality of the oil they inject versus the quality of the "common stream" they withdraw. This is managed through a **Quality Bank**.

- **Penalty Avoidance:** If a midstream operator delivers a batch that is "off-spec" (e.g., too much Sulfur or too high a Vapor Pressure), the downstream pipeline can reject the entire batch, forcing a costly "pump-back" or an emergency sale at a steep discount.
- **Volume Expansion (The "Heavy-Light" Spread):** Midstreamers aim to blend cheaper, heavier crudes into higher-value light streams up to the maximum allowable limit of the pipeline tariff. This "volume gain" is a primary profit lever.
- **Transmix Recovery:** "Transmix" is the unavoidable mixture of different products created at the interface between batches in a pipeline. Optimizing the re-blending of this transmix back into "on-spec" tanks is critical for minimizing waste.

---

### 2. The Root Cause: "The Information Gap"

The primary reason for margin erosion in midstream blending is the **decoupling of scheduling from physical chemistry**.

- **Assay Latency:** Operators often rely on "Representative Assays"—data that might be 30 days old—to set blend ratios for a stream that is changing in real-time as different producers turn wells on or off.
- **Stratification in Storage:** Large terminal tanks often "stratify" (heavier oil settles at the bottom). If the blender pulls from the bottom of a tank without updated sensor data, the resulting blend will be heavier than the model predicted.
- **Inbound Ticket Drift:** Small errors in the "Shipper’s Ticket" (the self-reported quality from the producer) accumulate. Without automated verification, the midstreamer inherits the producer's quality risk.

---

### 3. Implementation: Integrated Terminal Management

A comprehensive solution bridges the gap between the **Commercial Contract (CTRM)** and the **Terminal Automation System (TAS)**.


| Component                   | Function in Midstream Context                                                                                                                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Inbound Monitoring**      | Integrated Coriolis meters and online densitometers provide a "live" density and viscosity profile of incoming batches.                                                                                            |
| **Dynamic Recipe Logic**    | Instead of a fixed 90/10 blend, the system uses a **Proportional-Integral-Derivative (PID)** loop to adjust the injection rate of "diluent" or "heavy" components based on the real-time density of the main line. |
| **Inventory Visualization** | Digital Twin of the tank farm that tracks the "quality weighted average" of each tank, accounting for heel, inflow, and stratification.                                                                            |
| **Settlement Integration**  | Automatically links the "As-Blended" quality to the "Quality Bank" ledger to forecast credits or debits before the batch even reaches the delivery point.                                                          |


---

### 4. Target Outcomes & Success Metrics

The implementation transforms the terminal from a "pass-through" asset into a "margin-capture" engine.

- **Metric 1: Downgrade Volume Reduction.** Minimizing the number of barrels that have to be sold as a lower grade (e.g., selling WTI as Western Canadian Select) due to quality drift.
- **Metric 2: Tariff Limit Adherence.** Maintaining the blend at **98% of the pipeline’s maximum allowable RVP or Sulfur limit**. Being "too safe" means leaving money on the table; being "off-spec" means paying a penalty.
- **Metric 3: Demurrage & Pumping Efficiency.** Reducing the "re-circulating" of tanks for re-blending, which frees up pipeline capacity and reduces the power costs of pumps.

> **Executive Insight:** "By integrating our LIMS (Lab) data directly into our Terminal Automation, we moved from a reactive 'blend-and-test' model to a proactive 'test-while-blending' model, effectively capturing an additional $0.15–$0.40 per barrel in common-stream optimization."

---

