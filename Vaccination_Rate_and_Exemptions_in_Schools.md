## Vaccination Rate and Exemptions in Schools

**Project description:** This data set contains information from schools about vaccination rates and exemptions (0-100%) along with enrollment and school type. The objective of this research is to investigate the relationship between school type (public or private), enrollment, and the number of medical exemptions granted to students. By developing a linear regression model, the aim is to predict the number of medical exemptions in a school given its type and enrollment size. A hypothesis test is also ran to detemerine the odds of students claiming a religious exemption to vaccination increase or decrease with public school status.

## Scurbbing | Feature Engineering:
### Create the following new variables:
* public_dummy = Indicator variable that is 1 for public school 0 for private.
* hi_enrollment = Indicator variable that is 1 when enrollment > mean enrollment.
* relig_exempt = Indicator that is 1 when religious > 0, and 0 otherwise.

#### Viz for the raw data: 
<img src="images/vacc_Viz_for_the_raw_data.png?raw=true"/>

#### Viz for the new variables that were created: 
<img src="images/vacc_Viz_for_the_feat_data.png?raw=true"/>

## Quick EDA:

 
#### Tallying of the duplicated school names:
* Group by school name
<img src="images/vacc_duplicated_school_names.png?raw=true"/>
* 31 Total duplicate chr (school names) values found: 
 
#### Correlation with corrr / lava:
 <img src="images/vacc_corr_basic.png?raw=true"/>
* Correlation should be minimal between independent variable's to avoid multicollinearity:
 
## Modeling: 
### 1. Suggest hypotheses about the causes of observed phenomena

* Ho: There is no linear relationship and difference between the variables.
* Ha: There is a linear relationship and difference between the variables.

#### Using Predictive Modeling Outputs to Enhance Decision-Making Solutions:
* Linear Regression: Evaluating the Relationship Between Dependent and Independent Variables.
* GOAL: 
  * Minimize the error between the predicted and true values of the target variable.


### 2. Assess assumptions on which statistical inference will be based
#### Interpretation: 

<img src="images/vacc_nwork_graph.png?raw=true"/>

* In the network graph located on the top:
 * The medical node not being connected to other nodes suggest that medical is weakly correlated with all variables. 
* In the network graph located on the right:
  * suggest that there is a high positive correlation between public_dummy - enrollment - hi-enrollment.
* Lastly, the network graph on the left represents:
  * The strongest correlation's being grouped in the middle of this network 
  * The weakest correlation in this bucket are religious and conditional. 
  * The insight here is that both Religious and conditional are still correlated with the variable's in the middle. 


### 3. Support the selection of appropriate statistical tools and techniques
* Research Question: Can we develop a linear regression model to predict the number of medical exemptions in public and private schools based on school type and enrollment?
<img src="images/vacc_lin_basic.png?raw=true"/>
* There is at least one negative relationship for Medical exemptions and Enrollment size that is toward the higher enrollment size variable for schools. 
  * There seems to be multiple layers within the data. 
   * If this is graphed in 3-d space will show possible floors.  
<img src="images/vacc_lin_qq.png?raw=true"/>
* Residuals vs Fitted
  * Linearity is violated.

* Scale Residuals vs Fitted
  * Curvature showing the residuals do not have a constant variance
   * This will cause challenges for inference. 


* Normal Q-Q
  * Display's non-normal data due to the curve.
   * Skew-right / Positively Skewed
    * The top end deviates from the linear line and represents the sample data having more extreme values than expected. 
         

* Residuals vs Leverage:
  * There is one significant point that fall's along cook's distance, and investigating the cause of this outlier will be important for determining whether to remove the observation or this is not the best model for the data.
  * Further investigation of the outliers will be good to look at. 

### 4. Provide a basis for further data collection through surveys or experiments

This model could potentially help policymakers and educators better understand the factors that contribute to medical exemptions and identify trends or discrepancies in the distribution of exemptions across different school types and sizes. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
