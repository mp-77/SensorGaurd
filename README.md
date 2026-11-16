# 🧟‍♂️ Zombie Survival: Survive Using Data (SensorGuard)

> A story-driven, interactive educational web application designed to teach **Introduction to Data Science & Engineering (IDSE)** core concepts through 5 playable, high-stakes tactical survival missions.

---

## 🎯 Overview & Lore

The dead have risen. Traditional supply lines and military logistics have collapsed. Your only weapons are logic, probability, and data science. As the tactical data analyst for the survivor convoy, you must guide your crew through 5 hazardous districts to reach the Evacuation Centre alive.

Every survival choice requires interacting directly with live datasets and simulations—no boring multiple-choice quizzes! Biased samples, poor classification thresholds, or bad regression models cause ambushes and resource drain. Disciplined data science keeps your team alive.

---

## 🎮 The 5 Playable Survival Missions

| Mission | Tactical Scenario | Target Data Science Concepts | Interactive Mechanic |
| :--- | :--- | :--- | :--- |
| **Mission 1: Safe Zone Recon** | Estimate zombie density across a 50-sector grid using limited drone battery scans. | **Sampling & Sampling Bias**<br>*(Convenience vs. Stratified Random)* | Interactive city sector grid; radar scan pings; compare Convenience vs. Stratified sample means against true population parameters. |
| **Mission 2: Quarantine Checkpoint** | Screen incoming refugees at the perimeter gate without admitting asymptomatic carriers or turning away healthy survivors. | **Classification & Decision Boundaries**<br>*(Confusion Matrix, TPR/FPR, Precision/Recall)* | 2D Scatter plot with distinct survivor avatars (healthy vs. infected); adjustable bio-marker classification threshold; confusion matrix tracker. |
| **Mission 3: Supply Drop Recovery** | Deploy retrieval teams to collect scattered high-priority supply crates across contested ruins. | **Unsupervised Clustering (K-Means)**<br>*(Centroids, WCSS, Elbow Heuristic)* | Interactive 2D coordinate grid; step-by-step centroid updates and cluster boundary recalculations; real-time inertia / WCSS minimization. |
| **Mission 4: Outbreak Diagnosis** | Triage sick personnel with limited vaccine doses given a imperfect rapid antibody diagnostic test. | **Bayes' Theorem & Base-Rate Fallacy**<br>*(Prior, Likelihood, Posterior $P(\text{Infected} \mid +)$)* | Prior prevalence & test accuracy sliders; interactive probability tree / unit square; calculate true posterior risk to prevent fatal undertreatment. |
| **Mission 5: Highway Convoy Escape** | 120 km final dash to the Evacuation Centre while outrunning a horde. Predict exact fuel consumption based on cargo load and speed. | **Linear Regression & Outlier Detection**<br>*(Least Squares, Residuals, MSE, $R^2$)* | Telemetry scatter chart with damaged sensor anomalies; toggle outliers; auto-fit / manual slope & intercept; calculate fuel requirements. |

---

## 🛠️ Key Features

- **Persistent Tactical HUD:** Real-time monitoring of **Health (HP)**, **Food**, **Medicine**, and **Fuel**, with animated visual indicators and consequence feedback.
- **Two-Tier Mission Hint System:**
  - *Tier 1 (Conceptual Clue):* Explains what mathematical or statistical pattern to look for without spoiling answers.
  - *Tier 2 (Actionable Strategy):* Step-by-step tactical adjustments for chart sliders, filters, or sample sizes.
- **Dynamic Performance-Based Grading:** Composite scoring based 60% on mathematical mission accuracy + 40% on conserved resources:
  - **S Rank (90–100%):** *Apex Data Survivor — Fully Protected from Zombies*
  - **A Rank (75–89%):** *Tactical Analyst — Safe Behind Perimeter*
  - **B Rank (60–74%):** *Field Survivor — Made It Through Bruised*
  - **C Rank (40–59%):** *Scraped By — Narrow Escape*
  - **D Rank (<40%):** *Critical Condition — Overrun Risk*
- **Instruction Manual & Field Manual:** In-game tactical reference guide and mathematical formula sheets accessible at any time.
- **Story-Driven Radio Comms:** Typewriter radio transmission dialogue modals with tactical portraits (*Commander Vance, Dr. Aris, Scout Maya, Jax*).
- **Custom Visuals & Atmospheric Background:** Shambling zombie silhouettes, watchtower searchlights, ash particle effects, and distinct human vs. infected biometric markers.
- **Synthesized Audio Engine (Web Audio API):** Zero external `.mp3` files! Features an atmospheric ambient A-minor synth pad music loop, zombie groans, alarms, clicks, and independent **Music ON/OFF** and **SFX ON/OFF** toggles.

---

## 💻 Tech Stack

- **Framework:** [React 18](https://react.dev/) + [Vite](https://vitejs.dev/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/) (Tactical HUD / Post-apocalyptic dark terminal theme)
- **Visualizations:** [Recharts](https://recharts.org/) + Custom SVG Canvas & Data Markers
- **Icons:** [Lucide React](https://lucide.dev/)
- **Audio Engine:** Native Browser Web Audio API (`AudioContext`, Oscillator nodes, BiquadFilter, Gain envelopes)

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- `npm` or `yarn`

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/PurnaChandRaja05/SensorGaurd.git
   cd SensorGaurd/zombie-survival
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open your browser and navigate to `http://localhost:5173`.

### Production Build

To test and compile for production:
```bash
npm run build
npm run preview
```

---

## 📁 Project Structure

```text
idse/
├── .gitignore
├── README.md
└── zombie-survival/
    ├── index.html
    ├── package.json
    ├── vite.config.js
    └── src/
        ├── App.jsx                       # Root application shell & screen routing
        ├── main.jsx                      # Vite entry point
        ├── index.css                     # Tactical styling, scanline & keyframe animations
        ├── context/
        │   └── GameContext.jsx           # Global game state, inventory HUD & scoring engine
        ├── components/
        │   ├── HUD.jsx                   # Persistent tactical top bar (HP/Food/Med/Fuel/Audio)
        │   ├── DialogueModal.jsx         # Radio transmission dialogue pop-ups
        │   ├── MissionHint.jsx           # Two-tier interactive tactical hint drawer
        │   ├── FieldManual.jsx           # Mathematical formula & concept cheatsheet
        │   ├── InstructionManual.jsx     # "How to Play" rulebook modal
        │   ├── StartScreen.jsx           # Title screen & campaign launcher
        │   ├── MissionBriefing.jsx       # Pre-mission tactical briefings
        │   ├── EvacuationScreen.jsx      # Final debrief, dynamic grading & grade tier legend
        │   ├── GameOverScreen.jsx        # Out-of-resources retry modal
        │   └── ZombieBackground.jsx     # Animated silhouettes, searchlight & ash particles
        ├── missions/
        │   ├── Mission1.jsx              # Sampling & Sampling Bias (50-Sector Recon)
        │   ├── Mission2.jsx              # Classification & Confusion Matrix (Gate Checkpoint)
        │   ├── Mission3.jsx              # K-Means Clustering (Supply Drop Optimization)
        │   ├── Mission4.jsx              # Bayes' Theorem (Antibody Test & Base-Rate Triage)
        │   └── Mission5.jsx              # Linear Regression & Outliers (Convoy Fuel Dash)
        └── utils/
            └── soundEngine.js            # Pure Web Audio API procedural synthesizer
```

---

## 📜 License

This project is created for educational and interactive instructional purposes. Released under the [MIT License](LICENSE).

