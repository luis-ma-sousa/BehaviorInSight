# BehaviourInSight — Automated Analysis of Rodent Behavioral Tests

## 🐭 About the Data: Behavioral Tracking with Bonsai

Behavioral data in this project was collected using **Bonsai**, an open-source visual programming framework for real-time behavioral tracking. Bonsai captures high-resolution video of freely moving rodents and outputs coordinate data (x, y positions over time) that can be transformed into rich behavioral metrics.

The tracking system records animal position frame-by-frame across three standard neuroscience behavioral paradigms, enabling automated extraction of locomotor, exploratory, and anxiety-related behaviors.

The raw coordinate data are processed through custom pipelines to generate interpretable behavioral metrics for downstream analysis.

---

## 🧠 Project Overview

**BehaviourInSight** is a collection of automated analysis pipelines for three widely-used behavioral tests in neuroscience research:

- **Open Field Test (OFT)** — measures general locomotor activity and anxiety-like behavior
- **Elevated Plus Maze (EPM)** — assesses anxiety through approach-avoidance conflict
- **Y-Maze** — evaluates spatial working memory through spontaneous alternation

Each pipeline transforms raw position coordinates into biologically meaningful metrics, enabling standardized, reproducible behavioral phenotyping across multiple animals.

---

## 📊 What Each Pipeline Does

### 1️⃣ **Open Field Test (OFT)**
The open field is a square arena where rodents naturally explore. Increased time in the center indicates lower anxiety, while preference for corners/edges suggests anxiety-like behavior.

**Extracted Metrics:**
- **Locomotor activity:** Total distance traveled, average speed, moving speed
- **Immobility detection:** Identifies stationary periods to distinguish active vs. passive behavior
- **Region-of-interest (ROI) analysis:** Time spent in center, corners, and corridors
- **Spatiotemporal exploration:** Latency to first entry into each ROI, exploration dynamics over time
- **2D density maps:** Kernel density estimation (KDE) visualizations showing spatially averaged exploration patterns

---

### 2️⃣ **Elevated Plus Maze (EPM)**
The EPM consists of two open arms and two closed arms elevated above the ground. Rodents naturally avoid open spaces, so time spent in open arms reflects reduced anxiety.

**Extracted Metrics:**
- **Locomotor activity:** Total distance, speed, and moving speed
- **Immobility detection:** Captures freezing behavior
- **ROI analysis:** Time spent in open arms vs. closed arms
- **Transitions:** Number of entries between closed and open arms (exploratory anxiety-dependent behavior)
- **2D density maps:** KDE plots showing spatial exploration preferences

---

### 3️⃣ **Y-Maze (Spontaneous Alternation)**
The Y-maze has three identical arms. Healthy rodents naturally alternate between arms, reflecting intact spatial working memory. Repetitive entries into the same arm suggest memory deficits.

**Extracted Metrics:**
- **Locomotor activity:** Distance, speed, and moving speed
- **Immobility detection:** Identifies inactive periods
- **ROI analysis:** Time spent in each arm, including the novel arm (if applicable)
- **Spontaneous alternation behavior:** Quantifies sequential arm entries to assess working memory
- **2D density maps:** KDE visualizations of spatial preferences

---

## 🔄 Streamlined Workflow

All three pipelines follow a consistent, modular structure:

1. **Data Ingestion**  
   Reads raw coordinate data (CSV/TXT) exported from Bonsai tracking software.

2. **Coordinate Processing**  
   Calculates instantaneous speed, cumulative distance, and movement states (moving vs. immobile).

3. **ROI Segmentation**  
   Defines regions of interest based on arena geometry and extracts time-based metrics for each zone.

4. **Behavioral Scoring**  
   Computes test-specific behaviors (e.g., center time, arm transitions, spontaneous alternation).

5. **Visualization**  
   Generates 2D kernel density estimation (KDE) heatmaps to represent spatially averaged exploration patterns.

6. **Batch Processing**  
   Processes multiple animals in a single run, outputting standardized metrics for statistical analysis.

---

## 🔑 Key Features

- **Fully automated:** Minimal manual intervention required after initial setup
- **Batch processing:** Analyze dozens of animals with a single script execution
- **Standardized output:** Consistent metric definitions across all tests
- **Visualization-ready:** Built-in plotting for quality control and presentation
- **Modular design:** Easy to adapt for custom arenas or additional ROIs

---

## 📂 Data and Notebooks Availability

Due to the unpublished nature of this research, raw tracking data and original notebooks are not included in this repository.

➡️ **Access can be provided upon reasonable request.**

---

## 🧰 Tools & Technologies

- **Language:** Python 3.9+
- **Core Libraries:** pandas, NumPy, scipy
- **Visualization:** Matplotlib, Seaborn
- **Spatial Analysis:** scikit-learn (KDE), shapely (ROI geometry)
- **Environment:** Jupyter Notebooks

---

## 📁 Repository Structure
```
BehaviourInSight/
├── data/                   # Processed coordinate data (not included)
├── notebooks/              # Analysis pipelines (available upon request)
│   ├── OpenField_Analysis_Pipeline.ipynb
│   ├── ElevatedPlusMaze_Analysis_Pipeline.ipynb
│   └── YMaze_Analysis_Pipeline.ipynb
├── outputs/                # Example visualizations and summary metrics
└── README.md
```

---

## 📌 Status

Finalized for portfolio demonstration. Future updates may include real-time analysis integration and web-based dashboards.

> 🧩 **Future release:**  
> Once the study is published, all source code, notebooks, and example datasets will be made publicly available here.

---

## 👨‍💻 Author

Luís Sousa — [LinkedIn](https://www.linkedin.com/in/luis-ma-sousa31) | [GitHub](https://github.com/luismasousa)

---

## 🔗 Related Projects

**[DeepWalk](https://github.com/luismasousa/DeepWalk)** — Machine learning classification of Parkinson's motor deficits using gait data

