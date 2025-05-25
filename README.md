# 🐭 6170 Animal Cognition Course | HUJI
### Behavioral Dataset: Group-Housed Mice in Enriched Environments  

This repository contains data from a set of experiments described in the paper:  
📄 [Forkosh et al., Nature Neuroscience (2019)](https://www.nature.com/articles/s41593-019-0516-y)

In each experiment, **four adult male mice** were housed together for **four or more days** in a **shared enriched arena**. The arena included:  
- A closed nest  
- Two feeders  
- Two water bottles  
- Two ramps  
- An open shelter  
- An S-shaped separation wall in the center  

---

## 📁 File: `daily.csv`  
This CSV file contains **daily behavioral metrics** for each mouse.

### 📌 Structure  
Each row represents **one mouse on one day** of the experiment.

**Key columns:**
| Column         | Description |
|----------------|-------------|
| `Day`          | Day of the experiment (usually between 1–4) |
| `MouseNumber`  | Unique identifier for the mouse |
| `MouseID`      | ID of the mouse within its group (usually 1–4) — note: `MouseID` is **not** globally unique |
| `GroupNumber`  | Group ID (use this, rather than `GroupID`) |
| `GroupID`      | [⚠️ Deprecated] Avoid using this — `GroupNumber` is preferred |

In addition to these identifiers, each row includes a rich set of **behavioral metrics**, described below.

---

## 🧠 Behavioral Traits & Metrics

The features fall into two categories:

- **Pairwise Metrics**: Social interactions and comparisons with other mice  
- **Individual Metrics**: Exploration, movement, preferences, and spatial behavior

### 🔁 Pairwise Behavioral Metrics  

| Behavior | Description |
|----------|-------------|
| **Time outside** | Fraction of time the mouse is outside the nest |
| **Visit rate outside** | How often the mouse exits the nest |
| **Foraging correlation** | Synchrony with other mice in being outside |
| **Contact rate & time** | Number and duration of contacts with other mice (<10 cm apart outside the nest) |
| **Follow / Being followed** | Times one mouse follows or is followed by another after contact (aggressive or not) |
| **Chase / Escape** | Chases another or is chased aggressively (machine-classified) |
| **Approach / Being approached** | Initiates or receives directed approach ending in contact |
| **Approach-escape** | Initiates contact but ends up being chased |
| **Approach–chase difference** | Difference between number of approaches and chases |

### 🔍 Individual Behavioral Metrics  

| Behavior | Description |
|----------|-------------|
| **Exploration (ROI & grid)** | Entropy-based measure of how uniformly the mouse explores regions or grid |
| **Predictability** | Mutual information between successive locations (6×6 grid) |
| **Distance traveled** | Total path length outside the nest |
| **Speed (mean / median)** | Movement speed outside the nest |
| **Tangential / Angular velocity** | Measures of movement path curvature |
| **Food & water zone use** | Time spent near feeders and water bottles |
| **Feeder / Water preference** | Bias toward feeder/water location closer to nest |
| **Elevated area / Ramps / S-wall / Shelter / Open area** | Time spent in various zones |
| **Distance from walls / nest** | Spatial positioning in open area |
| **Alone outside** | Time spent outside when all others are in the nest |

### 📏 Notes on Units & Normalizations

Each metric includes one or more **normalized versions**, e.g.:
- Per hour of total time (`per 1 h`)
- Per hour of time outside the nest
- Per contact
- As a fraction of total time
- Arbitrary units (`a.u.`), where a unit does not have a direct physical meaning but is consistent across comparisons

You can refer to the original paper for deeper methodological details and normalization logic.
