# UNIJOS-student-fair-housing-price-detector
Linear Regression to detect overpriced student housing around the university of Jos using 100 jiji and Facebook listings

# UNIJOS Housing: Are Students Overpaying?

### The Problem

Students around Village, Farin Gada pay N150k to N450k for almost identical self-contains. No way to know fair price.

### What I Did

* Collected 100 houses from Jiji.ng and facebook (Oct 2026) - location, type, water, light, furnished, distance to UNIJOS
* Stored water/light/furnished as Yes/No for readability (converted to 1/0 for model)
* Trained Linear Regression to predict fair price
* Flagged OVERPRICED if actual is >20% above fair

### Key Results

* R2 = 0.71, MAE = ~N37k -> Model explains 71% of price variation
* 31 out of 100 houses flagged OVERPRICED
* Average overcharge in Village: N68k/year
* Biggest price driver: location (Village = +N90k vs Angwan Rogo), then has_water

### Visuals

![Actual vs Fair](images/price_vs_fair.png)

### What this means for students

If you're paying >20% above fair price, you're likely paying agent greed + location hype, not actual value.

### Files

* `data/unijos_100_yesno.csv` - Raw data (Yes/No format)
* `results/final_results.csv` - With fair_price, overpriced_pct, status
* `notebooks/model.ipynb` - Full training

### Limitations 

* Data is asking price from Jiji and facebook , not final paid price
* Yes/No hides quality (borehole 2hrs vs 24hrs both = Yes)
* Could improve with more data on security, road condition

### Next

Build Streamlit app: enter house details -> tells you if overpriced.
