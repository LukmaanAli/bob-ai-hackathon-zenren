# 🚀 Supply Chain Disruption Assistant & Fleet Utilisation Optimizer


## 👥 Team

| Field | Value |
|---|---|
| **Team Name** | ZENREN |
| **Track** | AI  |
| **Team Lead** | LukmaanAli — lukmaanali313@gmail.comm |
| **Members** | Om Tapaniya, LukmaanAli, Dhruv, Adnan Vora |

---

## 🎯 Problem Statement

> In 2–3 sentences: What problem does your project solve? Who experiences this problem?

Weather events, port strikes, geopolitical crises, and infrastructure failures can cascade across hundreds of active shipments. Operations teams must manually correlate disruption notices, shipment records, route constraints, available vehicles, and sensor logs.

This creates delayed decisions, underused fleet capacity, avoidable rerouting costs, and late discovery of cold-chain temperature excursions. When a temperature breach is discovered only at delivery, high-value cargo may already be unusable.
---

## 💡 Solution

> In 2–3 sentences: What did you build? How does it solve the problem above?

Our solution provides a unified operational view of shipment and fleet risk. It uses Bob to interpret operational questions, call the relevant workflows, and return prioritised recommendations.

The system identifies shipments affected by an active disruption, estimates impact, recommends feasible reroutes or alternative carriers, matches idle fleet assets to urgent demand, and analyses cold-chain sensor logs for temperature excursions.
---

## ✨ Key Features

- **Feature 1:** Active-disruption impact analysis.
- **Feature 2:** Rerouting and alternative-carrier recommendations.
- **Feature 3:** Idle truck, container, and vessel identification.
- **Feature 4:** Fleet redeployment matching based on location, capacity, equipment, and availability.

---

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| **Languages** | Python |
| **Frameworks** | FastAPI |
| **IBM Technologies** |IBM Bob workflow integration, IBM watsonx  |
| **Databases** | PostgreSQL|
| **Other** | Mermaid |

---

## 📁 Repository Structure

```
├── src/                  # All source code
├── docs/                 # Written documentation
│   ├── problem-statement.md
│   ├── solution-overview.md
│   ├── architecture.md
│   └── setup-guide.md
├── demo/                 # Demo artifacts
│   ├── screenshots/      # App screenshots
│   └── demo-video-link.txt  # Link to demo video
├── presentation/         # Slide deck
└── submission.yaml       # Structured submission metadata
```

---

## ⚡ How to Run

> **Copy these exact steps from your [`docs/setup-guide.md`](docs/setup-guide.md)**

```bash
# 1. Clone the repo
git clone https://github.com/LukmaanAli/bob-ai-hackathon-zenren.git
cd bob-ai-hackathon-zenren

# 2. Install dependencies
pip install -r requirements.txt

# 3. Configure environment
copy .env.example .env

# Edit .env with your values

# 4. Run the project
uvicorn main:app --reload
```

---

## 🖥️ Demo

| Artifact | Link |
|---|---|
| 📹 Demo Video | [See demo/demo-video-link.txt](demo/demo-video-link.txt) |
| 🌐 Live Demo | [See demo/live-demo-url.txt](demo/live-demo-url.txt) |
| 🖼️ Screenshots | [See demo/screenshots/](demo/screenshots/) |
| 📊 Presentation | [See presentation/slides.pdf](presentation/) |

---

## ⚠️ Known Limitations

> Be honest — judges appreciate transparency over overclaiming.

- Route recommendations are evaluated using a constrained scoring model rather than a production-grade global optimisation engine.
- Regulatory classification is decision support and does not replace quality, safety, or compliance review.
- Fleet availability and route conditions may become stale without real-time integrations.


---

## 🏅 What We're Most Proud Of

[Tell the judges what part of your submission is strongest and worth paying close attention to.]

---
