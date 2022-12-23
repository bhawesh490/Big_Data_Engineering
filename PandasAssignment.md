### Q1. How do you load a CSV file into a Pandas DataFrame?
A1.Lets assume we have a csv file name bhawesh.csv 

```
import pandas as pd 
df = pd.read_csv('bhawesh.csv') 
print(df.to_string())
```


### Q2. How do you check the data type of a column in a Pandas DataFrame?
A2. We can check the data type of column in Pandas using below code
```
<!-- importing pandas package -->
import pandas as pd
<!-- create a Pandas DataFrame -->
df = pd.DataFrame({'Col1':[1,2,3,4,5], 
'Col2':['bhawesh', 'yogesh','shashank','vishal','rahul'], 
'Col3':[1.2, 8.9,9.1,2,1,4,2]})
print("DataFrame is:")
print(df)
<!-- apply the dtype attribute -->
result = df.dtypes
print("Types of Columns in dataframe is")
print(result)
```

Q3. How do you select rows from a Pandas DataFrame based on a condition?
A3.lets assume we have a dataframe like 
df = pd.DataFrame({'Col1':["Bangalore","Pune","Delhi","Hyderabad","Bangalore"],
 'Col2':[1,2,3,4,5])

case 1
lets suppose we have to filter out only Bangalore city we will use this

df.iloc[df['Col1']=='Bangalore',:]

case 2
lets assume we have to get a dataframe with Col1 as Bangalore and Col2 with Number 5 
df.iloc[((df['Col1']=='Bangalore')&(df['Col2']==5)),:]

case 3
lets assume we have to get a dataframe with Col1 as Bangalore or Pune 

df.iloc[((df['Col1']=='Bangalore')|(df['Col1']=='Pune')),:]

|=OR Operator 
&=AND Operator

Q4. How do you rename columns in a Pandas DataFrame?
A4.Using Rename Method
df.rename(col={'Old Name':'New Name'},inplace=True)

Q5. How do you drop columns in a Pandas DataFrame?
A5. Using Drop Method
    Lets assume we have a dataframe with Col Names A,B,C
    Dropping Single Column
    df.drop(['A'], axis=1)

    Dropping Multiple Columns 
    Lets Drop Column B and C 
    df.drop(['B','C'], axis=1)

Q6. How do you find the unique values in a column of a Pandas DataFrame?
A6.Using .unique() method

import pandas as pd
data = {
  "Students": ["Bhawesh", "Hardik", "Molik", "Pradeep", "Kartikey", "Rahul", "Saksham", "Gaurav"],
  "Subjects": ["Maths", "Pyhsics", "Chemsitry", "Maths", "Chemistry", "Maths", "Statistics", "Computers"]
}

#load data into a DataFrame object:
df = pd.DataFrame(data)

print(df["Subjects"].unique())
 
Q7. How do you find the number of missing values in each column of a Pandas DataFrame?
A7.We can use pandas “isna()” function to find out all the fields which have missing values. 
This will return True if a field has missing values and false if the field does not have missing values.
df.isna().sum().reset_index(name="n").

This will give Column wise count of null values in df dataframe

Q8. How do you fill missing values in a Pandas DataFrame with a specific value?
A8.Using "fillna('Replaced Value',inplace=True)
Example:
We have a dataframe named df which contains some null values 
we need to replace na values with a string called 'Missing Values' so we will use this command 
df.fillna('Missing Values',inplace=True)

Q9. How do you concatenate two Pandas DataFrames?
A9.We can use the concat function in pandas to append either columns or rows from one DataFrame to another. 

Let’s grab two subsets of our data to see how this works.

1)Read in first 10 lines of students table
students_sub = students_df.head(10)

2)Grab the last 10 rows
students_sub_last10 = students_df.tail(10)

3) Reset the index values to the second dataframe appends properly

students_sub_last10 = students_sub_last10.reset_index(drop=True)

Note: drop=True option avoids adding new index column with old index values

Important Notes on Axis

When we concatenate DataFrames, we need to specify the axis.
axis=0 tells pandas to stack the second DataFrame UNDER the first one. 
It will automatically detect whether the column names are the same and will stack accordingly. 
axis=1 will stack the columns in the second DataFrame to the RIGHT of the first DataFrame. 
To stack the data vertically, we need to make sure we have the same columns 
and associated column format in both datasets. 
When we stack horizontally, we want to make sure what we are doing makes sense 
(i.e. the data are related in some way).


# Stack the DataFrames on top of each other
vertical_stack = pd.concat([student_sub, student_sub_last10], axis=0)


# Place the DataFrames side by side
horizontal_stack = pd.concat([student_sub, student_sub_last10], axis=1)


Q10. How do you merge two Pandas DataFrames on a specific column?
A10.
The pandas function for performing joins is called merge and an Inner join is the default option:
Inner Join Example:
lets assume we have two dataframes named df1 and df2 with a common column 'city'
merged_inner = pd.merge(left=df1, right=df2, left_on='city', right_on='city')

Left joins
What if we want to add information from df1 to df2 without losing any of the information from df1? 
In this case, we use a different type of join called a  “left join”.

merged_left = pd.merge(left=df1, right=df2, how='left', left_on='city', right_on='city')

The pandas merge function supports two other join types:

1-Right (outer) join: Invoked by passing how='right' as an argument. 
Similar to a left join, except all rows from the right DataFrame are kept, while rows from the left DataFrame without matching join key(s) values are discarded.
2-Full (outer) join: Invoked by passing how='outer' as an argument.
This join type returns the all pairwise combinations of rows from both DataFrames; i.e., 
the result DataFrame will NaN where data is missing in one of the dataframes. 
This join type is very rarely used.

Q11. How do you group data in a Pandas DataFrame by a specific column and apply an aggregation function?
A11.Lets assume we have a dataframe named df containing multiple columns 
df=df.groupby(['city', 'District']).agg({"Population": 'min',
                                           "Age": 'median',
                                           "Litrecay": 'mean'})


Q12. How do you pivot a Pandas DataFrame?
A12.The pivot() function is used to reshaped a given DataFrame organized by given index / column values. 
This function does not support data aggregation, multiple values will result in a MultiIndex in the columns.
Syntax:
DataFrame.pivot(index=None, columns=None, values=None)
index:Column to use to make new frame’s index. If None, uses existing index.
columns:Column to use to make new frame’s columns
	
values:Column(s) to use for populating new frame’s values.
If not specified, all remaining columns will be used and the result will have hierarchically indexed columns.

Example:
df = pd.DataFrame({'aaa': ['one', 'one', 'one', 'two', 'two',
                           'two'],
                   'bbb': ['P', 'Q', 'R', 'P', 'Q', 'R'],
                   'ccc': [2, 3, 4, 5, 6, 7],
                   'ddd': ['h', 'i', 'j', 'k', 'l', 'm']})


df.pivot(index='aaa', columns='bbb', values='ccc')

Q13. How do you change the data type of a column in a Pandas DataFrame?
A13.DataFrame.astype() method is used to cast pandas object to a specified dtype. 

df = pd.DataFrame({
    'A': [1, 2, 3, 4, 5],
    'B': ['Bhawesh', 'Shubham', 'Ravi', 'Kiran', 'Puran'],
    'C': [1.1, '1.0', '1.3', 2, 5]})
 
# converting all columns to string type
df = df.astype(str)

We can use other method to change columns datatypes

Dataframe to that type, or we can pass a dictionary having column names as keys and datatype 
as values to change the type of selected columns. 

import pandas as pd
df = pd.DataFrame({
    'A': [1, 2, 3, 4, 5],
    'B': ['a', 'b', 'c', 'd', 'e'],
    'C': [1.1, '1.0', '1.3', 2, 5]})
 
# using dictionary to convert specific columns
convert_dict = {'A': float,
                'C': int
                }
 
df = df.astype(convert_dict)
print(df.dtypes)


Q14. How do you sort a Pandas DataFrame by a specific column?
A14.
sorted_df = df.sort_values(by=['Column_name'], ascending=True)

Q15. How do you create a copy of a Pandas DataFrame?

A15. Using copy() method
The copy() method returns a copy of the DataFrame.

By default, the copy is a "deep copy" meaning that any changes made in the original DataFrame will NOT be reflected in the copy.

import pandas as pd
data = {
"name": ["Bhawesh", "Chetan", "Kamal"],
"Hobbies": ['Singing', 'Dancing', 'Playing']
}

df = pd.DataFrame(data)
#Make a copy:
newdf = df.copy()
print(newdf)

Q16. How do you filter rows of a Pandas DataFrame by multiple conditions?
A16.
import pandas as pd
dataFrame = pd.DataFrame({'Name': ['Bhawesh', ' Kamal', 'Rahul',' Hardik ', 'Ankit', 'Ramesh'],
                           
                          'Age': [30, 29, 29, 27, 21, 19],
                           
                          'Salary': [10000, 93000, 88000, 120000, 94000, 95000],
                           
                          'JOB': ['Analyst', 'Engineer', 'Data Engineer', 'Officer','IT', 'Musician']})
# filter dataframe
dataFrame.loc[(dataFrame['Salary']>=100000) & (dataFrame['Age']< 40) & (dataFrame['JOB'].str.startswith('D')),
                    ['Name','JOB']])

&=And Operator
|=Or Operator


Q17. How do you calculate the mean of a column in a Pandas DataFrame?
A17.
Using Mean Method on a single column 
df=df.loc['Column Name'].mean()

Using Mean Method on Multiple Columns 
df=df.loc[['Column Name A','Column Name B']].mean()

Q18. How do you calculate the standard deviation of a column in a Pandas DataFrame?
A18.
import pandas as pd

my_data = {'Name':pd.Series(['Bhawesh','Yogesh','Hardik','Kartik','Chetan']),
'Age':pd.Series([30, 31, 29, 13, 25]),
'value':pd.Series([8.79,23.24,31.98,78.56,90.20])}

print("The dataframe is :")
my_df = pd.DataFrame(my_data)
print(my_df)

print("The standard deviation of column 'Age' is :")
print(my_df['Age'].std())
print("The standard deviation of column 'value' is :")
print(my_df['value'].std())

Q19. How do you calculate the correlation between two columns in a Pandas DataFrame?
A19.By using corr() function we can get the correlation between two columns in the dataframe.
dataframe[‘first_column’].corr(dataframe[‘second_column’])

Note:
1-dataframe is the input dataframe
2-first_column is correlated with second_column of the dataframe

# import pandas module
import pandas as pd
 
# create dataframe with 3 columns
data = pd.DataFrame({
    "column1": [12, 23, 45, 67],
    "column2": [67, 54, 32, 1],
    "column3": [34, 23, 56, 23]
}
)
# display dataframe
print(data)
 
# correlation between column 1 and column2
print(data['column1'].corr(data['column2']))

Q20. How do you select specific columns in a DataFrame using their labels?
A20.Using loc 

df=df.loc[:,['ColA':'ColB','ColC','ColD']]

Q21. How do you select specific rows in a DataFrame using their indexes?
A21.Using Loc 
select the rows with index labels '3', '6', and '9'
df.loc[[3, 6, 9]]

Using iloc 

select the 3rd, 4th, and 5th rows of the DataFrame
df.iloc[[2, 3, 4]]

The Difference Between .iloc and .loc
The examples above illustrate the subtle difference between .iloc an .loc:

.iloc selects rows based on an integer index. So, if you want to select the 5th row in a DataFrame, you would use df.iloc[[4]] since the first row is at index 0, the second row is at index 1, and so on.
.loc selects rows based on a labeled index. So, if you want to select the row with an index label of 5, you would directly use df.loc[[5]].


Q22. How do you sort a DataFrame by a specific column?
A22.
sorted_df = df.sort_values(by=['Column_name'], ascending=True)

Q23. How do you create a new column in a DataFrame based on the values of another column?
A23.
We can use this by apply method in dataframe
import pandas as pd

df = pd.DataFrame(
    [
        (1, 'Hello', 158, True, 12.8),
        (2, 'Hey', 567, False, 74.2),
        (3, 'Hi', 123, False, 1.1),
        (4, 'Howdy', 578, True, 45.8),
        (5, 'Hello', 418, True, 21.1),
        (6, 'Hi', 98, False, 98.1),
    ],
    columns=['colA', 'colB', 'colC', 'colD', 'colE']
)
print(df)

For example, you can define your own method 
and then pass it to the apply() method. 
Let’s suppose we want to create a new column called 'ColNew' 
that will be created based on the values of the column colC using the categorise() 
method defined below:

def categorise(row):  
    if row['colC'] > 0 and row['colC'] <= 99:
        return 'A'
    elif row['colC'] > 100 and row['colC'] <= 199:
        return 'B'
    elif row['colC'] > 200  and row['colC'] <= 299:
        return 'C'
    return 'D'

All you need to do is to pass the above method to apply() as a lambda expression:

df['ColNew'] = df.apply(lambda x: categorise(x), axis=1)


Q24. How do you remove duplicates from a DataFrame?
A24.
We can use drop_duplicates(inplace=True)
By default, it removes duplicate rows based on all columns.

To remove duplicates on specific column(s), use subset.
df.drop_duplicates(subset=['city'],inplace=True)

To remove duplicates and keep last occurrences, use keep.
df.drop_duplicates(subset=['city', 'district'], keep='last')
 

Q25. What is the difference between .loc and .iloc in Pandas?
A25.loc is label-based, which means that you have to specify rows and columns based on their row and column labels.
iloc is integer position-based, so you have to specify rows and columns by their integer position values (0-based integer position).


import pandas as pd
 
# creating a sample dataframe

data = pd.DataFrame({'Brand': ['Maruti', 'Hyundai', 'Tata',
                               'Mahindra', 'Maruti', 'Hyundai',
                               'Renault', 'Tata', 'Maruti'],
                     'Year': [2012, 2014, 2011, 2015, 2012,
                              2016, 2014, 2018, 2019],
                     'Kms Driven': [50000, 30000, 60000,
                                    25000, 10000, 46000,
                                    31000, 15000, 12000],
                     'City': ['Gurgaon', 'Delhi', 'Mumbai',
                              'Delhi', 'Mumbai', 'Delhi',
                              'Mumbai', 'Chennai',  'Ghaziabad'],
                     'Mileage':  [28, 27, 25, 26, 28,
                                  29, 24, 21, 24]})
 
# displaying the DataFrame
display(data)

# selecting cars with brand 'Maruti' and Mileage > 25
display(data.loc[(data.Brand == 'Maruti') & amp
                 (data.Mileage & gt
                  25)])


# selecting range of rows from 2 to 5
display(data.loc[2: 5])

The iloc() function is an indexed-based selecting method which means that we have to pass an 
integer index in the method to select a specific row/column. 
This method does not include the last element of the range passed in it unlike loc(). iloc() does not accept the boolean data unlike loc(). Operations performed using iloc() are:

selecting 0th, 2th, 4th, and 7th index rows
display(data.iloc[[0, 2, 4, 7]])

