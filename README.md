1. Business Objective
The goal of this project is to train a Named Entity Recognition (NER) model using Conditional
Random Fields (CRF) to extract key entities from recipe data. The model classifies words into
predefined categories such as ingredients, quantities, and units, enabling the creation of a
structured database of recipes and ingredients. This can be used in recipe management
systems, dietary tracking apps, or e-commerce platforms.
2. Data Description
The data is in JSON format, representing a structured recipe ingredient list with NER labels. It
contains two fields:
● input: A raw ingredient list from a recipe.
● pos: Corresponding part-of-speech (POS) tags or NER labels, identifying quantities,
ingredients, and units.
3. Data Ingestion and Preparation
● Data Loading: A function load_json_to_dataframe was defined to read the JSON file into a
Pandas DataFrame.
● Data Exploration: The DataFrame was explored using head() to display the first five rows
and info() to show its structure.
● Data Cleaning: The input and pos columns were tokenized, and their lengths were
calculated and stored in new columns (input_length, pos_length).
Print the first five rows of train_df and val_df
4. Exploratory Data Analysis (EDA)
● Token Flattening: Functions were defined to flatten the lists of input tokens and POS tags.
● Token Extraction and Validation: Tokens were extracted and validated to ensure the
number of input tokens matched the number of POS tags.
● Token Categorization: Tokens were categorized into ingredients, units, and quantities.
● Frequency Analysis: The top 10 most frequent ingredients and units were identified and
visualized using bar plots.
○ Top 10 Ingredients: "powder", "Salt", "seeds", "Green", "chopped", "Oil", "Red",
"Chilli", "Coriander", and "Sunflower".
○ Top 10 Units: "teaspoon", "cup", "tablespoon", "grams", "tablespoons", "inch", "cups",
"sprig", "cloves", and "teaspoons".
Perform EDA analysis
5. Data Preprocessing
● Feature Engineering: Features were engineered to aid in entity recognition, including
context, numeric values, and keyword matching.
● Data Splitting: The dataset was split into training and validation sets (70:30 ratio).
6. Model Training
● CRF Model Initialization: A Conditional Random Fields (CRF) model was initialised with
specific hyperparameters.
● CRF Model Training: The CRF model was trained on the training data.
7. Model Evaluation
● Training Data Evaluation: The model's performance on the training data was evaluated
using a classification report and confusion matrix.
● Validation Data Evaluation: The model's performance on the validation data was assessed,
and error analysis was conducted to identify common misclassifications.

Confusion Matrix:
Prediction and Model Evaluation:
Confusion Matrix On Validation dataset:
8. Error Analysis
● Detailed Error Analysis: Errors were analysed to understand the model's failure points,
considering factors like class weights and token context.
● Error Categorization: Errors were categorised and analysed to identify patterns.
9. Results and Insights
● The CRF model achieved high overall accuracy in extracting key entities from recipe data.
● The model performed well on ingredient and quantity extraction but showed some
challenges with unit recognition.
● Error analysis revealed common misclassification patterns, such as confusion between
ingredients and units, and the impact of context on entity recognition.
10. Conclusion
A CRF model was successfully developed to extract key entities from recipe data. The model
achieved high overall accuracy, with room for improvement in specific cases. Future work could
focus on refining features and handling challenging scenarios. This project demonstrates the
effectiveness of CRF for recipe ingredient extraction, with potential applications in various
culinary domains.
