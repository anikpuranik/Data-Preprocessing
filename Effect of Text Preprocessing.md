<h2> Performance Comparison of Text Preprocessing Steps </h2>

Text Preprocessing is a very crucial task of Natural Language Processing. Multiple ways and multiple steps are to be performed before data is ready to be trained.
This post compares the performance of the model with respect to steps involved for the text classification.
 
 Here, we are taking very famous IMDB dataset which is binary dataset for text classification. Dataset contains 50000 reviews in a balanced distribution 
i.e. 25000 positive and 25000 negative reviews. Dataset can be obtained from <a href="https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews">
here.</a><br> 

To check for the model performance we are using Naïve Bayes, SVM and Logistic Regression and the dataset is split in 80:20 as train:test.<br>

<b>Steps Taken are:</b>
<oi>
	<li>We first took the dataset and directly put it into the model. This constructs our base model.</li>
	<li>Converting reviews to lower case.</li>
	<li>Applying Stemming to text.</li>
	<li>Removal of stop words.</li>
	<li>Then Combination of the above two</li>
	<li>Complete Processing Steps.</li>
</oi>
<br>
![image](https://user-images.githubusercontent.com/22523309/168589759-b2476ff6-d8de-40ad-a828-d59d3c6ef8b9.png)

For Word Embedding, both the CountVectoizer and TfiDF to observe the results.
![image](https://user-images.githubusercontent.com/22523309/168590580-9179f77a-fb77-40ef-9655-0804bc63232c.png)

<b> Observations:</b>
<ul>
	<li>From the above table we can draw that SVM with TFIDF perform a good base model with approximate average accuracy of 90% followed by 
		Logistic regression than Naïve Bayes.</li>
	<li>The performance difference in Naïve Bayes with CV and Tfidf very much higher as compared to other two.</li>
	<li>Logistic regression takes longer time to train the model and Naïve Bayes is much faster.</li>
</ul>

Keeping all the parameters same, we also perform same for ngram=3 (i.e. unigram, bigram and trigram) to observe the result.

![image](https://user-images.githubusercontent.com/22523309/168591453-88fb3c5a-8e48-4e81-bb48-73eae77ee673.png)

<b>Observations</b>
<ul>
	<li>There is high performance improvement in the Naive Bayes with TFIDF.</li>
	<li>Logistic Regression performs more or less the same but train time increases by great margin.</li>
	<li>SVM outperform every other case here even without no pre-processing.</li>
</ul>

#### Conclusion:
With each preprocessing step, there is little change in the model accuracy. Performance may vary upto 1% which may or may not be important.

<b>
Note: Although this seems very simple to create a base model, the data in real time scenario is very-very messy. The dataset is most of the time not even properly labeled and often time labels are missing or not even present. If we try web scrapping the IMDB site itself have reviews in the star-based rating system. So, the original data obtaining from scrapping will be more difficult to deal with.

The IMDB dataset obtain here is very polished dataset with very little tweaking to do which makes it much easier to perform this analysis. 
</b>
