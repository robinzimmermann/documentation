# DescriptiveAnalytics

Evaluates statistical properties of text embeddings in an ML model via mean, median, and standard deviation
histograms.

**1. Purpose:**
This metric, Descriptive Analytics for Text Embeddings Models, is employed to comprehend the fundamental properties
and statistical characteristics of the embeddings in a Machine Learning model. It measures the dimensionality as
well as the statistical distributions of embedding values including the mean, median, and standard deviation.

**2. Test Mechanism:**
The test mechanism involves using the 'DescriptiveAnalytics' class provided in the code which includes the 'run
function. This function computes three statistical measures - mean, median, and standard deviation of the test
predictions from the model. It generates and caches three separate histograms showing the distribution of these
measures. Each histogram visualizes the measure's distribution across the embedding values. Therefore, the method
does not utilize a grading scale or threshold; it is fundamentally a visual exploration and data exploration tool.

**3. Signs of High Risk:**

- Abnormal patterns or values in the distributions of the statistical measures. This may include skewed
distributions or a significant amount of outliers.
- Very high standard deviation values which indicate a high degree of variability in the data.
- The mean and median values are vastly different, suggesting skewed data.

**4. Strengths:**

- Provides a visual and quantifiable understanding of the embeddings' statistical characteristics, allowing for a
comprehensive evaluation.
- Facilitates the identification of irregular patterns and anomalous values that might indicate issues with the
machine learning model.
- It considers three key statistical measures (mean, median, and standard deviation), offering a more well-rounded
understanding of the data.

**5. Limitations:**

- The method does not offer an explicit measure of model performance or accuracy, as it mainly focuses on
understanding data properties.
- It relies heavily on the visual interpretation of histograms. This could be subjective, and important patterns
could be overlooked if not carefully reviewed.
- While it displays valuable information about the central tendency and spread of data, it does not provide
information about correlations between different embedding dimensions.