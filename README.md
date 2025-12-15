
## Overview

This repository contains the final deliverables for **INFO 4125 (Project Management)**, focused on building a predictive model that estimates library occupancy at Cornell University. The goal of the project is to improve students’ ability to find available study spaces by providing time-based occupancy predictions for selected campus libraries.

The project combines data preprocessing, predictive modeling, and interface prototyping to demonstrate a proof-of-concept system that could support more transparent and efficient use of shared academic spaces.

---

## Repository Structure

```
info4125project/
│
├── Data/
│   ├── library_occupancy_data.csv
│   ├── library_occupancy_MS3.csv
│   └── prelim_dates_fall2025.csv
│
├── Models/
│   ├── initial_model.ipynb
│   ├── Updated_Model.ipynb
│   ├── Updated_Model_MS3.ipynb
│   ├── most_recent_Model_MS3.ipynb
│   └── Final_Model.ipynb
│
├── Notebooks/
│   ├── preprocessing.ipynb
│   └── main_file.ipynb
│
├── requirements.txt
└── README.md
```

* **Data/** contains cleaned and synthetic datasets used for training and evaluation.
* **Models/** contains model development notebooks documenting the evolution from initial experiments to the final model.
* **Notebooks/** contains preprocessing and exploratory analysis notebooks.
* **Final_Model.ipynb** is the primary execution artifact and represents the final version of the predictive model.

---

## Predictive Model Description

To build the predictive model, our team initially collected real library occupancy data manually over several days. However, this two-week dataset proved insufficient for training an accurate and stable model, resulting in limited predictive performance. To address this constraint and accelerate development, we generated additional synthetic data using ChatGPT, spanning the months of October through November. The synthetic data preserved the structure and temporal trends observed in the real samples while increasing overall data volume.

While synthetic data enables pattern learning under time constraints, it does not fully capture the variability of real-world student behavior. As a result, all reported accuracy metrics should be interpreted as **proof-of-concept benchmarks rather than deployment-ready guarantees**. With the expanded dataset, the model was able to capture consistent temporal patterns in library usage, improving overall performance to approximately **75% accuracy**, defined as predictions falling within an acceptable deviation threshold from observed occupancy counts.

---

## Model Evaluation

Model performance was evaluated using held-out data that the model had not previously seen. Predicted occupancy values were compared against actual values and visualized using scatter plots, where closer alignment with the diagonal indicates stronger performance.

* **Mann Library** exhibited particularly strong predictability, reflecting consistent usage patterns.
* **Olin and Uris Libraries** showed close alignment with real data, with higher variance during peak academic hours.
* **Math Library** displayed a distinct pattern due to extended operating hours and lower late-night occupancy.

We experimented with multiple feature sets, starting with temporal features such as hour of day and day of week, and later incorporating operational features including library closing hours and prelim-period indicators. Each additional feature resulted in incremental improvements in predictive accuracy, confirming their relevance to occupancy behavior. Across libraries, prediction error ranged approximately between **25 and 65 people**, depending on usage variability.

---

## Execution and Reproducibility

All modeling work was consolidated into a single, well-documented Jupyter notebook (`Final_Model.ipynb`), which serves as the central execution artifact for the project. The notebook is organized into clear sections for data preparation, feature engineering, model training, evaluation, and visualization, enabling reproducibility and ease of review.

Intermediate notebooks in the `Models/` directory document earlier iterations and experiments, providing transparency into the development process. The repository is structured to support future extensions, including integration with real-time data sources, live deployment, and formal user testing.

---

## Team Contributions

This project was completed collaboratively by **Team 3** for INFO 4125.

* **Data Subteam:** Wassan Nasreddin, Jinpeng Li, Nick-Aurel Mugirashaka
* **Design Subteam:** Chengling Zheng, Goretti Muriithi, Fiona Huang, Jocelyn Wong

Responsibilities were divided to allow parallel progress on modeling and interface design while maintaining alignment through shared documentation and regular check-ins.

---

## Limitations and Future Work

This project represents a functional prototype rather than a production-ready system. Key limitations include the use of synthetic data, the absence of real-time deployment, and the lack of formal user interviews during this iteration. Future work would focus on integrating live occupancy data, conducting structured user testing, improving model robustness during peak periods, and deploying the system as a unified web platform.

---

## Requirements

To run the notebooks locally, install dependencies listed in:

```
requirements.txt
```

---


