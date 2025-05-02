# DF Final Demo Analysis & A/B Test

## Table of Contents

* [Project Overview](#project-overview)
* [Repository Structure](#repository-structure)
* [Data Description](#data-description)
* [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)

* [Hypotheses](#hypotheses)
* [Recommendations & Next Steps](#recommendations--next-steps)
* [Getting Started](#getting-started)

  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Usage](#usage)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

---

## Project Overview

This project analyzes client behavior and funnel performance for a banking web platform. Key objectives include:

1. Profiling client demographics and account tenure.
2. Identifying "prime" clients based on login frequency and balance.
3. Comparing control vs. test groups through A/B testing on the web conversion flow.
4. Measuring anomaly rates in funnel progression.
5. Conducting statistical tests to assess significance.
6. Formulating data-driven recommendations for optimization.

---

## Data Description

* Client demographics aggregated by age and tenure.

  * `age_group`: older (>35), younger (<35)

* Subset of "prime clients" with ≥7 logins in 6 months.

*  Client classification based on balance and tenure.

  * `premium_client`: balance ≥1,000,000
  * `regular_client`: balance <1,000,000
  * `loyal_client`: tenure ≥60 months; otherwise `newer_client`

* **Web Funnel Data**:

  * `df_web_data_control_start` / `df_web_data_control_confirm` (Control group)
  * `df_web_data_test_start` / `df_web_data_test_confirm` (Test group)

* **Transition Times**:

  * `df_transition_times_control` / `df_transition_times_test`: Step-to-step duration for all users.
  * `df_avg_duration_success_control` / `df_avg_duration_success_test`: Mean durations for successfully completed flows.

* **Anomaly Data**:

  * `df_flagged_control` / `df_flagged_test`: Flagged records where step sequence is abnormal.

---

## Exploratory Data Analysis (EDA)

### Demographic Insights

* **Younger vs. Older Clients**: Younger clients (<35) visit the platform more often on average, but older clients (>35) hold 90% of total balances and tend to have more accounts and calls.

* **Tenure Distribution**: Clients are split into "new" (<2 years) and "established" (>2 years) groups to assess loyalty and activity patterns.

### Prime Clients

* Defined as clients with ≥7 logins per 6-month period.
* Majority of prime clients are older, indicating higher engagement among experienced users.

---

## Hypotheses

1. **Completion Rate Improvement**

   * H0: Test completion rate ≤ Control completion rate
   * H1: Test completion rate > Control completion rate

2. **Anomaly Reduction**

   * H0: Control anomalies ≥ Test anomalies
   * H1: Control anomalies < Test anomalies

Statistical results reject H1 for both tests, indicating the new design did not improve completion and increased anomalies.

---

## Recommendations & Next Steps

* **Design Iteration**: Refine the step flow to reduce anomalies; ensure correct flagging logic.
* **Qualitative Feedback**: Implement user surveys to capture pain points.
* **Technical Documentation**: Document data collection, anomaly detection, and anomaly definitions for reproducibility.

---

## Getting Started

### Prerequisites

* Python 3.8+
* pandas, seaborn, matplotlib.pyplot, scipy.stats, scipy.stats

### Installation

1. Clone the repo:

   ```bash
   git clone https://github.com/your-username/df-final-demo.git
   cd df-final-demo
   ```
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

* Launch Jupyter Notebook:

  ```bash
  jupyter notebook notebooks/Main.ipynb
  ```
* Explore EDA steps, rerun analyses, and adjust parameters as needed.

---

## Contributing

Contributions are welcome! Please:

1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/YourFeature`.
3. Commit your changes: `git commit -m "Add new analysis"`.
4. Push to your branch: `git push origin feature/YourFeature`.
5. Open a Pull Request.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## Contact

* **Author**: Modris12
* **Email**: modris.opelts@gmail.com
* **GitHub**: https://github.com/Modris12

* **Author**: JorgeMMLRodrigues
* **Email**: jorgemmlrodrigues@gmail.com
* **GitHub**: https://github.com/JorgeMMLRodrigues

* **Author**: 
* **Email**: atefah.hassani@gmail.com
* **GitHub**: 

* **Author**:
* **Email**: michelemontalvo@outlook.com
* **GitHub**: 

Feel free to open issues or reach out for collaborations. Good luck!
