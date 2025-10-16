# Word Concreteness Prediction using BaysBERT & Literary Words

This project predicts the concreteness of words by integrating literary word features and using BaysBERT embeddings. It also provides an **interactive prediction interface**.

Sources:

Literary texts (e.g., Woolf, Joyce, Eliot)

Brysbaert Concreteness Dataset (human-rated concreteness scores)

Integrated Dataset Columns:


| Column           | Description                                     |
| ---------------- | ----------------------------------------------- |
| `word`           | Target word                                     |
| `concreteness`   | Avg human concreteness score                    |
| `conc_sd`        | Standard deviation of human ratings             |
| `percent_known`  | Familiarity percentage                          |
| `source`         | Literary author/source                          |
| `dom_pos`        | Dominant POS tag                                |
| `zipf_freq`      | Word frequency (from `wordfreq`)                |
| `word_len`       | Length of the word                              |
| `len_times_conc` | Interaction term for word length × concreteness |

✅ Output: Unified, structured dataset ready for processing.

</details>
<details> <summary><b>
  
🧹Step 2: Data Cleaning & Preprocessing</b></summary>

Handle missing values (drop or impute).

Convert object columns to categorical/numeric.

Validate distributions, outliers, and nulls.

Prepare X (features) and y (target = concreteness).

✅ Output: Clean numerical dataset for modeling.

</details>
<details> <summary><b>
  
📊Step 3: Exploratory Data Analysis (EDA)</b></summary>

Heatmaps → Check correlations among features.

Scatterplots → Visualize feature relationships.

Insights:

High zipf_freq → often more concrete.

Long words → tend to be abstract.

len_times_conc captures mixed behavior.

✅ Output: Analytical understanding of dataset structure.

</details>
<details> <summary><b></b>
                     
⚙️Step 4: Feature Engineering</b></summary>

Compute linguistic and psycholinguistic features:

zipf_freq (word frequency)

word_len (word length)

len_times_conc (interaction)

percent_known (normalized)

conc_sd

Drop irrelevant columns (word, source if unused).

✅ Output: Final feature matrix X and target y.

</details>
<details> <summary><b>📈 
  
Step 5: Model Training</b></summary>

Split data: Train/Test (80/20)

Scale features using StandardScaler.

Model: LinearRegression()

Metrics: R², MAE, RMSE

Visualization: Feature Importance Plot (coefficients)

✅ Output: Trained regression model + scaler objects.

</details>
<details> <summary><b>
💬 Step 6: Interactive Prediction Model</b></summary>

User Input: Type a new word.

Process:

Compute features dynamically (zipf_freq, word_len, etc.)

Convert to DataFrame with same feature columns

Scale using trained scaler

Predict using trained regression model

Display predicted concreteness

<details> <summary><b>

🚀 Step 7: Future Extensions</b></summary>

Add contextual concreteness using sentence embeddings.

Model metaphor interpretation via graph neural networks.

Integrate cross-linguistic concreteness measures.

Deploy on Streamlit for interactive LLM-style UI.

✅ Goal: Bridge human and machine understanding of abstractness and imagery.

</details>
