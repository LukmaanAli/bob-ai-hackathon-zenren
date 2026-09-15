# Solution Overview

## What We Built

We built a Supply Chain Disruption Assistant & Fleet Utilisation Optimizer that helps logistics teams respond quickly when supply chains are disrupted.

The solution brings together shipment records, active disruption events, fleet availability, route options, and cold-chain temperature sensor readings in one operational workflow. Instead of manually checking separate spreadsheets and systems, an operator can ask IBM Bob questions such as:

“Which high-priority shipments are affected by the Rotterdam port strike?”

“What is the best alternative route for this refrigerated shipment?”

“Which idle refrigerated trucks can be redeployed today?”

“Has this vaccine shipment had a temperature excursion?”

The assistant identifies at-risk shipments, explains why they are affected, recommends alternative routing or carriers, matches unused fleet assets to urgent transport needs, and flags cold-chain temperature breaches before cargo reaches its destination.

This is designed as an operational decision-support tool. It does not replace logistics planners, quality teams, or formal regulatory review. Instead, it helps those teams focus first on the shipments and actions that require attention.
## How It Works

1 The system loads operational data.
The solution ingests shipment records, planned routes, carrier information, active disruption events, fleet asset availability, and cold-chain IoT temperature logs. For the hackathon prototype, this data is generated as realistic CSV files, but the same workflow can later connect to transportation-management systems, carrier APIs, port-status feeds, and IoT platforms.

2 The system identifies active disruptions.
Each disruption contains information such as its type, location, start time, expected duration, severity, and operational impact. Examples include a port strike in Rotterdam, severe weather near a shipping lane, a customs delay, or a geopolitical route closure.

3 The disruption engine maps events to shipments.
The system compares the disruption with each shipment’s origin, destination, intermediate ports, carrier, transport mode, and planned travel dates. A shipment is marked as affected when its route or delivery window overlaps with the disrupted area or service.

4 Affected shipments are prioritised by operational risk.
The system assigns each affected shipment a risk score. High-priority shipments, perishable goods, refrigerated cargo, high-value cargo, and shipments with short delivery windows receive greater urgency. This helps operators avoid treating every delay as equally important.

5 The routing engine evaluates alternatives.
For each affected shipment, the solution evaluates possible reroutes and carrier alternatives. It compares transit time, estimated delay, route exposure, available capacity, cost impact, cargo constraints, and cold-chain compatibility. The output is an explainable recommendation rather than only a raw route suggestion.

6 The fleet optimiser finds idle assets.
The system checks available trucks, containers, and other fleet assets that are currently idle or underused. It filters them by location, availability window, capacity, asset type, maintenance status, and refrigerated capability. Suitable assets are then matched to disrupted or high-priority shipment demand.

7 Cold-chain sensor logs are monitored continuously.
For refrigerated shipments, the solution analyses IoT sensor readings over time. It compares the recorded temperature against the shipment’s permitted temperature range and identifies excursions, repeated breaches, prolonged exposure, and recovery behaviour.

8 The cold-chain engine classifies severity.
Temperature events are classified as normal, advisory, major, or critical based on configurable thresholds. For example, a brief temperature increase that quickly returns to range may require monitoring, while a prolonged breach for a vaccine shipment may require immediate quarantine and quality review.

9 IBM Bob acts as the operational interface.
IBM Bob is the primary way an operator interacts with the solution. It translates natural-language questions into workflow calls, gathers relevant shipment, disruption, fleet, and sensor data, and returns a concise operational summary with recommended next steps.

10 The operator receives a clear, actionable response.
The final response identifies the affected shipment, explains the reason for the risk, shows recommended rerouting or asset redeployment options, highlights cold-chain concerns, and suggests the appropriate next action.
## Architecture Diagram

> See [`architecture.md`](architecture.md) for the detailed diagram.

[Optionally include a simple ASCII or Mermaid diagram here for quick reference.]

```
Data Sources
     │
     ▼
Python + Pandas
     │
     ▼
┌───────────────┬──────────────┬────────────────┐
│ Disruption    │ Idle Fleet   │ Cold-Chain IoT │
│ Impact        │ Matching     │ Monitoring     │
└───────┬───────┴──────┬───────┴───────┬────────┘
        └───────────────┼───────────────┘
                        ▼
             Action Recommendation
                        │
                        ▼
                  IBM watsonx
                        │
                        ▼
                   FastAPI API
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
          Database          Operations UI
              ▲
              │
           IBM Bob
```

## Key Design Decisions

| Decision | Rationale |
|---|---|
| [e.g., Used watsonx.ai for anomaly detection] | [e.g., Pre-trained models reduced time-to-value vs. building from scratch] |
| [Decision 2] | [Rationale 2] |
| [Decision 3] | [Rationale 3] |

## IBM Technologies Used

[Explain specifically HOW you used each IBM technology — not just that you used it.]

- **[IBM Tech 1, e.g., watsonx.ai]:** [How it was used — e.g., "Used the `ibm/granite-13b-instruct-v2` model via the Python SDK to classify anomaly types from log text."]
- **[IBM Tech 2]:** [How it was used]
