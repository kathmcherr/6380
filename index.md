---
title: "PSYC*6380 Group Presentation"
author: "Lindsay Bryant, Katie Cherry, Kaytlin Constantin, & Sandy Erb"
highlighter: highlight.js
incremental: yes
job: null
knit: slidify::knit2slides
mode: selfcontained
hitheme: school_book
subtitle: Multiple Regression & Structural Equation Modeling
framework: io2012
widgets: mathjax
github:
  user: kathmcherr
  repo: TESTING
---

<style>
em {
  font-style: italic
}
</style>

<style>
strong {
  font-weight: bold;
}
</style>

## Today's Objectives

>- Analytic problem
>- Concept behind Multiple Regression (MR) & Structural Equation Modeling (SEM)
>- Assumptions of MR & SEM
>- MR & SEM in the R environment
>- Advantages & disadvantages
>- Reflections

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/people.png)

--- .class #id 

## Analytic Problem

*You're interested in the relations between a set of variables in some psychological system. For practical and/or ethical reasons, you're unable to experimentally manipulate these variables. You need to figure out a way to still describe the relations between these variables, and you recognize you will be limited from drawing causal inferrences from whatever technique you decide to use.*

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/man-thinking.png)
![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/02.png)

--- .class #id 

## Conceptual Model: Multiple Regression

>- $Y = a + b_1X_1 + b_2X_2 + b_3X_3 + {\epsilon}$

>- MR examines **variations in Y**, attempting to **explain this variance** through **examining its relation** with a set of predetermined **predictor X variables**.
  + i.e., *How much variance in Y is predicted by a set of X predictors all together?*
>- **$R^2$**: The proportion of variance in the dependent variable accounted for by all the predictors together
>- **Caution**: whenever you add a predictor, $R^2$ automatically increases
  + Solution: Adjusted $R^2$ corrects for the number of predictor variables in the equation

--- .class #id

## MR: Selection Types

>- 1. **Hierarchical**
  + Predictors entered cumulatively
  + Appropriate when: order driven by theory
>- 2. **Forced entry**
  + Predictors entered simultaneously
  + Appropriate when: a) small # of predictors; b) "best" predictor unknown
  + Each predictor assessed for unique variance
>- 3. **Step-wise**
  + Predictors added/removed to satisfy alpha level
  + Relies on “significance testing” (**dun dun dun**)
  + Used when: no hypotheses about predictors (i.e., exploratory stages)

--- .class #id

## Conceptual Model: Structural Equation Modeling

>- Used to investigate theoretical constructs (i.e., latent variables) that are not observable and thus cannot be measured directly
>- Combination of factor analysis and regression
>- Often presented visually in a path diagram 

>- ![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/pathmodel.png)
  + Hox & Bechger, 1998

--- .class #id

## Conceptual Model: SEM (con't)

>- Appropriate to use when:
  + A set of theoretical constructs (i.e., latent variables) are hypothesized to (1) correlate with each other; and (2) cause covariation among observed variables assumed to compose and represent proposed theoretical constructs  

>- ![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/pathmodel.png)
  + Hox & Bechger, 1998

--- .class #id

## Assumptions of MR

>- Continuous dependent variable
>- Two or more independent variables (continuous [interval/ratio] or categorical [ordinal/nominal])
>- Independence of observations (i.e., independence of residuals/errors): Durbin-Watson statistic
>- Linear relationship between:
  + Dependent variable and each of the independent variables
  + Dependent and independent variables collectively
  
![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/checklist.png)

--- .class #id

## Assumptions of MR (con't)

>- Homoscedasticity of residuals (equal error variances)
>- No multicollinearity
>- No extreme outliers, high leverage points, or highly influential points
>- Residuals (errors) should be normally distributed

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/checklist.png)

--- .class #id

## Assumptions of SEM

>- Temporal precedence
>- Association or observed covariation between X and Y
>- Isolation is present - no other reasonable explanation for this relationship - confounding variables controlled and relationship holds
>- Data distribution meets assumptions of method used to estimate the relationship
>- Correct specification of the direction of the causal relationship

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/man-asking-to-other-about-an-educational-book.png)

--- .class #id

## Specifications of Exogeneity, Endogeneity, and Disturbances

>- **Exogeneity**: unmeasured, unknown, and free to vary and covary
>- **Endogeneity**: explicitly measured, not free to vary or covary
>- **Disturbances**: set of unspecified causes of effect variable - similar to error or residual
>- Assumption of independence of endogenous variables
  + no common or ommitted causes: this assumption unrealistic and restrictive for behavioural sciences - thus all ommitted causes are unrelated to each other

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/man-asking-to-other-about-an-educational-book.png)

--- .class #id

## Recursive and Non-Recursive Models

>- Both assume that disturbances of endogenous variables unrelated to exogenous variables
>- **Recursive**
  + no feedback loops
  + all causal effects assumed to be unidirectional
  + Therefore, no endogenous variable a cause and effect of each other.
>- **Non-Recursive**
  + Have feedback loops or optional correlated errors
  + Two special circumstances:
   + 1. **Assumption of "equilibrium"** needed for reciprocal effects in a feedback loop where cross-sectional data is involved
   + 2. **Assumption of "stationarity"** means that over time the basic causal relationship stays constant

--- .class #id

## Assumptions of Measurement Models

>- 1. **Reflective Models**: most common type analyzed in SEM
  + SEM analyzes continuous latent variables
  + Factors and measurement errors uncorrelated
  + Factors assumed to be continuous variables that are unidimensional
  + Factors are normally distributed
  + Independent error terms (omitted causes of different indicators) are uncorrelated - effect indicators are independent
  + Assumption is relaxed with the ability to specify correlated measurement errors
>- 2. **Formative Models:** used where composites are involved
  + Direct effects go from indicator to composite; either a latent composite with an associated disturbance or to a composite with a total score that is not latent
  + In order to identify a latent composite, it must have direct effects on at least two endogenous factors with effect indicators

--- .class #id

## Assumptions of Measurement Models (con't)

>- 3. **MIMIC Models**: specify a factor with both cause and effect indicators
  + Requires a strong theoretical rationale and theory regarding the direction of effect between indicators and latent variables

--- .class #id

## Data-Related Assumptions
# Cardinal assumption: the model is **correctly specified**

>- Observations independent; variables unstandardized
>- No missing values
>- Specific distribution assumptions target endogenous, *not* exogenous variables
>- Normal univariate distributions of endogenous variables - implies they are continuous
  + Robust ML estimation used with non-normal distribution
  + Robust forms (e.g., weighted least squares regression) used with noncontinuous endogenous variables

--- .class #id

## Data-Related Assumptions (con't)

>- Linear bivariate scatterplots
>- Homoscedastic distribution of residual
>- No measurement error in exogenous variables (unrealistic)
>- Exogeneity Assumptions:
  + Distribution of Endogenous and Exogenous continuous variables is  multivariate normal
  + All biviariate relations  are linear
  + Homoscedastic distributions of regression residuals

--- .class #id

## PHEW!

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/exhausted-man.png)

--- .class #id

## MR in the R environment: Example 1

- Example: examining the relation between rime awareness, phonological awareness, and verbal short-term memory as predictors of the WISC-V's Verbal Comprehension Index. 
- Using a forced entry MR method (no predictions)
- Need to combine these into a new variable






    ```{r verbatimchunk}
    my.regression1 <- lm(VCI~RimeAwareness+PhonologicalAwareness+VerbalSTM, data=mydata)
    ```

--- .class #id

## MR Example 1

This output shows us how we combined rime awareness, phonological awareness and verbal short term memory and a constant to create $\hat{Y}$ (reported as the intercept in the output). Basically we are looking at how well, overall, can these three variables predict scores on the verbal comprehension index. 


    ```{r verbatim = TRUE}
    print(my.regression1)
    ```

```
## 
## Call:
## lm(formula = VCI ~ RimeAwareness + PhonologicalAwareness + VerbalSTM, 
##     data = mydata)
## 
## Coefficients:
##           (Intercept)          RimeAwareness  PhonologicalAwareness  
##              -2.65549                1.80655                0.01713  
##             VerbalSTM  
##              -0.30720
```

---.smallcode

## MR Example 1 (con't)

The $R^2$ value (ranges 0 to 1) indicates how well we predicted VCI based on our predictors. B-weights are presented under the Estimate columns. Here, $R^2$ = .16, indicating  16% of the variability in VCI scores can be explained by rime awareness, phonological awareness and verbal short term memory.


    ```{r verbatim = TRUE}
    summary(my.regression1)
    ```

```
## 
## Call:
## lm(formula = VCI ~ RimeAwareness + PhonologicalAwareness + VerbalSTM, 
##     data = mydata)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -5.1788 -1.5385  0.1764  1.7060  4.7523 
## 
## Coefficients:
##                       Estimate Std. Error t value Pr(>|t|)  
## (Intercept)           -2.65549    2.81464  -0.943   0.3486  
## RimeAwareness          1.80655    0.88496   2.041   0.0449 *
## PhonologicalAwareness  0.01713    0.49059   0.035   0.9722  
## VerbalSTM             -0.30720    0.39219  -0.783   0.4361  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 2.461 on 71 degrees of freedom
## Multiple R-squared:  0.1553,	Adjusted R-squared:  0.1197 
## F-statistic: 4.353 on 3 and 71 DF,  p-value: 0.00715
```

--- .class #id

## MR Example 1 (con't)

Next, we examined the confidence interval for $R^2$ (using the MBESS package). 

From this output, we see that our $R^2$ for the population ranges from .02 and .29. 


    ```{r verbatim = TRUE}
    ci.R2(R2=.16, df.1 = 3, df.2 = 72, Random.Predictors = FALSE)
    ```

```
## $Lower.Conf.Limit.R2
## [1] 0.01716246
## 
## $Prob.Less.Lower
## [1] 0.025
## 
## $Upper.Conf.Limit.R2
## [1] 0.2865617
## 
## $Prob.Greater.Upper
## [1] 0.025
```

--- .class #id

## MR Example 1 (con't)

Now we will obtain the $\beta$-weights/standardized regression weights and semi-partial corelations, which will give us a better indicator of the "best predictor".


    ```{r verbatim = TRUE}
    apa.reg.table(my.regression1, filename = "myRegressionTable1.doc")
    ```

```
## 
## 
## Regression results using VCI as the criterion
##  
## 
##              variables      b    SE  beta sr2     r             fit  
##                Model 1                                               
##            (Intercept)  -2.66  2.81                                  
##          RimeAwareness  1.81*  0.88  0.50 .05 .38**                  
##  PhonologicalAwareness   0.02  0.49  0.01 .00 .32**                  
##              VerbalSTM  -0.31  0.39 -0.16 .01  .25*                  
##                                                           R2 = .155  
##                                                     F(3, 71) = 4.35  
##                                                                      
## 
## Note. * indicates p < .05; ** indicates p < .01.
## A significant b-weight indicates the beta-weight and semi-partial correlation are also significant.
## b represents unstandardized regression weights; SE represents the standard error of the 
## unstandardized regression weights; beta indicates the beta-weights or standardized regression weights; 
## sr2 represents the semi-partial correlation squared;r represents the zero-order correlation.
## 
```

--- .class #id

## MR Example 1 (con't)

$sr^2$ tells us how much of $R^2$ = .16 is uniquely accounted for by each predictor. From our table (ignore the *p* values!), we can see rime awareness is our best predictor of scores on the VCI. 

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/RegressionTable.png)

--- .class #id

## MR Example 2

We decided to repeat these steps to examine the scores from the WISC, including the verbal comprehension index (VCI), the visual-spatial index (VSI), the working memory index (WMI), and the processing speed index (PSI) as predictors of self-regulation. 

Again, we have our intercept created from the four predictor variables.


    ```{r verbatim = TRUE}
    my.regression2 <- lm(SelfRegulation~VCI+VSI+WMI+PSI, data=mydata)
    print(my.regression2)
    ```

```
## 
## Call:
## lm(formula = SelfRegulation ~ VCI + VSI + WMI + PSI, data = mydata)
## 
## Coefficients:
## (Intercept)          VCI          VSI          WMI          PSI  
##    -0.26081      0.33602      0.07949      0.01574      0.45509
```

--- .class #id

## MR Example 2 (con't)

In this output, the $R^2$ value is much higher at .59, which indicates  59% of the variability in self-regulation scores can be explained by VCI, VSI, WMI, and PSI.


    ```{r verbatim = TRUE}
    summary(my.regression2)
    ```

```
## 
## Call:
## lm(formula = SelfRegulation ~ VCI + VSI + WMI + PSI, data = mydata)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -6.0681 -1.2823  0.2691  1.4068  4.2844 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) -0.26081    0.61147  -0.427 0.671026    
## VCI          0.33602    0.15010   2.239 0.028363 *  
## VSI          0.07949    0.09249   0.859 0.393021    
## WMI          0.01574    0.10659   0.148 0.883025    
## PSI          0.45509    0.12455   3.654 0.000495 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 2.126 on 70 degrees of freedom
## Multiple R-squared:  0.594,	Adjusted R-squared:  0.5708 
## F-statistic: 25.61 on 4 and 70 DF,  p-value: 4.317e-13
```

--- .class #id

## MR Example 2 (con't)

Next, we examined the confidence interval for $R^2$.

From this output, we see that our $R^2$ for the population ranges from .42 and .67. 


    ```{r verbatim = TRUE}
    ci.R2(R2=.59, df.1 = 3, df.2 = 72, Random.Predictors = FALSE)
    ```

```
## $Lower.Conf.Limit.R2
## [1] 0.4232401
## 
## $Prob.Less.Lower
## [1] 0.025
## 
## $Upper.Conf.Limit.R2
## [1] 0.6777139
## 
## $Prob.Greater.Upper
## [1] 0.025
```

--- .class #id

## MR Example 2 (con't)

Again, we will obtain the $\beta$-weights/standardized regression weights and semi-partial corelations, which will give us a better indicator of the "best predictor".


    ```{r verbatim = TRUE}
    apa.reg.table(my.regression2, filename = "myRegressionTable2.doc")
    ```

```
## 
## 
## Regression results using SelfRegulation as the criterion
##  
## 
##    variables       b    SE beta sr2     r              fit  
##      Model 1                                                
##  (Intercept)   -0.26  0.61                                  
##          VCI   0.34*  0.15 0.27 .03 .67**                   
##          VSI    0.08  0.09 0.10 .00 .61**                   
##          WMI    0.02  0.11 0.02 .00 .53**                   
##          PSI  0.46**  0.12 0.47 .08 .74**                   
##                                                  R2 = .594  
##                                           F(4, 70) = 25.61  
##                                                             
## 
## Note. * indicates p < .05; ** indicates p < .01.
## A significant b-weight indicates the beta-weight and semi-partial correlation are also significant.
## b represents unstandardized regression weights; SE represents the standard error of the 
## unstandardized regression weights; beta indicates the beta-weights or standardized regression weights; 
## sr2 represents the semi-partial correlation squared;r represents the zero-order correlation.
## 
```

--- .class #id

## MR Example 2 (con't)

In this table (again, ignore the *p* values!) we can see that all four of our variables are correlated wtih self-regulation, ranging from medium to large effects. However, the table also shows that the PSI and VCI are the two predictors that are uniquely contributing, with .08 and .03, respectively. 

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/RegressionTable2.png)

--- .class #id

## SEM in the R environment

>- There are several packages available for SEM in R:
  + sem
  + lavaan
  + lava
  + systemfit
  + OpenMX
>- Today we will be looking at the package **lavaan**

--- .smallcode 

## SEM Example

- Latent variables represented by =~ (e.g., VCI + VSI + WMI + PSI loading onto IQ)
- Regressions represented by ~ (response variable ~ independent variable)
- Residual correlations represented by ~~
  + This is saying intelligence (g) is dependent on Reading Ability, and Student Engagement is dependent on those two. So, you get this dynamic model that is the nature of SEM.
- Residual correlations represent the notion that these variables are somehow correlated.




    ```{r verbatim = TRUE}
    model <- '
      # measurement model
        ReadingAbility =~ RimeAwareness + PhonologicalAwareness + VerbalSTM
        IQ =~ VCI + VSI + WMI + PSI
        StudentEngagement =~ Creativity + Leadership + LoveOfLearning + SelfRegulation
      # regressions
        IQ ~ ReadingAbility
        StudentEngagement ~ ReadingAbility + IQ
      # residual correlations
        VCI ~~ Creativity
        VSI ~~ PSI 
        VSI~~ Leadership
        WMI ~~ LoveOfLearning
        PSI ~~ SelfRegulation
        Leadership ~~ SelfRegulation
    '
    ```

--- .class #id 

## SEM Example (con't)
- Want models to converge; otherwise data does not fit the model
- "leftover" DF; completely saturated model, DF = 0
- Low *p* values are **bad**. $H_0$ = *data fits the model*


    ```{r verbatim = TRUE, comment = NA, message=FALSE, cache.comments= FALSE, warning = FALSE, error = FALSE}
    #fit your SEM
    fit <- sem(model, data = my.data)
    #summarize results
    summary(fit, standardized = TRUE, rsq = T)
    ```

```
lavaan (0.5-21) converged normally after  68 iterations

  Number of observations                            75

  Estimator                                         ML
  Minimum Function Test Statistic               38.125
  Degrees of freedom                                35
  P-value (Chi-square)                           0.329

Parameter Estimates:

  Information                                 Expected
  Standard Errors                             Standard

Latent Variables:
                       Estimate  Std.Err  z-value  P(>|z|)   Std.lv
  ReadingAbility =~                                                
    RimeAwareness         1.000                               0.670
    PhonlgclAwrnss        2.180    0.139   15.742    0.000    1.460
    VerbalSTM             1.819    0.152   11.967    0.000    1.218
  IQ =~                                                            
    VCI                   1.000                               2.223
    VSI                   1.257    0.182    6.889    0.000    2.794
    WMI                   1.058    0.151    6.987    0.000    2.351
    PSI                   1.265    0.145    8.722    0.000    2.812
  StudentEngagement =~                                             
    Creativity            1.000                               2.103
    Leadership            1.186    0.169    7.024    0.000    2.493
    LoveOfLearning        1.280    0.160    8.002    0.000    2.691
    SelfRegulation        1.266    0.158    8.007    0.000    2.662
  Std.all
         
    0.920
    0.973
    0.872
         
    0.850
    0.717
    0.722
    0.846
         
    0.808
    0.746
    0.824
    0.828

Regressions:
                      Estimate  Std.Err  z-value  P(>|z|)   Std.lv
  IQ ~                                                            
    ReadingAbility       1.483    0.399    3.715    0.000    0.447
  StudentEngagement ~                                             
    ReadingAbility       0.572    0.221    2.586    0.010    0.182
    IQ                   0.837    0.098    8.514    0.000    0.885
  Std.all
         
    0.447
         
    0.182
    0.885

Covariances:
                   Estimate  Std.Err  z-value  P(>|z|)   Std.lv  Std.all
 .VCI ~~                                                                
   .Creativity        0.624    0.358    1.741    0.082    0.624    0.296
 .VSI ~~                                                                
   .PSI               1.313    0.702    1.871    0.061    1.313    0.273
   .Leadership        2.153    0.734    2.934    0.003    2.153    0.356
 .WMI ~~                                                                
   .LoveOfLearning    0.795    0.608    1.308    0.191    0.795    0.191
 .PSI ~~                                                                
   .SelfRegulation    0.348    0.442    0.787    0.431    0.348    0.109
 .Leadership ~~                                                         
   .SelfRegulation    1.356    0.568    2.386    0.017    1.356    0.338

Variances:
                   Estimate  Std.Err  z-value  P(>|z|)   Std.lv  Std.all
   .RimeAwareness     0.082    0.019    4.184    0.000    0.082    0.154
   .PhonlgclAwrnss    0.120    0.070    1.718    0.086    0.120    0.053
   .VerbalSTM         0.467    0.090    5.177    0.000    0.467    0.239
   .VCI               1.891    0.444    4.256    0.000    1.891    0.277
   .VSI               7.373    1.374    5.366    0.000    7.373    0.486
   .WMI               5.067    0.952    5.324    0.000    5.067    0.478
   .PSI               3.148    0.739    4.261    0.000    3.148    0.285
   .Creativity        2.351    0.480    4.895    0.000    2.351    0.347
   .Leadership        4.954    0.914    5.419    0.000    4.954    0.443
   .LoveOfLearning    3.431    0.713    4.814    0.000    3.431    0.322
   .SelfRegulation    3.254    0.695    4.685    0.000    3.254    0.315
    ReadingAbility    0.448    0.087    5.173    0.000    1.000    1.000
   .IQ                3.956    0.921    4.295    0.000    0.800    0.800
   .StudentEnggmnt    0.172    0.215    0.803    0.422    0.039    0.039

R-Square:
                   Estimate
    RimeAwareness     0.846
    PhonlgclAwrnss    0.947
    VerbalSTM         0.761
    VCI               0.723
    VSI               0.514
    WMI               0.522
    PSI               0.715
    Creativity        0.653
    Leadership        0.557
    LoveOfLearning    0.678
    SelfRegulation    0.685
    IQ                0.200
    StudentEnggmnt    0.961
```

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/Summary1.png)

--- .class #id

## SEM Example (con't)

- Displays correlations, estimates, z-scores, *p*-values for correlations between variables
- The "rsq = T" command gives us an estimate of $R^2$ for each variable.
- Here, values are high; so, we have lots of prediction power


    ```{r verbatim = TRUE, comment = NA, message=FALSE, cache.comments= FALSE, warning = FALSE, eval=FALSE, error = FALSE}
    summary(fit, standardized = TRUE, rsq = T)
    ```

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/Summary2.png)

--- .class #id

## SEM Example (con't)

- Plots in lavan using **semPaths** command from **qgraph** package
- "std" command tells R to standardize the data
- *Drawback*: unable to plot in APA format


    ```{r verbatim = TRUE, comment = NA, message=FALSE, cache.comments= FALSE, warning = FALSE, eval=FALSE, error = FALSE}
    library(semPlot)
    
    semPaths(fit, "std", edge.label.cex = 0.5, curvePivot = TRUE, layout = "tree")
    ```

--- .class #id

## SEM Example (con't)

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/Plot.png)

--- .class #id

## SEM Example (con't)

- **modindices**: allows you to see if you missed a pathway in your dataset


    ```{r verbatim = TRUE, comment = NA, message=FALSE, cache.comments= FALSE, warning = FALSE, eval=FALSE, error = FALSE}
    modindices(fit)
    ```

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/mod.png)

- **vartable**: allows you to look at variance in your variables
  + note: lavan does *not* like big variances; might tell you to scale your variables
  

    ```{r verbatim = TRUE, comment = NA, message=FALSE, cache.comments= FALSE, warning = FALSE, eval=FALSE, error = FALSE}
    vartable(fit)
    ```

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/var.png)

--- .class #id 

## Advantages

>- **Multiple Regression**
  + Good for predicting variance in an IV, based on linear combinations of interval/dichotomous variables
>- **Structural Equation Modeling**
  + Can examine variables not directly assessed/observed
  + Can specify/estimate more complicated path models
  + Less emphasis on null-hypothesis significance testing
  + Can account for measurement error

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/thumbs-up.png)

--- .class #id 

## Disadvantages

>- **Multiple Regression**
  + Does not consider measurement error
  + Cannot have multiple "dependent variables"
  + Unable to deal with theoretically complex models
  + Problems with interpretations of beta-weights (see Nathans et al., 2012), bivariate hypotheses (see O'Neill et al., 2014) and significance testing
  
![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/thumb-down.png)


--- .class #id 

## Disadvantages (con't)

>- **Structural Equation Modeling**
  + Large burden on researcher to justify structure/design of model.
  + Assumptions of causality - invalid and unjustified
  + Considering "equivalent models"
  + Implications for replication; difficult given number of assumptions and sample size requirements
  
![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/thumb-down.png)

--- .class #id 

## Reflections

>-  *"I found I was more critical as I was thinking about how to conceptually explain MR and SEM. I focused on the words I would need to conceptualize both analytic techniques, and had to be careful not to use loaded language (e.g., significance testing, cause/effect"* - **Lindsay**
>- *"I learned a lot about the advantages and disadvantages of these techniques, especially around the sheer volume of assumptions for SEM. I also quite liked the lavaan package in R, and think it has quite a lot of flexibility that I might use in the future"* - **Katie**
>- *"INSERT QUOTE"* - **Kaytlin**
>- *"INSERT QUOTE"* - **Sandy**

![](/Users/katiecherry/Dropbox/GROUP PROJECT PSYC*6380/KATIE'S FOLDER/Group Project/think.png)

--- .class #id 

<style>
article li.build {
  font-size: 14px;
}
</style>


## References

+ Beaujean, A. A. (2014). *Latent variable modeling using R: A step-by-step guide*. New York: Routledge.

+ Hox, J. J., & Bechger, T. M. (1998). An introduction to structural equation modeling. *Family Science Review, 11*, 354-373.

+ Kline, R. B. (2016). *Principles and practice of structural equation modeling*. New York, NY: The Guilford Press. 

+ Nathans, L. L., Frederick, L., & Nimon, K. (2012). Interpreting multiple linear regression: A guidebook of variable importance. *Practical Assessment, Research, & Evaluation, 17*(9), 1-19.

+ O'Neill, T. A., McLarnon, M. J. W., Schneier, T. J., & Gardner, R. C. (2014). Current misuses of multiple regression for investigating bivariate hypotheses: An example from the organizational domain. *Behavioural Research, 46*, 798-807.

+ Westfall, J., & Yarkoni, T. (2016). Statistically controlling for confounding constructs is harder than you think. *PLOS One, 11*, 1-22.

+ Yves Rosseel (2012). lavaan: An R package for structural equation modeling. *Journal of Statistical Software, 48*(2), 1-36. URL http://www.jstatsoft.org/v48/i02/
