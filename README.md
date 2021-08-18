## 1 Introduction:

Medical Insurance in the US is a 'direct-fee' system, which relies on the private induvidials below the age of 65 years old to pay for the medical fees directly, usualy through a private medical insurance and obtained through the employer.

### 1.1 Screening

Lack of the health insurance leads to absence of the preventetive medicine, and as a result can increase the chances of serious illnesses among uninsured and untreated population.

### 1.2 Goals

The goal of this project is to determine whether there is a correlation between the insurance price and the variable parameters of the insurees including their induvidual circumstances. Additionally exploring how does induvidual circumstances compare to one another in significance and their affect on the insurance price.

### 1.3 Actions

The actions would be to educate and make aware people, who are looking into enrolling into a private medical insurance on how certain circumstances and life choices can affect the price of the premium to be paid.

### 1.4 Data

The data provided came from an example Kaggle project, and was sourced from a book 'Machine Learning with R by Brett Lantz'. It comes as a CSV file.

Traditionally the project has to be 'problem-centric', but due to the nature of this project it can only be 'data-centric', as it is the data I am required to work with, and I am limited to it.

There are 1338 rows and 7 columns in the CSV file provided, and there is no indication on how the data was collected and when it was collected. Leading to a potential bias and unreliability of the dataset. That is because it is an educational data, taken out of the context for practice/learning purposes only.

#### 1.4.1 Contents
    
The content and their describtion comes from the same source as the data:
    
__age:__ age of primary beneficiary

__sex:__ insurance contractor gender, female, male

__bmi:__ Body mass index, providing an understanding of body, weights that are relatively high or low relative to height, objective index of body weight (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9

__children:__ Number of children covered by health insurance / Number of dependents

__smoker:__ Smoking

__region:__ the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.

__charges:__ Individual medical costs billed by health insurance

### 1.5 Analysis

####  1.5.1 Data Analysis

Explaratory Data Analysis would be used to investigate the data.

#### 1.5.2 Data Visualisation

For the data visualisations, I would be relying partialy at Matplotlib and Seaborn libraries.

#### 1.5.3 Ethical Considerations

In this particular project, ethical considerations are unapplicable. Due to the training data.


## Results

Looking through the results, I have first inspected the data frame for any missing/abnormal/incorrect filled data (Ch. 3.1). It showed no abnormalities, and overall gave an impression of very clean dataset. 

The average insurance price is 13270.42 $ (Ch 3.2.7)

#### Age

Looking at the age, it shows a very balanced average age of 39.21. Standard deviation of 14.04 and the range of 46 years apart. (Ch 3.2.1)

Figure 1.1, looking at the relationship between insurance price and the age in the 10 year segment age groups, split with gender. We can see on the bar plot that there is a steady increase of insurance price with age, as well as the mean insurance price for male being higher for male over female insurers in all age segments. We will return to examining this later. 

In order to inspect the relationship further I have drown 5 scatter graphs of Age vs Insurance price and Hue: Sex, BMI, Children, Smoker, Region. All of the graphs show a clear three lines of positive trend. 

Figures 1-2 Hue: Sex; 1-3 Hue: BMI; 1-4 Hue: Children; 1-6 Hue: Region shows little or no correlation to explain the origin of the scatter graphs shape. 

Figure 1-5 Hue: Smoker on the other hand shows a distinctive correlation. The lower band is entirely non smokers. The upper band with the higher prices is smokers. The middle line is the mix between the two. 

A non-smoking individual in the age group ’60+’ can expect an average insurance charge of as much as 4 times greater than an individual in the ’10-19’ age group. This can grow to be as much as 9 times greater for smokers in the ’60+’ age group compared to non-smokers in the ’10-19’ age group, indicating once again, that smoking significantly increases the cost of insurance.

#### Gender

The gender split in the dataset is pretty equal. The data frame has 676 males and 662 females. (Ch 3.2.2) which is 51% / 49% split. 

The average price of the insurance for the males is 13956.75 $, and 12569.58 $ for the females. Difference is 1387.17 $

Digging deeper and looking at smokers and non smokers, the average price of the smoker male is 33042.01 $, while for a smoker female it is 30679.0 $ with a difference of 2363.01 $. Having male insurance price still being higher.

The non smoker average price for males is 8087.2 $ and 8762.3 $ for the females. Making a difference of -675.09 $, Making the average female non smoker insurance price actually pricier then for males. (Ch 3.2.7)

There are 274 smokers and 1064 non smokers in the dataset. (Ch 3.2.4)

Whether a male individual pays more for insurance than a female individual is significantly affected by whether the male is a smoker, which can be observed on Figure 8.2

Figure 8.2 shows that both smoker distributions are bimodal, which indicates that there is another factor that significantly affects the final insurance cost in the smoker sample other than gender.

In non-smokers, males are observed to pay on average 675.10 USD *less* than females, however upon further analysis, this was not found to be a statistically significant difference (p-value = 0.066 of two-sample t-test for a significance threshold of 0.05. (Ch 4)

#### BMI

The average BMI in the dataset is 30.66. The standard deviation of BMI values is 6.1. (Ch 3.2.3)

Looking at Figure 3.7, a KDE plot of Male and Female BMI distributions we can see that both of them are normally and evenly distributed. In fact almost identical.

Figure 3.2 is a scatter graph between the BMI and insurance price (Hue: Sex). The scatter graph shows three distinctive plots, implying that at least one another variable significantly varying the insurance price of individuals with the same BMI and gender. At the same time we see that gender is no that variable. 

Three distinctive plots are seen on all the scatter plots associated with BMI.

Looking at the further scatter graphs with Hue: Children, Region and Age. Figures 3.4, 3.5, 3.6. There are no observable effect and no segregation of insurance cost. 

However Figure 3.3 on the other hand Hue: Smoker reveals all three layers. 
	
1. The lowest insurance cost bracket contains a large proportion of non-smokers with a wide range of BMI values
2. The medium insurance cost bracket contains smokers with a BMI value less than 30, and some non-smokers with a high BMI value as well as non-smokers with low BMI value, who could potentially have other unfavourable attributes
3. The high insurance cost bracket, which contains mostly smokers with a high BMI value.

The above indicates that smokers and non-smokers are treated differently, with the single biggest factor affecting insurance cost in the smokers is BMI value. Meanwhile, it is not immediately clear what, if not a high BMI, could put a non-smoking individual into the medium insurance cost bracket.

#### Number of Children

The average number of children is closer to one, at 1.09. While out of the families who have at least one child, the average is 1.92.  The percentage of individuals without children is 43%.

It is hard to understand the relationship between number of children and insurance price, without investigating the matter further. A bar plot Figure 4.1 shows a distribution of insurance cost between number of children. 

#### Region

Distribution of induviduals per region is as follows:
- South West - 325
- South East - 364
- North West - 325
- North East - 324

All the regions are equally distributed. Figure 6.2 is a bar plot representing the insurance price per region. We can conclude from it that the highest insurance prices South East and the lowest is closely shared by South West and North West. 

However, looking closer at the data South East has considerably more smokers then any other region. 

South East - 91 smokers
South West - 58 smokers
North West - 58 smokers
North East - 67 smokers

Further investigation would be needed to understand significance of induvidual region on insurance prices.

#### Machine Learning

Multiple linear regression model was found to be a good predictor of an individual’s insurance cost based on the following attributes: age, sex, BMI, children, and smoker status with an R^2 value of 0.7789.

Removing the smoker status attribute dropped the R^2 to 0.0674 indicating that smoker is the single biggest factor accounting for over 70% variation between predicted and actual insurance costs of individuals.

### Conclusions

- The most significant factor on insurance price between induviduals in the data frame is smoking. It is far ahead of the rest of the parameters. The second place is taken by Age, and the third is by BMI.

- A person who doesnt smoke and with the age above 60 would average 4 times of what a person in the '10-19' group. 

- A person who smokes in the age above 60 would average 9 times of that if compared to a non smoker in the same '10-19' category.

- There was no statistically significant difference between insurance costs of male and female non-smokers. However, male smokers should expect to pay on average 2,363.01 USD more than female smokers.

- The number of children and an individual's region were found to have little or no affect on a persons insurance cost.  
