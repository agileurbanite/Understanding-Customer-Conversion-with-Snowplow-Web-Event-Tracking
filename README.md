# Understanding Customer Conversion with Snowplow Web Event Tracking
I apply machine learning (ML) techniques to Snowplow web event data to understand how variation in marketing site experiences might correlate to customer conversion.

### Data Transformation 
The distillation of the raw data into a transformed feature set with labels is handled by the iPython notebook 'Notebook 1 - Data Munging.' In transforming the data, we will need to create features by creating combinations of event types and
distinct URLs, and counting the number of occurrences while grouping on accounts. For instance, if ‘.../pay-
ment plan.com’ is a frequent page url, then the number of page views on payment plan.com would be one
feature, the number of page pings would be another, as would the number of web forms submitted, and so
forth. Given that there are six distinct event types and dozens of URLs within the marketing site, then
the feature space quickly expands to encompass hundreds of features. This feature space will only widen as we add
additional variables to the mix including geo region, number of visitors per account, and so forth.
<div align="center">
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/Data_Transformation.png" width="500" height="400" />


</div>
### Exploratory Analysis
The exploratory analysis of the initial feature set is handled in the iPython notebook 'Notebook 2 - Exploratory Analysis.'
<div align="center">
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/exploratory_analysis-labels.png" width="500" height="400" />
</div>

<div align="center">
<p align="center"><b>Summary Statistics: Means and Standard Deviations of Spare Feature Space</b></p>
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/exploratory_analysis-feature_means.png" align="middle" width="420" height="320" />
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/exploratory_analysis-feature_sds.png" align="middle" width="420" height="320" />
</div>

</div>
### Establishing a Baseline 
<p> How do we know if our ultimate model is any good? To establish a baseline, I implement a Support Vector Machine (SVM) model and a linear SVM model, both with their default settings.
<div align="center">
<p align="center"><b>Results: SVM with RBF Kernel and Linear SVM (Default Hyper-Parameter Settings)</b></p>
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/non-optimized_rbf_kernel.png" width="420" height="320" />
<img src="https://github.com/b-knight/Understanding-Customer-Conversion-with-Snowplow-Web-Event-Tracking/blob/master/Images/non-optimized_linear_svm.png" width="420" height="320" />
</div>
