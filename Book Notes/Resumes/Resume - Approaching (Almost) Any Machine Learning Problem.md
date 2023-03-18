#MachineLearning #DataScience
- Mostly we will use Ubuntu because it can connect to server and the powerful bash script. But is it necessary to do dual boot? Or we can just use WSL instead?
- What is the advantages of using Miniconda rather just using Python Virtual Environment?
- It seems Conda use `.yml` file as its environment file extension, can we use `pip` to install packages in that `.yml` file?
- The excistence of target variable is differentiate between supervised and unsupervised problem
- Supervised problem is easier because we just predict the target variable, meanwhile unsupervised problem need human reasoning to conclude the result report.
- In a dataset, columns represent different features meanwhile rows represent data point or samples
- Sometimes we can use regression in a classification setting (depending on the evaluation metric)
- **Decomposition Technique** is a set of methods used to break down a complex problem into a simpler sub-problems that can be solved independently. It is often used when dealing with large datasets or complex models. In ML, this technique is used for dimensionality reduction, feature extraction, and clustering. Several types of decomposition techniques:
	- PCA: reduce dimensionality of a dataset by identifying the most important features.
	- SVD
	- NMF
	- etc.
- Cross validation helps us ensure that our models fit the data accurately and also ensures that we do not overfit.
- I don't know if it is an important step or not, but maybe you need to shuffle your dataset before spiltting it to train and test set
	```python
	df = df.sample(frac=1).reset_index(drop=True)
	```
- Overfit: the model learning the training data well but won't generalize on unseen samples. Or in a neural network training sense, overfitting is when the test loss is increases as we keep improving training losss. **We must stop training where the validation loss reaches its minimum value**.
	![500](https://vitalflux.com/wp-content/uploads/2022/05/model-complexity-vs-model-overfitting-vs-model-accuracy-640x430.png)
- Splitting datasets into train and test sets is also a kind of cross validation commonly known as a hold-out set. We use this kind of cross-validation when we have a large amount of data and model inference is time-consuming
- The aim of cross-validation is to generalizable the ML Model by dividing training data into a few parts, we train the model on some of these parts and test on the remaining parts. Cross-validation is the first and most essential step when it comes to building ML Models.
- The most popular cross-validation techniques:
	- K-Fold Cross-Validation
	- Stratified K-Fold Cross-Validation
	- Hold-Out Based Validation
	- Leave-One-Out Cross-Validation
	- Group K-Fold Cross-Validation
- Many people split datasets into a third set: training, validation, and test sets.
- Choosing the right cross-validation technique depends a lot on the dataset you are dealing with. You might need to adopt new forms of cross-validation depending on your problem and data.
- K-Folds Validation technique can be used with almost all kinds of datasets.
- Use Stratified K-Fold Validation when your target data is skewed or imbalance. The rule is simple, if it's a standard classification problem, choose Stratified K-Fold Validation.
- Hold-Out Based Validation technique is suitable for big datasets (ex: 1 million samples) and also this technique used very frequently with time-series data. To note, when predicting new dataset in time-series data, you should include the hold-out data in your model.
- When we deal with a small datasets and creating big validation sets means losing a lot  of data for the model to learn. In those cases, we can choose for a type of K-Fold Validation where K = N, where N is the number of samples in the dataset.
- When dealing with a regression problem, we can use all the cross validation techniques except for Stratified K-Fold. We can use Stratified K-Fold directly, but there are ways to change the problem. Mostly, simple K-Fold Validation works for any regressio problem, however if the distribution of targets is not consistent, you can use stratified K-Fold.
	- First, we have to divide the target into bins, and then we can use Stratified K-Fold in the same way as for classification problems
	- If you have a lot of samples (>10k, >100k), then you don't need to care about the number of bins. Just divide the data into 10 or 20 bins.  But if the samples is small, you csn use *Sturge's Rule* to calculate the appropriate number of bins.
- Another technique for cross-validation, GroupKFold. The use case is when your dealing with datasets consist of multiple images for the same patient in the training set for classification. To build a good cross-validation system here, we use Stratified K-Fold, but we must make sure that patients in training set do not appear in validation set (the data for the same patient is overlap in training and validation set). With GroupKFold, the patients can be considered as groups. As a task, combine this GroupKFold with Stratified K-Fold! 







