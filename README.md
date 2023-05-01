# textmining_sklearn

<h3>Introduction</h3>
The purpose of this code is to predict the category of discussion posts in a newsgroup. The unit of analysis is a
discussion post.

<h3>Package Imports</h3>
This code uses the following packages:

<ol>
    <li>pandas for data manipulation</li>
    <li>numpy for numerical operations</li>
    <li>sklearn for machine learning algorithms</li>
    <li>nltk for natural language processing</li>
</ol>



<h3>Loading Data</h3>
This code reads a CSV file called news.csv using pandas.

<h3>Data Cleaning</h3>
This code checks for missing values in the TEXT column of the news dataframe. If there were missing values, they would
be filled with the string "missing". The input variable is assigned to X and the target variable is assigned to y.

<h3>Preprocessing</h3>
This is a multi-class classification problem, with three categories to predict: whether a post is "graphics," "hockey,"
or "medical" related. The LabelEncoder from sklearn is used to transform the categorical target variable into numeric
labels. The WordNetLemmatizer from nltk is used to lemmatize the corpus of documents.

<h3>Text Preparation</h3>
For simplicity, no text cleaning or preprocessing is performed. The raw text is used as input to the model. The
TfidfVectorizer from sklearn is used to tokenize, remove stop words and transform the text data.

<h3>Dimensionality Reduction</h3>
The TruncatedSVD algorithm from sklearn is used to perform Singular Value Decomposition (SVD) with varying numbers of
components (100, 300, and 500). The resulting matrices are used as input to train a random forest classifier and a
stochastic gradient descent classifier.

<h3>Model Training and Evaluation</h3>
The RandomForestClassifier and SGDClassifier algorithms from sklearn are trained on the data, and their performance is
evaluated on a test set. The resulting accuracy scores are recorded and summarized in a performance dataframe.

<h3>Observations</h3>
Two observations are noted in the code:

The upper limit for the number of SVD components is the number of rows or columns in the matrix. Increasing the number
of components beyond this limit will not improve performance.
Increasing the number of SVD components beyond a certain point may result in overfitting, where the model becomes too
complex and starts to memorize noise in the data, leading to worse performance on new data.
Based on the results of the analysis, SVD components = 100 is the best choice for the random forest model and SVD
components = 300 is the best choice for the stochastic gradient descent model.
