# 🕵️‍♂️ AutoSleuth — Knowledge-Based Vehicle Diagnostic System

A **Certainty Factor (CF) expert system** built with Python and Streamlit that diagnoses vehicle faults using forward-chaining inference across 73 logical rules.

> Developed as a Knowledge-Based Systems (KBS) course project at **Galala University**, powered by Arizona State University.

---

## 🧠 How It Works

The system implements the classic **3-step CF methodology** for reasoning under uncertainty:

1. **Evidence Logic** — For rules with multiple AND conditions, take the minimum certainty: `CF(E) = min(CF_E1, CF_E2, ...)`
2. **Apply Rule** — Compute hypothesis certainty: `CF(H,E) = CF(Evidence) × CF(Rule)`
3. **Combine CFs** — When multiple rules support the same hypothesis: `CF_combined = CF_old + CF_new × (1 − CF_old)`

---

## 🚗 Diagnostic Coverage

The system covers **6 major vehicle systems** with **73 inference rules**:

| System | Rules | Sample Faults |
|---|---|---|
| Engine & Mechanical | 15 | Fuel injector, throttle body, timing chain |
| Transmission | 8 | Clutch slip, solenoid failure, torque converter |
| Brakes & Wheels | 9 | ABS sensor, master cylinder, warped rotors |
| Electrical | 7 | Alternator failure, parasitic drain, BCM glitch |
| Exhaust, Fuel & Cooling | 7 | Head gasket breach, catalytic converter, EGR valve |
| Steering & Suspension | 4 | Strut failure, sway bar link, power steering pump |
| Combined Multi-System | 8 | Engine + transmission co-faults, charging collapse |

---

## ✨ Features

- **Forward Chaining Inference Engine** — Rules fire dynamically based on user-reported symptoms
- **Certainty Factor Combination** — Multiple triggered rules compound evidence for higher confidence
- **Explanation Facility** — Every diagnosis shows *why* each question was asked and *how* the conclusion was reached (step-by-step reasoning trace)
- **Ranked Diagnostic Output** — Results sorted by combined CF score, with the primary diagnosis highlighted
- **Dynamic Question Generation** — Only shows questions relevant to the selected symptom categories

---

## 🚀 Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/AutoSleuth-KBS.git
cd AutoSleuth-KBS
pip install streamlit
streamlit run app.py
```

Then open `http://localhost:8501` in your browser.

---

## 📊 Sample Results (Simulated Run)

| Rank | Diagnosis | Certainty Factor |
|---|---|---|
| 1 | Alternator Failure | 0.8939 |
| 2 | ABS Sensor / Module Failure | 0.8870 |
| 3 | Radiator Strangled | 0.5880 |
| 4 | Head Gasket Breach | 0.5866 |
| 5 | Brake Fluid Escaping | 0.5810 |

---

## 🛠️ Tech Stack

- **Python 3**
- **Streamlit** — interactive web UI
- **Custom CF Inference Engine** — built from scratch (no ML libraries)

---

## 👥 Team

Developed by a team of 7 students under the supervision of **Dr. Hebatalla Mohamed**.

---

## 📄 License

This project was created for academic purposes at Galala University.
