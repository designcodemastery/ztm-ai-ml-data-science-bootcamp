# Section 6: Pandas: Data Analysis

## Important: Downloading Workbooks and Assignments

Throughout the course and the rest of the sections, Daniel and I will share our code and workbooks with you, plus provide notes for each section for you to keep with you and study. You can find the entire course notebooks here: [https://github.com/mrdbourke/zero-to-mastery-ml](https://github.com/mrdbourke/zero-to-mastery-ml)

You can download the entire notebooks (click on the download button), or we have attached them as resources to each specific lecture. We have also provided a video at the end of this section titled [How To Download The Course Assignments](https://www.udemy.com/course/complete-machine-learning-and-data-science-zero-to-mastery/learn/lecture/17673810) if you need help getting set up when we do the assignments at the end of this section.

- [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/)
- [Introduction to Pandas Jupyter Notebook](https://github.com/mrdbourke/zero-to-mastery-ml/blob/master/section-2-data-science-and-ml-tools/introduction-to-pandas-video.ipynb)
- [Introduction to Pandas Jupyter Notebook with annotations](https://github.com/mrdbourke/zero-to-mastery-ml/blob/master/section-2-data-science-and-ml-tools/introduction-to-pandas.ipynb)
- [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html#min)
- [pandas-anatomy-of-a-dataframe](./pandas-anatomy-of-a-dataframe.png)
- [car-sales.csv](./car-sales.csv)

## Quick Note: Upcoming Videos

Hey there, Just a quick update on the code in the next videos.

You might see me run the code: car_sales.mean() This is to get the mean/average values of different columns in a pandas DataFrame. However, there’s been an update to pandas which means the above code will error.


The new code is: car_sales.mean(numeric_only=True) This tells pandas to only find the mean/average on numerical columns (not string-based columns).

In summary:

**Previous code (will error)**
car_sales.mean()
 
**New code (update to the pandas library)**
car_sales.mean(numeric_only=True)


As always, you can see the most up to date code examples on the course GitHub notebook/online book version:

Intro to pandas notebook on GitHub: https://github.com/mrdbourke/zero-to-mastery-ml/blob/master/section-2-data-science-and-ml-tools/introduction-to-pandas.ipynb

Intro to pandas notebook on course book website: https://dev.mrdbourke.com/zero-to-mastery-ml/introduction-to-pandas/

--- 

## Quick Note: Upcoming Videos

Hey there! Just a quick note for the next video.

You’ll see me write a line to change the Price column of the **car_sales** DataFrame like this: **car_sales["Price"] = car_sales["Price"].str.replace('[\$\,\.]', '')**

However, this will return an error if you’re using a newer version of pandas. Not to worry, the fix is quick! By adding **regex=True** (this tells pandas that the change is a “regular expression” or regex in Python for short) the code will work: **car_sales["Price"] = car_sales["Price"].str.replace('[\$\,\.]', '', regex=True)**


In summary:

### Previous code (will error)
``` python
car_sales["Price"] = car_sales["Price"].str.replace('[\$\,\.]', '')
```
 
### New code 
### Change Price column to integers
```python
car_sales["Price"] = car_sales["Price"].str.replace('[\$\,\.]', '', regex=True)
car_sales['Price'] = car_sales["Price"].astype(float).round(decimals=0)
car_sales['Price'] = car_sales["Price"].astype(int)
```
You can see the documentation for this operation on the pandas website under [pandas.Series.str.replace](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.replace.html).

And as always, you can see the most up to date code examples on the course GitHub notebook/online book version:

- Intro to pandas notebook on GitHub: [https://github.com/mrdbourke/zero-to-mastery-ml/blob/master/section-2-data-science-and-ml-tools/introduction-to-pandas.ipynb](https://github.com/mrdbourke/zero-to-mastery-ml/blob/master/section-2-data-science-and-ml-tools/introduction-to-pandas.ipynb)

- Intro to pandas notebook on course book website: [https://dev.mrdbourke.com/zero-to-mastery-ml/introduction-to-pandas/](https://dev.mrdbourke.com/zero-to-mastery-ml/introduction-to-pandas/)

Happy coding and let us know if you run into any other errors!