<link rel="stylesheet" href="http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css">
<style type="text/css"> body {padding: 10px 30px 10px 30px;} table,th, td {text-align: center;} </style>


Derived Attributes and Dimensionality Reduction 
========================================================

**T. Evgeniou, INSEAD**


What is this for?
---------------------------------------------------------

One of the key steps in Data Analytics is to generate meaningful attributes starting from possibly a large number of **raw attributes**. Consider for example the case of customer data, where for each customer we have a very large number of raw attributes (which could be, for example, *independent variables* in the case of a regression used to predict acquisition, purchases, or churn) ranging from demographic information, to what products they bought in the past, who their friends on various social media sites are, what websites they visit more often, how they rated a number of movies or products in general, whether they use their mobile phone mostly the weekends or in the mornings, how they responded to various surveys, etc. One can easily end up with tens if not thousands of such raw attributes, for thousands or millions of customers. In such cases it is virtually impossible to use some of the "advanced" methodologies developed for data analytics, or even simple ones such as linear regression. This is not only because of compuational reasons but, more important, because of statistical/mathematical reasons as, doing so entails a high risk that the estimated models (e.g. consumer behavior models) may be of very low quality in a statistical hence also practical sense. Moreover, the insights developed may not be practical or actionable as they may correspond to complicated statements involving a very large number of raw customer attributes.  

In such situations, which arise almost always in practice, one needs to spend a lot of creative effort and time - based on a deep contextual knowledge - to generate new  attributes (e.g. "this customer is price sensitive", or "this customer likes comfort", or "this customer is status conscious", etc) from the original raw ones, which we call here **derived attributes**. These attributes can be generated manually, or using what we call **data or dimensionality reduction statistical techniques**. 

We will consider a specific family of such statistical techniques which we will broadly call **Factor Analysis techniques**. Such techniques are often used at the early stages of a data analytics project, for example before running a regression with many independent variables (the raw attributes in that case), in order to summarize information (the variation) in correlated raw attributes using a smaller number of manageable **factors** - which are typically uncorrelated or independent. In the process one decreases the number of raw attributes while **keeping most of the information in the data, in a statistical sense**. 

Such derived variables are usually useful also for managerial interpretation and action. For example, when analyzing survey data from students regarding the quality of a school, the quality of education may be a useful variable, but in a student survey one could instead ask several questions related to this: (1) Breadth of courses; (2) Depth of courses; (3) Quality of Instruction; (4) Practicality of coursework, etc. A "good linear combination" of these raw attributes may be more managerially useful in understanding student perceptions of the quality of education than each of these variables alone. If indeed these variables are highly related to the underlying construct of "quality of education", Factor analysis will be able to summarize the information into such a single factor, while capturing most of the information in those "raw" attributes.

<blockquote> <p>
Before proceeding on understanding the statistical techniques considered here, it is important to note that this is not the only approach to generating meaningful derived attributes from large numbers of raw ones: there is always "the manual approach"" based on contextual knowledge and intuition, which can probably take a data analytics project already very far. However, in terms of mathematical techniques used in data analytics, factor analysis is one of the key ones when it comes to generating new meaningful derived attributes from the original raw ones.
</p> </blockquote>


Factor Analysis for Dimensionality Reduction using an Example
--------------------------------------------

There are many dimensionality reduction statistical methods. In this note we will go through the steps of one specific approach. We will do so using a simple example. For this example the "meaningful derived variables" will seem to be straightforward to design, which can help us with the intuition of what the method does. Having said this, before reading the analysis below, do try to think what "derived attributes" one could get from the raw ones below. You will see that even in this case it is not as obvious and you will most likely disagree with your colleagues about what the derived attributes should be: so we will let the numbers and statistics help us be more *objective and statistically correct*.

### The "Business Decision"

We consider the core decision of an MBA admissions committee: *which applicants should we accept in the MBA program?* The school is interested in predicting the MBA participant's success in the future before offering admission.

### The Data

To make this decision, the committee uses a number of data about the applicants. Let us consider for example the following attributes in evaluating an MBA application (of course in practice many more can be considered):

1. GPA 
2. GMAT score 
3. Scholarships, fellowships won 
4. Evidence of Communications skills (debating competition, personal interview score) 
5. Prior Job Experience 
6. Organizational Experience 
7. Other extra curricular achievements 

Let us assume that this data is converted into a numerical scale from 1-7. For example: a numerical rating may be given to the fellowships based on the prestige and the number of fellowships won. Job experience may be rated on the number of years on the job, with a numerical weighting for the level of the job in the managerial ladder.






























