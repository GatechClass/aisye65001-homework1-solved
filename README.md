# aisye65001-homework1-solved
**TO GET THIS SOLUTION VISIT:** [AISyE65001 Homework1-Solved](https://mantutor.com/product/aisye65001-homework1-solved/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;56230&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;AISyE65001 Homework1-Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<strong>&nbsp;</strong>Question 2.1

<strong>&nbsp;</strong>Describe a situation or problem from your job, everyday life, current events, etc., for which a classification model would be appropriate. List some (up to 5) predictors that you might use.

<strong>&nbsp;</strong>Question 2.2

The files credit_card_data.txt (without headers) and credit_card_data-headers.txt

(with headers) contain a dataset with 654 data points, 6 continuous and 4 binary predictor variables.&nbsp; It has anonymized credit card applications with a binary response variable (last column) indicating if the application was positive or negative. The dataset is the “Credit Approval Data Set” from the UCI Machine Learning Repository (<u><a href="https://archive.ics.uci.edu/ml/datasets/Credit+Approval">https://archive.ics.uci.edu/ml/datasets/Credit+Approval</a></u><a href="https://archive.ics.uci.edu/ml/datasets/Credit+Approval">)</a> without the categorical variables and without data points that have missing values.

<ol>
<li>Using the support vector machine function ksvm contained in the R package kernlab, find a good classifier for this data. Show the equation of your classifier, and how well it classifies the data points in the full data set. (Don’t worry about test/validation data yet; we’ll cover that topic soon.)</li>
</ol>
&nbsp;

Notes on ksvm

<ul>
<li>You can use scaled=TRUE to get ksvm to scale the data as part of calculating a classifier.</li>
<li>The term λ we used in the SVM lesson to trade off the two components of correctness and margin is called C in ksvm. One of the challenges of this homework is to find a</li>
</ul>
value of C that works well; for many values of C, almost all predictions will be “yes” or almost all predictions will be “no”.

<ul>
<li>ksvm does not directly return the coefficients a<sub>0</sub> and a<sub>1</sub>…a<sub>m</sub>. Instead, you need to do the last step of the calculation yourself.&nbsp; Here’s an example of the steps to take (assuming your data is stored in a matrix called data):<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a></li>
</ul>
# call ksvm.&nbsp; Vanilladot is a simple linear kernel.

model &lt;- ksvm(data[,1:10],data[,11],type=”Csvc”,kernel=”vanilladot”,C=100,scaled=TRUE)

# calculate a<sub>1</sub>…a<sub>m</sub>

a &lt;- colSums(model@xmatrix[[1]] * model@coef[[1]]) a

# calculate a<sub>0</sub> a0 &lt;- –model@b a0

# see what the model predicts pred &lt;- predict(model,data[,1:10]) pred

# see what fraction of the model’s predictions match the actual classification

sum(pred == data[,11]) / nrow(data)

&nbsp;

<u>Hint</u>: You might want to view the predictions your model makes; if C is too large or too small, they’ll almost all be the same (all zero or all one) and the predictive value of the model will be poor.&nbsp; Even finding the right order of magnitude for C might take a little trial-and-error.

&nbsp;

<u>Note</u>: If you get the error “Error in vanilladot(length = 4, lambda = 0.5) : unused arguments (length = 4, lambda = 0.5)”, it means you need to convert data into matrix format:

&nbsp;

model &lt;-

ksvm(as.matrix(data[,1:10]),as.factor(data[,11]),type=”Csvc”,kernel=”vanilladot”,C=100,scaled=TRUE)

<ol start="3">
<li>You are welcome, but not required, to try other (nonlinear) kernels as well; we’re not covering them in this course, but they can sometimes be useful and might provide better predictions than vanilladot.</li>
<li>Using the k-nearest-neighbors classification function kknn contained in the R kknn package, suggest a good value of k, and show how well it classifies that data points in the full data set. Don’t forget to scale the data (scale=TRUE in kknn).</li>
</ol>
Notes on kknn

<ul>
<li>You need to be a little careful. If you give it the whole data set to find the closest points to i, it’ll use i itself (which is in the data set) as one of the nearest neighbors.&nbsp; A helpful feature of R is the index –i, which means “all indices except i”.&nbsp; For example, data[i,] is all the data except for the ith data point.&nbsp; For our data file where the first 10 columns are predictors and the 11<sup>th</sup> column is the response, data[-i,11] is the response for all but the ith data point, and data[-i,1:10] are the predictors for all but the ith data point.</li>
<li><strong>Note</strong> that kknn will read the responses as <u>continuous</u>, and return the fraction of the k closest responses that are 1 (rather than the most common response, 1 or 0).</li>
</ul>
