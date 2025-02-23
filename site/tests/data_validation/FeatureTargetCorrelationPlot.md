# FeatureTargetCorrelationPlot

Visualizes the correlation between input features and model's target output in a color-coded horizontal bar plot.

**Purpose**: This test is designed to graphically illustrate the correlations between distinct input features and
the target output of a Machine Learning model. Understanding how each feature influences the model's predictions is
crucial - a higher correlation indicates stronger influence of the feature on the target variable. This correlation
study is especially advantageous during feature selection and for comprehending the model's operation.

**Test Mechanism**: This FeatureTargetCorrelationPlot test computes and presents the correlations between the
features and the target variable using a specific dataset. These correlations are calculated, graphically
represented in a horizontal bar plot, and color-coded based on the strength of the correlation. A hovering template
can also be utilized for informative tooltips. It is possible to specify the features to be analyzed and adjust the
graph's height according to need.

**Signs of High Risk**:
- There are no strong correlations (either positive or negative) between features and the target variable. This
could suggest high risk as the supplied features do not appear to significantly impact the prediction output.
- The presence of duplicated correlation values might hint at redundancy in the feature set.

**Strengths**:
- Provides visual assistance to interpreting correlations more effectively.
- Gives a clear and simple tour of how each feature affects the model's target variable.
- Beneficial for feature selection and grasping the model's prediction nature.
- Precise correlation values for each feature are offered by the hover template, contributing to a granular-level
comprehension.

**Limitations**:
- The test only accepts numerical data, meaning variables of other types need to be prepared beforehand.
- The plot assumes all correlations to be linear, thus non-linear relationships might not be captured effectively.
- Not apt for models that employ complex feature interactions, like Decision Trees or Neural Networks, as the test
may not accurately reflect their importance.