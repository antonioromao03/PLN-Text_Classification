# Assignment Description

The aim of this assignment is to build NLP classifiers for a specific text classification task. For that, you may explore any of the techniques that we are exploring during the course, including pre-processing, feature extraction, and sparse vs dense feature representations (including word embeddings). In the scope of this first assignment, you can also use any "traditional" machine learning classifier, including Naive Bayes, Logistic Regression, Decision Trees, Random Forest, Support Vector Machine, Multi-Layer Perceptron, XGBoost, and so on. You may NOT use any deep learning architecture based on CNNs, RNNs, or Transformers.

While developing your assignment, you are expected to:

    - Have a good understanding of the data provenance and characteristics: when and from where it was collected, which text genre(s) and language(s) it covers, how it has been annotated, etc.
    - Make an exploratory data analysis of the provided dataset: how many classes, how many examples per class, word distribution (e.g. TF-IDF), etc. You should document your analysis with proper visualizations.
    - Choose sensible pre-processing and feature representation techniques, while trying to justify your choices. Consider using external resources, such as lexicons. For sparse representations, quantify the size of the feature space. For dense representations, you may adopt pre-trained word embeddings or train your own (depending on the problem). Again, try to justify your decisions.
    - Report your classifier results using appropriate metrics (Precision, Recall, F1, macro-F1, etc.). Undertake some kind of error analysis for your best-performing models, by trying to understand the reasons behind misclassifications.

Regarding model evaluation, you should start with a simple baseline, upon which you can compare your developments (different features, new classifier types, hyperparameter tuning, etc.). If available, do compare your work with any existing related work on the same problem. You are not expected to beat the state-of-the-art, but to frame your work in the context of any prior published achievements by others.
