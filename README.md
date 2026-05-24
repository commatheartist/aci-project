# Approach per Count Index (ACI)

A public baseball analytics project evaluating MLB hitter approach quality using Statcast pitch-level data.

**Live App:**
[https://aci-baseball.streamlit.app/](https://aci-baseball.streamlit.app/)

---

# What is ACI?

The **Approach per Count Index (ACI)** measures hitter decision-making quality by evaluating swing/take decisions within the context of:

* Count leverage
* Pitch location
* Personalized hot/cold zones
* Damage-hunting philosophy
* Intelligent 2-strike protection

Unlike traditional offensive metrics, ACI is:

> **process-focused rather than outcome-focused**

meaning the model evaluates the quality of a hitter’s approach independent of whether the result was a hit, out, strikeout, etc.

---

# Formula

```text
ACI = Good Decisions / Total Pitches Seen
```

Each pitch is scored binary:

```text
1 = Good Decision
0 = Poor Decision
```

based on game context and approach philosophy.

Only hitters in the **top 25% of MLB pitch volume** are included to stabilize decision-quality samples.

---

# Examples of Positively Scored Decisions

* Swinging at damage pitches in advantage counts (2-0, 2-1, 3-1)
* Taking edge/shadow pitches when ahead
* Attacking hitter-specific hot zones
* Punishing elevated hanging breaking balls
* Protecting competitive pitches with 2 strikes
* Taking obvious chase pitches with 2 strikes

---

# Context Matters

ACI evaluates decisions relative to count leverage and hitter intent.

For example:

* A take on the edge at **2-0** may be scored positively
* That same take at **2-2** may be scored negatively due to protection expectations

The same pitch can therefore receive different evaluations depending on count context.

---

# Current Model Features

* Pitch-level Statcast ingestion via `pybaseball`
* Personalized hitter hot/cold zones
* Count-based approach framework
* Geometry-based pitch evaluation using `plate_x` and `plate_z`
* Righty/lefty compatible pitch-location logic
* Public Streamlit leaderboard
* Search + team filters
* Percentile rankings

---

# Tech Stack

* Python
* Pandas
* PyBaseball
* Streamlit
* GitHub
* MLB Statcast Data

---

# Repository Structure

```text
aci-project/
│
├── ACI_prod.ipynb      # Main modeling notebook
├── aci.csv             # Processed leaderboard output
├── app.py              # Streamlit app
├── README.md
```

---

# Future Development Ideas

* Hunting / Pivot / Survival sub-scores
* Rolling 7/14/30 day ACI trends
* Player detail pages
* Team dashboards
* Swing decision heatmaps
* Correlations between ACI and offensive production
* Slump/recovery analysis

---

# Author

**Brandon Smith**
Baseball Analytics Portfolio:
[https://medium.com/@WinsAboveSmitty](https://medium.com/@WinsAboveSmitty)

---

# Disclaimer

ACI is an independent baseball analytics project and is not affiliated with MLB or any MLB organization.
