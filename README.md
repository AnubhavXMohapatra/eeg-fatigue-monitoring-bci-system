# Closed-Loop EEG-Based Cognitive Fatigue Monitoring System Using Real-Time BCI Signal Processing and Neurophysiological Modeling

## 📘 Overview
This project is a **closed-loop brain-computer interface (BCI) system** designed to detect cognitive fatigue in real time using **EEG signals** from the Muse 2 headset and simulated heart rate data. By leveraging frequency band analysis and neurophysiological modeling, the system identifies early, moderate, and critical levels of fatigue. A dynamic auditory alert system is triggered based on evidence-backed fatigue thresholds.

## 🎯 Objectives
- Stream and process EEG data from the Muse 2 headset using the Lab Streaming Layer (LSL).
- Extract alpha and beta wave powers to calculate cognitive fatigue.
- Simulate heart rate data, with future integration support for real HR datasets.
- Detect fatigue severity and trigger adaptive sound alerts.
- Visualize EEG and HR trends via generated plots.
- Export collected data for further analysis and research validation.

## 🧠 Inspiration & Research
Fatigue classification thresholds in this system are adapted from:

**Shen, J., Barbera, J., & Shapiro, C. M. (2006).**  
*"Distinguishing fatigue from sleepiness: Clinical and research perspectives."*  
_Sleep Medicine Reviews, 10(1), 63–76._  
[https://doi.org/10.1016/j.smrv.2005.05.004](https://doi.org/10.1016/j.smrv.2005.05.004)

Heart rate simulation logic is supported by validated open datasets, including the **MIT-BIH Normal Sinus Rhythm Database** and **PhysioNet’s Fantasia Dataset**, used for verifying realistic HR fluctuation ranges.

---

## 🛠 Tools & Technologies
- **Hardware**: Muse 2 EEG Headset
- **Streaming**: BlueMuse + Lab Streaming Layer (LSL)
- **Languages**: Python
- **Libraries**: `numpy`, `matplotlib`, `pygame`, `pylsl`
- **Signal Processing**: Real-time FFT for frequency band extraction
- **Alert System**: Sound-based alerts via `pygame.mixer`

---

## 📈 Features
- ✅ Real-time EEG signal acquisition via Muse 2
- ✅ Frequency band isolation (alpha: 8–12 Hz, beta: 12–30 Hz)
- ✅ Fatigue classification logic based on combined EEG & HR inputs
- ✅ Progressive alert system (1–3 dings) tied to fatigue severity
- ✅ Research-backed fatigue thresholds:
  - *Mild*: ≥10/50 (20%)
  - *Moderate*: ≥15/50 (30%)
  - *Serious*: ≥20/50 (40–50%)
- ✅ Data visualization saved as `fatigue_plot.png`
- ✅ Future expansion: live updating graphs & real HR input

---

## 📦 How to Run
```bash
pip install numpy matplotlib pygame pylsl
Start Muse Stream

Turn on your Muse 2 headset.

Open BlueMuse, and connect your Muse device.

Click "Start Stream" to stream EEG data via LSL (Lab Streaming Layer).

Add Sound File

Place a file named ding.mp3 in your project root directory.

This will be played when cognitive fatigue thresholds are crossed.

Run the Script
Execute the main fatigue detection script:

bash
Copy
Edit
python fatigue_monitor.py
View Results

After running, check your terminal for real-time fatigue assessments.

A file called fatigue_plot.png will be saved showing EEG and heart rate data trends.

A CSV file fatigue_data.csv will be saved with raw data for further analysis.
