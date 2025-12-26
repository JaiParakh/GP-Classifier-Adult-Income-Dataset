# Introduction
The goal of the project is to train a classifier using either GP or GE for
a modified version of the Adult Dataset. For this task, I chose GP over GE
for two reasons, first, I have a better understanding of GP as
compared to GE and second, since it’s a classification problem of 0
and 1, a simple math equation is easy to understand and is easier to
represent.


# Data Pre-Processing
This dataset is designed for a binary classification problem where
the goal is to predict whether a person’s annual income exceeds
$50K based on demographic and employment attributes. The target
variable income takes the value 1 if income > $50K and 0 otherwise.
The dataset contains 39,073 entries with 15 columns, including both
numerical and categorical features.
Out of the 14 remaining columns, excluding income, I dropped three
columns entirely, namely, fnlwgt, education, and native country.
1. fnlwgt: Kaggle mentions that it is the final sampling weight, so didn’t
see much use for this.
2. education: Since we already have education-num, I found it
redundant.
3. native-country: This was an interesting case, since 90% were USA,
didn’t see much point in keeping it.

The numerical columns were scaled using StandardScaler, and the
categorical columns were encoded, but by dropping the first column,
since it gave better accuracy as compared to the standard one-hot
encoding.


# GP Primitives/Functions
After a lot of experiments below primitives made it to the cut
- Addition
- Subtraction
- Multiplication
- Division
- Negative
- Tan
- Absolute
- If_Else
- Sin
- Cos
- Greater/Less Than

Five terminals were added as well for better results: 1, 0, -1, 0.5, 2


# Fitness Function
A multi-objective fitness function where the first objective is the fitness or accuracy score, second is the tree size, was used. This gave
much better results since larger trees were penalised. And it made
sure that no overfitting happened.


# Parameters Setup
After trying various parameters below are the values that produced
best results, with proper reasoning and other values that I tried for
the same.

- POPULATION_SIZE: 1000
- P_CROSSOVER = 0.65
- P_MUTATION = 0.4
- MAX_GENERATIONS = 150
- HALL_OF_FAME_SIZE = 15
- N_RUNS = 2
- TOURNAMENT_SELECTION_SIZE = 20
- Tree Size Parameters
  - MIN_TREE_HEIGHT = 2
  - MAX_TREE_HEIGHT = 8
  - LIMIT_TREE_HEIGHT = 10
 

# Result
Of all the numerous submissions received, mine ranked 4th in terms of accuracy!
