# Analyzing-Yelp-Data
We will analyze a subset of Yelp's business, reviews and user data. This dataset comes to us from Kaggle although we have taken steps to pull this data into a publis s3 bucket: `s3://sta9760-yelpdataset/yelp-light/*business.json`

### Data Source: [Yelp Dataset](https://www.kaggle.com/yelp-dataset/yelp-dataset#yelp_academic_dataset_user.json)
<img src = 'https://media.giphy.com/media/1iphue3Q2fJuCzkjmC/giphy.gif' width = '300' high = '50'>
## [Analysis](https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/Analysis.ipynb)
## You will learn about:
- Leverage large data by using powerful cluster
- Coding in PySpark

## Preparation:
- Upload the dataset to AWS S3
- Create Cluster/ Notebook in AWS EMR

### AWS S3

![](https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/Upload%20data%20to%20S3.png)
### Cluster Configuration 
![](https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/Create%20cluster.png)
### Notebook Configuration
![](https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/Create%20Notebook.png)

## Install & Import Essential Packages
- SparkSession
- pandas
- seaborn
- matplotlib

## Loading Data from S3
```
s3://{your_bucket_name}/{your_file_name}
```

## Overviewing Data
#### Showing all cloumns
```
df.printSchema()
```
## Analyzing Categories
- Association Table

Categories {1 : [a, b, c]} --> Category {1 : a, 1: b, 1: c}
- Total Categories
- Unique Numbers of Category
- Top 20 Popular Categories

**TOP3:** Restaurants, Shopping, Food

***Plotting the outcome***
<img src="https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/top20.PNG" height="400" width="560"> 
## Do Yelp Review Skew Negative?

The formula you can use is something like:

(row['avg(stars)'] - row['stars']) / row['stars']
<img src="https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/skew.PNG" height="400" width="560">
### Conclusion:
- **The plot seems like a normal distribution and there is no obvious skewness to either negative or positive.**
## Should the Elite be Trusted?
<img src="https://github.com/mendel462/Analyzing-Yelp-Data/blob/master/10GB%20Yelp%20Analysis-PySpark/diff.PNG" height="400" width="560">

### Conclusion:
- **Elite users are more likely to give a higher rating on review. We could trust them, but we should understand the fact that they usually given a higher point than normal users** 
