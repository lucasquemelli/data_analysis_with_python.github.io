# data_analysis_with_python.github.io
This is a repository about the study of data analysis with python.

# Data acquisition 

There are various formats for a dataset: .csv, .json, .xlsx etc. The dataset can be stored in different places, on your local machine or sometimes online.

The Pandas Library is a useful tool that enables us to read various datasets into a dataframe; our Jupyter notebook platforms have a built-in Pandas Library so that all we need to do is import Pandas without installing.

![image](https://user-images.githubusercontent.com/81119854/127533858-e4506f1e-4b93-4b07-900d-7f2860b49dd2.png)

# Read Data

We use pandas.read_csv() function to read the csv file. In the brackets, we put the file path along with a quotation mark so that pandas will read the file into a dataframe from that address. The file path can be either an URL or your local file address.

Because the data does not include headers, we can add an argument headers = None inside the read_csv() method so that pandas will not automatically set the first row as a header.

We can also assign the dataset to any variable you create.

![image](https://user-images.githubusercontent.com/81119854/127534385-465c3769-4897-45ff-869c-2243402423c5.png)

After reading the dataset, we can use the dataframe.head(n) method to check the top n rows of the dataframe, where n is an integer. Contrary to dataframe.head(n), dataframe.tail(n) will show you the bottom n rows of the dataframe.

![image](https://user-images.githubusercontent.com/81119854/127534498-626c7e6f-551e-4d52-b07b-bb1f198aa0cf.png)

![image](https://user-images.githubusercontent.com/81119854/127534693-4caea40d-e28a-4379-9e7f-3dc4d15210de.png)
![image](https://user-images.githubusercontent.com/81119854/127534724-8ebeb54e-fa6a-4380-be40-d2bd990e0f18.png)
![image](https://user-images.githubusercontent.com/81119854/127534778-b35a587c-1634-4763-a232-6c6f99bcc343.png)

# Add Headers

Take a look at our dataset. Pandas automatically set the header with an integer starting from 0. To better describe our data, we can introduce a header. Thus, we have to add headers manually. 

First, we create a list "headers" that include all column names in order. Then, we use dataframe.columns = headers to replace the headers with the list we created.

![image](https://user-images.githubusercontent.com/81119854/127535322-05dba6f6-d727-45af-9372-a6ae3b9f8227.png)

We replace headers and recheck our dataframe:

![image](https://user-images.githubusercontent.com/81119854/127535411-2ab105b0-847f-416f-9e25-942dd9c016b8.png)

![image](https://user-images.githubusercontent.com/81119854/127535446-d935669c-9aeb-4196-a0ae-e69246a33a7d.png)

We need to replace the "?" symbol with NaN, so the dropna() can remove the missing values:

![image](https://user-images.githubusercontent.com/81119854/127535576-6fc94ac4-46a9-4da5-8438-3d1adddb99c4.png)

We can drop missing values along the column "price" as follows:

![image](https://user-images.githubusercontent.com/81119854/127535982-6fc1dea7-4c84-41e9-b215-fa6d9eb6d9b8.png)

![image](https://user-images.githubusercontent.com/81119854/127536087-1da55ca2-d86e-4f3d-b647-600eff1dfdb8.png)

![image](https://user-images.githubusercontent.com/81119854/127536203-d90c3f20-be4e-41b9-963a-af88b272cca3.png)

![image](https://user-images.githubusercontent.com/81119854/127536395-fa971d57-1c51-418c-8533-1909672a07d1.png)

# Save Dataset

Correspondingly, Pandas enables us to save the dataset to csv. By using the dataframe.to_csv() method, you can add the file path and name along with quotation marks in the brackets.

For example, if you would save the dataframe df as automobile.csv to your local machine, you may use the syntax below, where index = False means the row names will not be written.

![image](https://user-images.githubusercontent.com/81119854/127538679-7d7e20d2-0aab-4878-9244-e36e29f5e099.png)

We can also read and save other file formats. We can use similar functions like pd.read_csv() and df.to_csv() for other data formats. The functions are listed in the following table:

![image](https://user-images.githubusercontent.com/81119854/127538817-ac414fd8-7e91-4f72-bc5c-379cfc94c370.png)

# Basic Insight of Dataset

After reading data into Pandas dataframe, it is time for us to explore the dataset. There are several ways to obtain essential insights of the data to help us better understand our dataset.

Data has a variety of types. The main types stored in Pandas dataframes are object, float, int, bool and datetime64. In order to better learn about each attribute, it is always good for us to know the data type of each column. In Pandas:

![image](https://user-images.githubusercontent.com/81119854/127539320-b6874be3-7845-41ef-8127-d5f83009b636.png)

![image](https://user-images.githubusercontent.com/81119854/127539381-f4a7b41f-66ff-4bf8-935e-27919c559303.png)

A series with the data type of each column is returned.

![image](https://user-images.githubusercontent.com/81119854/127539629-b5bd3915-b410-41bf-a80c-b76b3756d5b1.png)

![image](https://user-images.githubusercontent.com/81119854/127539702-3f3a9ded-7636-4f35-9188-4143f2ae0bd9.png)

If we would like to get a statistical summary of each column e.g. count, column mean value, column standard deviation, etc., we use the describe method:

![image](https://user-images.githubusercontent.com/81119854/127539888-85a28af3-de6c-4fe4-aa11-d15b0e77e584.png)

This method will provide various summary statistics, excluding NaN (Not a Number) values.

![image](https://user-images.githubusercontent.com/81119854/127540018-785e245d-24cc-43c8-b40f-1303609ebeb9.png)

This shows the statistical summary of all numeric-typed (int, float) columns.

For example, the attribute "symboling" has 201 counts, the mean value of this column is 0.84, the standard deviation is 1.25, the minimum value is -2, 25th percentile is 0, 50th percentile is 1, 75th percentile is 2, and the maximum value is 3.

If we would also like to check all the columns including those that are of type object, we can add an argument include = "all" inside the bracket.

![image](https://user-images.githubusercontent.com/81119854/127540558-a06216ae-1318-4404-9984-e46e94736b24.png)

Now it provides the statistical summary of all the columns, including object-typed attributes.
We can now see how many unique values there, which one is the top value and the frequency of top value in the object-typed columns.

Some values in the table above show as "NaN". This is because those numbers are not available regarding a particular column type.

![image](https://user-images.githubusercontent.com/81119854/127541489-27126cda-9b97-4ead-bd4d-ba9f439f9866.png)

![image](https://user-images.githubusercontent.com/81119854/127541543-3329ba7a-9afd-4bad-bedf-c471992af717.png)

Another method you can use to check your dataset is:

![image](https://user-images.githubusercontent.com/81119854/127541615-5f3141b5-d437-48b3-82e6-5147bd8e23ef.png)

It provides a concise summary of your DataFrame. This method prints information about a DataFrame including the index dtype and columns, non-null values and memory usage.

![image](https://user-images.githubusercontent.com/81119854/127541805-e2907cc4-faaf-4404-917d-c3a1b51679b3.png)

![image](https://user-images.githubusercontent.com/81119854/127541850-74fd5b30-dcad-4fef-a415-ddd85e5441c4.png)
![image](https://user-images.githubusercontent.com/81119854/127541911-48f742c6-bb06-45a3-a43d-34e1671a4c24.png)

# Data wrangling 

Data wrangling is the process of converting data from the initial format to a format that may be better for analysis.

First, we must import pandas. 

![image](https://user-images.githubusercontent.com/81119854/127715871-5580c962-0196-48da-a677-e69f64886158.png)

Let's read the dataset from the URL and adding the related headers.

![image](https://user-images.githubusercontent.com/81119854/127715987-16494df7-ad14-4a8b-843e-1af92e78e694.png)

![image](https://user-images.githubusercontent.com/81119854/127716017-adb1b29d-fc65-4240-864f-d2ec9083ed86.png)

Use the Pandas method read_csv() to load the data from the web address. Set the parameter "names" equal to the Python list "headers".

![image](https://user-images.githubusercontent.com/81119854/127716170-33e5aac4-cf22-4d81-95a5-c9f680fddf43.png)

Use the method head() to display the first five rows of the dataframe.

![image](https://user-images.githubusercontent.com/81119854/127716249-fb85d968-d63f-46c8-a362-b4194375a2bf.png)

As we can see, several question marks appeared in the dataframe; those are missing values which may hinder our further analysis. So, how do we identify all those missing values and deal with them? How to work with missing data?

Steps for working with missing data: (1) Identify missing data; (2) Deal with missing data; (3) Correct data format.

In the car dataset, missing data comes with the question mark "?". We replace "?" with NaN (Not a Number), Python's default missing value marker for reasons of computational speed and convenience. Here we use the function:

.replace(A, B, inplace = True) to replace A by B.

![image](https://user-images.githubusercontent.com/81119854/127716674-fc665b1e-efea-46d4-ab34-c7d97ef0f8d9.png)

![image](https://user-images.githubusercontent.com/81119854/127716703-c0ac3909-d144-49cc-bfb6-9923d8701311.png)

The missing values are converted by default. We use the following functions to identify these missing values. There are two methods to detect missing data:

.isnull()
.notnull()

The output is a boolean value indicating whether the value that is passed into the argument is in fact missing data.

![image](https://user-images.githubusercontent.com/81119854/127717001-c23c0430-ee47-420f-8da3-1c1a0c23023f.png)

![image](https://user-images.githubusercontent.com/81119854/127717068-c72ee141-14a7-431d-b5da-2498f71a69e5.png)

"True" means the value is a missing value while "False" means the value is not a missing value.

Using a for loop in Python, we can quickly figure out the number of missing values in each column. As mentioned above, "True" represents a missing value and "False" means the value is present in the dataset. In the body of the for loop the method ".value_counts()" counts the number of "True" values.

![image](https://user-images.githubusercontent.com/81119854/127717260-d37c7d23-c6af-46fa-86de-dfe5f24b3aff.png)

![image](https://user-images.githubusercontent.com/81119854/127717338-66a07a6c-af45-435f-be32-0a76184c6315.png)

![image](https://user-images.githubusercontent.com/81119854/127717355-a3e724af-505a-4ec5-9d40-909c5da5fcb0.png)

![image](https://user-images.githubusercontent.com/81119854/127717369-15b1d2a4-4c6e-444e-b59e-5855f915e9a9.png)

![image](https://user-images.githubusercontent.com/81119854/127717381-ef04ccfa-cfe4-4f33-b2a5-0b224768fa77.png)

Based on the summary above, each column has 205 rows of data and seven of the columns containing missing data:

"normalized-losses": 41 missing data
"num-of-doors": 2 missing data
"bore": 4 missing data
"stroke" : 4 missing data
"horsepower": 2 missing data
"peak-rpm": 2 missing data
"price": 4 missing data

How to deal with missing data?
Drop data
a. Drop the whole row
b. Drop the whole column
Replace data
a. Replace it by mean
b. Replace it by frequency
c. Replace it based on other functions

Whole columns should be dropped only if most entries in the column are empty. In our dataset, none of the columns are empty enough to drop entirely. We have some freedom in choosing which method to replace data; however, some methods may seem more reasonable than others. We will apply each method to many different columns:

Replace by mean:

"normalized-losses": 41 missing data, replace them with mean
"stroke": 4 missing data, replace them with mean
"bore": 4 missing data, replace them with mean
"horsepower": 2 missing data, replace them with mean
"peak-rpm": 2 missing data, replace them with mean

Replace by frequency:

"num-of-doors": 2 missing data, replace them with "four".
Reason: 84% sedans is four doors. Since four doors is most frequent, it is most likely to occur.

Drop the whole row:

"price": 4 missing data, simply delete the whole row.
Reason: price is what we want to predict. Any data entry without price data cannot be used for prediction; therefore any row now without price data is not useful to us.

Calculate the mean value for the "normalized-losses" column. 

![image](https://user-images.githubusercontent.com/81119854/127718328-59a77cc8-3d68-4066-bbc2-52823740304a.png)

Replace "NaN" with mean value in "normalized-losses" column

![image](https://user-images.githubusercontent.com/81119854/127718550-6cfdaf4b-1170-4d3c-b82c-97fe24490aa8.png)

Calculate the mean value for the "bore" column

![image](https://user-images.githubusercontent.com/81119854/127718613-91478d8b-81fe-43ed-8519-c426053b93a3.png)

Replace "NaN" with the mean value in the "bore" column

![image](https://user-images.githubusercontent.com/81119854/127718675-46211a1c-3134-4df2-a0dc-8f251487cdda.png)

![image](https://user-images.githubusercontent.com/81119854/127718841-d6726042-50eb-4fbe-b77e-4921b8ef98aa.png)

![image](https://user-images.githubusercontent.com/81119854/127718857-bf07cead-d7cc-4987-a7b0-b0e6d83e6404.png)

Calculate the mean value for the "horsepower" column

![image](https://user-images.githubusercontent.com/81119854/127719501-697fe29f-0dfc-43a7-ab64-66328a5357c9.png)

Replace "NaN" with the mean value in the "horsepower" column

![image](https://user-images.githubusercontent.com/81119854/127719603-d12e654d-97c8-408e-8161-d861a68c3d3d.png)

Calculate the mean value for "peak-rpm" column

![image](https://user-images.githubusercontent.com/81119854/127719685-1e4eb551-0d92-4290-9b80-9cc8a317103d.png)

Replace "NaN" with the mean value in the "peak-rpm" column

![image](https://user-images.githubusercontent.com/81119854/127719716-11db26d3-4bd4-4d43-85d3-e2c38dd39fbe.png)

To see which values are present in a particular column, we can use the ".value_counts()" method:

![image](https://user-images.githubusercontent.com/81119854/127719911-2a763089-67df-4c03-ba55-1200680a24b5.png)

We can see that four doors are the most common type. We can also use the ".idxmax()" method to calculate the most common type automatically:

![image](https://user-images.githubusercontent.com/81119854/127719953-b38cead4-5b3f-45a7-8a64-5b9149967cc3.png)

The replacement procedure is very similar to what we have seen previously:

![image](https://user-images.githubusercontent.com/81119854/127720017-cac86526-baf4-468d-835a-02b8a05e094a.png)

Finally, let's drop all rows that do not have price data:

![image](https://user-images.githubusercontent.com/81119854/127720085-0bde2de7-0b1a-42b4-8807-50806d0aa244.png)

![image](https://user-images.githubusercontent.com/81119854/127720109-9f7e6eb8-2cee-4c14-b7cc-e4c206f9a147.png)

Now, we have a dataset with no missing values.

The last step in data cleaning is checking and making sure that all data is in the correct format (int, float, text or other).

In Pandas, we use:

.dtype() to check the data type

.astype() to change the data type

![image](https://user-images.githubusercontent.com/81119854/127720871-9cd7dded-80c5-4dbd-a0c5-17ca6f27f702.png)

![image](https://user-images.githubusercontent.com/81119854/127720890-bece9fbf-139f-4932-8a31-e687099bc48f.png)

As we can see above, some columns are not of the correct data type. Numerical variables should have type 'float' or 'int', and variables with strings such as categories should have type 'object'. 

For example, 'bore' and 'stroke' variables are numerical values that describe the engines, so we should expect them to be of the type 'float' or 'int'; however, they are shown as type 'object'. We have to convert data types into a proper format for each column using the "astype()" method.

![image](https://user-images.githubusercontent.com/81119854/127721023-b6b39097-f1b4-45e2-9b93-016d5b1836df.png)

![image](https://user-images.githubusercontent.com/81119854/127721048-4be2da80-d11f-4adb-aa47-546434825677.png)

![image](https://user-images.githubusercontent.com/81119854/127721069-c0ffc8b1-fd2b-4f3e-bfeb-cde20a70f785.png)

Now we have finally obtained the cleaned dataset with no missing values with all data in its proper format.

Data is usually collected from different agencies in different formats. (Data standardization is also a term for a particular type of data normalization where we subtract the mean and divide by the standard deviation.)

Standardization is the process of transforming data into a common format, allowing the researcher to make the meaningful comparison.

In our dataset, the fuel consumption columns "city-mpg" and "highway-mpg" are represented by mpg (miles per gallon) unit. Assume we are developing an application in a country that accepts the fuel consumption with L/100km standard.

We will need to apply data transformation to transform mpg into L/100km.

The formula for unit conversion is:

L/100km = 235/mpg

We can do many mathematical operations directly in Pandas.

![image](https://user-images.githubusercontent.com/81119854/127721623-11971ba1-5679-497f-88a7-00feba850648.png)

![image](https://user-images.githubusercontent.com/81119854/127721647-31d5e6e1-23cb-42af-9762-53c335bdfb50.png)

![image](https://user-images.githubusercontent.com/81119854/127721661-f24ded71-24fb-4293-b217-a7d7f4ba518b.png)

![image](https://user-images.githubusercontent.com/81119854/127721755-79ef2d6c-4407-418c-b191-0ea82dbf463f.png)

