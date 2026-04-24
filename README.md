# 📊 Experiment 15: Data Normalization and Data Type Conversion

---

## 🎯 Aim

To normalize numerical data and convert categorical data into numerical form using appropriate encoding techniques.

---

## 📚 Theory

### 🔹 1. Data Normalization

Data normalization is used to scale numerical features to a common range so that no single feature dominates others during analysis. In datasets where variables have different units (e.g., price vs units sold), direct comparison can be misleading.

Normalization ensures:

* Balanced contribution of features
* Improved comparability
* Better suitability for analytical models

---

### 🔹 2. Normalization Techniques Used

#### Min-Max Normalization

Scales values between 0 and 1 using:
[
X' = \frac{X - X_{min}}{X_{max} - X_{min}}
]

* Preserves relative differences between values
* Applied to features like **Price, Units_Sold, Discount**

#### Z-Score Normalization

Standardizes data using:
[
Z = \frac{X - \mu}{\sigma}
]

* Centers data around mean = 0
* Identifies values above or below average
* Applied to **Units_Sold**

#### Decimal Scaling

Scales values by dividing by powers of 10:
[
X' = \frac{X}{10^j}
]

* Reduces magnitude of large values
* Applied to **Price**

---

### 🔹 3. Key Observation from Normalization

Different normalization techniques represent the same data differently:

* Min-Max keeps values within a fixed range
* Z-score highlights deviation from average
* Decimal scaling simplifies magnitude

This shows that the choice of normalization depends on the objective of analysis.

---

### 🔹 4. Categorical Data Conversion

Categorical data cannot be directly used in numerical analysis. Therefore, it must be converted into numerical form while preserving its meaning.

---

### 🔹 5. Encoding Techniques Used

#### Label Encoding

* Assigns a unique integer to each category
* Used for columns like **Gender, City**

Limitation: introduces an artificial order between categories

---

#### One-Hot Encoding

* Creates separate binary columns for each category
* No ordering is assumed

Used for variables like **Payment Method, Product Category**

---

#### Dummy Encoding

* Similar to one-hot encoding but drops one column
* Prevents redundancy and multicollinearity

---

### 🔹 6. Key Observation from Encoding

* Label encoding is efficient but may introduce unintended relationships
* One-hot encoding preserves category independence but increases dimensionality
* Dummy encoding balances both by reducing redundancy

---

## ⚙️ Commands Used & Explanation

### Normalization

* `(X - min) / (max - min)` → Min-Max normalization
* `(X - mean) / std` → Z-score normalization
* `X / 10^j` → Decimal scaling

### Encoding

* `LabelEncoder()` → Converts categorical values into numerical labels
* `pd.get_dummies()` → Performs one-hot encoding
* `drop_first=True` → Implements dummy encoding

### Data Handling

* `pd.read_csv()` → Reads dataset
* Column operations using `df[...]`

---

## 📊 Output Summary

* Numerical features were successfully normalized using multiple techniques
* Differences between normalization methods were observed clearly
* Categorical variables were converted into numerical form
* Encoding methods ensured compatibility with data analysis

---

## ✅ Conclusion

The experiment demonstrates that proper preprocessing is essential before analysis. Normalization ensures that numerical features are comparable, while encoding enables categorical data to be used effectively. The choice of technique directly affects how the data is interpreted, making it important to select methods based on the nature of the dataset and the objective of analysis.

