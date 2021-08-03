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

Why normalization?

Normalization is the process of transforming values of several variables into a similar range. Typical normalizations include scaling the variable so the variable average is 0, scaling the variable so the variance is 1, or scaling the variable so the variable values range from 0 to 1.

Example

To demonstrate normalization, let's say we want to scale the columns "length", "width" and "height".

Target: would like to normalize those variables so their value ranges from 0 to 1

Approach: replace original value by (original value)/(maximum value)

![image](https://user-images.githubusercontent.com/81119854/127722625-24b0abee-d95a-4671-9b25-6eb1ff11c116.png)

![image](https://user-images.githubusercontent.com/81119854/127722694-d6ee62e2-aa4d-4491-b6c8-a6c6143faae6.png)

![image](https://user-images.githubusercontent.com/81119854/127722703-20f87f34-a8a9-4165-b8f4-1cdec947451e.png)

Here we can see we've normalized "length", "width" and "height" in the range of [0,1].

Why binning?
Binning is a process of transforming continuous numerical variables into discrete categorical 'bins' for grouped analysis.

Example:

In our dataset, "horsepower" is a real valued variable ranging from 48 to 288 and it has 57 unique values. What if we only care about the price difference between cars with high horsepower, medium horsepower, and little horsepower (3 types)? Can we rearrange them into three ‘bins' to simplify analysis?

We will use the pandas method 'cut' to segment the 'horsepower' column into 3 bins.

Convert data to correct format:

![image](https://user-images.githubusercontent.com/81119854/127722929-22ba3b12-af24-44b4-aaa8-f7900f8d4480.png)

Let's plot the histogram of horsepower to see what the distribution of horsepower looks like.

![image](https://user-images.githubusercontent.com/81119854/127722986-b2790feb-14c7-465a-a10d-c62d488a3bf6.png)

![image](https://user-images.githubusercontent.com/81119854/127723001-65796a7c-d5e2-470b-b0be-fd05944cfed7.png)

We would like 3 bins of equal size bandwidth so we use numpy's linspace(start_value, end_value, numbers_generated function.

Since we want to include the minimum value of horsepower, we want to set start_value = min(df["horsepower"]).

Since we want to include the maximum value of horsepower, we want to set end_value = max(df["horsepower"]).

Since we are building 3 bins of equal length, there should be 4 dividers, so numbers_generated = 4.

We build a bin array with a minimum value to a maximum value by using the bandwidth calculated above. The values will determine when one bin ends and another begins.

![image](https://user-images.githubusercontent.com/81119854/127723167-892e7de0-5cd9-4eca-8879-ed483451f200.png)

![image](https://user-images.githubusercontent.com/81119854/127723291-a2e2976c-a5c8-413b-90cc-400e1f946c84.png)

We apply the function "cut" to determine what each value of df['horsepower'] belongs to.

![image](https://user-images.githubusercontent.com/81119854/127723387-5e4df349-cc74-4f48-9c43-decce7991531.png)

![image](https://user-images.githubusercontent.com/81119854/127723393-0e14f62b-d096-4b02-8aa5-78e03cfa074a.png)

Let's see the number of vehicles in each bin:

![image](https://user-images.githubusercontent.com/81119854/127723789-a5c5fa47-479b-4d9d-93ff-8c3e552ef03d.png)

Let's plot the distribution of each bin:

![image](https://user-images.githubusercontent.com/81119854/127723820-111f470b-0495-48ee-8ca9-3c140c73c760.png)

Normally, a histogram is used to visualize the distribution of bins we created above.

![image](https://user-images.githubusercontent.com/81119854/127723848-da7879d6-09d8-44b1-948e-a7d2fa720bc2.png)

![image](https://user-images.githubusercontent.com/81119854/127723850-ff9c6852-eec1-463e-a54c-dd1746b3e8e3.png)

What is an indicator variable?
An indicator variable (or dummy variable) is a numerical variable used to label categories. They are called 'dummies' because the numbers themselves don't have inherent meaning.

Why we use indicator variables?

We use indicator variables so we can use categorical variables for regression analysis in the later modules.

Example
We see the column "fuel-type" has two unique values: "gas" or "diesel". Regression doesn't understand words, only numbers. To use this attribute in regression analysis, we convert "fuel-type" to indicator variables.

We will use pandas' method 'get_dummies' to assign numerical values to different categories of fuel type.

![image](https://user-images.githubusercontent.com/81119854/127723915-0c1837a4-99d9-422a-9772-af1fadb83065.png)

Get the indicator variables and assign it to data frame "dummy_variable_1":

![image](https://user-images.githubusercontent.com/81119854/127723945-6252bdd5-b542-45d2-8e58-730ef261915e.png)

Change the column names for clarity:

![image](https://user-images.githubusercontent.com/81119854/127723974-722f33a7-4b81-446b-866b-1762157bb20d.png)

In the dataframe, column 'fuel-type' has values for 'gas' and 'diesel' as 0s and 1s now.

![image](https://user-images.githubusercontent.com/81119854/127724015-b8ba994d-eed3-4249-8e9f-cb7be9e69ca8.png)

![image](https://user-images.githubusercontent.com/81119854/127724260-e69d3236-a646-47de-bdef-73b84b16d32b.png)

![image](https://user-images.githubusercontent.com/81119854/127724272-359099ff-4dc9-4fc3-a82a-5d5397189c50.png)

![image](https://user-images.githubusercontent.com/81119854/127724302-b97df526-27ec-48bf-a464-cd526266ffc4.png)

Save the new csv:

![image](https://user-images.githubusercontent.com/81119854/127724307-de21ebe8-ced5-49a0-a29a-205a4a348363.png)

# Exploratory Data Analysis

Import libraries:

![image](https://user-images.githubusercontent.com/81119854/127927714-35cf8a9d-e10a-42c1-b76b-40508c8495d6.png)

![image](https://user-images.githubusercontent.com/81119854/127927773-427aadc1-8f11-48db-9ff7-aa69bb1b334c.png)

To install Seaborn we use pip, the Python package manager.

![image](https://user-images.githubusercontent.com/81119854/127927831-8574414c-a5d6-4e07-890f-bfb929b97323.png)

Import visualization packages "Matplotlib" and "Seaborn".

When visualizing individual variables, it is important to first understand what type of variable you are dealing with. This will help us find the right visualization method for that variable.

![image](https://user-images.githubusercontent.com/81119854/127927999-8c25b5cc-9b17-47f3-b6a8-531af9173c32.png)

![image](https://user-images.githubusercontent.com/81119854/127928292-f700b76d-d76c-4b3e-a7bd-7088f92b2101.png)

By checking the code above, we may see that the type of peak-rpm is float64.

We can calculate the correlation between variables of type "int64" or "float64" using the method "corr".

![image](https://user-images.githubusercontent.com/81119854/127928511-f3048b10-8439-4fc0-9017-fb964a61a863.png)

The diagonal elements are always one.

![image](https://user-images.githubusercontent.com/81119854/127928960-81dcbffe-b5e5-4181-a07a-50de77997c8c.png)

![image](https://user-images.githubusercontent.com/81119854/127929003-dc319126-482c-411a-b83d-9b6e78f9e4b2.png)

Continuous numerical variables are variables that may contain any value within some range. They can be of type "int64" or "float64". A great way to visualize these variables is by using scatterplots with fitted lines.

In order to start understanding the (linear) relationship between an individual variable and the price, we can use "regplot" which plots the scatterplot plus the fitted regression line for the data.

Let's see several examples of different linear relationships:

Positive Linear Relationship

Let's find the scatterplot of "engine-size" and "price".

![image](https://user-images.githubusercontent.com/81119854/127930471-73bb90d0-5f5e-42b1-86e4-e75c6c89152d.png)

![image](https://user-images.githubusercontent.com/81119854/127930497-19dda6c3-8abc-4f94-b9b0-67f18dbe8faa.png)

![image](https://user-images.githubusercontent.com/81119854/127930509-e6f2f53e-33b5-4548-9f23-fb5f8f9ff3c0.png)

As the engine-size goes up, the price goes up: this indicates a positive direct correlation between these two variables. Engine size seems like a pretty good predictor of price since the regression line is almost a perfect diagonal line.

We can examine the correlation between 'engine-size' and 'price' and see that it's approximately 0.87.

![image](https://user-images.githubusercontent.com/81119854/127930615-a206d5c7-51d4-49d9-90ce-902a2ea4ba75.png)

Highway mpg is a potential predictor variable of price. Let's find the scatterplot of "highway-mpg" and "price".

![image](https://user-images.githubusercontent.com/81119854/127930909-620b2c9b-3784-4038-ad26-0fd85fea5c8a.png)

As highway-mpg goes up, the price goes down: this indicates an inverse/negative relationship between these two variables. Highway mpg could potentially be a predictor of price.

We can examine the correlation between 'highway-mpg' and 'price' and see it's approximately -0.704.

![image](https://user-images.githubusercontent.com/81119854/127931061-ed163ddf-f9b0-45b4-a4c4-901f861b1c37.png)

Weak Linear Relationship

Let's see if "peak-rpm" is a predictor variable of "price".

![image](https://user-images.githubusercontent.com/81119854/127931867-87f38d48-bd83-461c-b1bc-33fc9247ad2e.png)

Peak rpm does not seem like a good predictor of the price at all since the regression line is close to horizontal. Also, the data points are very scattered and far from the fitted line, showing lots of variability. Therefore, it's not a reliable variable.

We can examine the correlation between 'peak-rpm' and 'price' and see it's approximately -0.101616.

![image](https://user-images.githubusercontent.com/81119854/127932064-b9ba6779-dba8-4fc7-b4e8-c4fc0efd5ccc.png)

![image](https://user-images.githubusercontent.com/81119854/127932156-89d37ab9-ab47-4f96-b64b-e3d0343941ad.png)

![image](https://user-images.githubusercontent.com/81119854/127932260-00b10fe6-7fb1-4c51-abb7-4abfb91a17d2.png)

![image](https://user-images.githubusercontent.com/81119854/127932348-b396db0c-5b6d-476f-b9bd-d8ae5e3b57d2.png)

It is not expected a good linear correlation between price and stroke due to the correlation coefficient 0.08231.

![image](https://user-images.githubusercontent.com/81119854/127932563-73332e5e-ec24-42a7-b81f-38df26be92d8.png)

Categorical Variables

These are variables that describe a 'characteristic' of a data unit, and are selected from a small group of categories. The categorical variables can have the type "object" or "int64". A good way to visualize categorical variables is by using boxplots.

Let's look at the relationship between "body-style" and "price".

![image](https://user-images.githubusercontent.com/81119854/127932657-6b26a315-615e-4bcb-a9de-02aed0f4ebe8.png)

![image](https://user-images.githubusercontent.com/81119854/127932794-53b0aa89-0cda-4642-9c83-4be88c548b9d.png)

We see that the distributions of price between the different body-style categories have a significant overlap, so body-style would not be a good predictor of price. Let's examine engine "engine-location" and "price":

![image](https://user-images.githubusercontent.com/81119854/127932855-029056ce-1668-4aa2-8012-6a79b428bdf6.png)

Here we see that the distribution of price between these two engine-location categories, front and rear, are distinct enough to take engine-location as a potential good predictor of price.

Let's examine "drive-wheels" and "price".

![image](https://user-images.githubusercontent.com/81119854/127932960-66942914-3fd4-42f8-b45b-29ed02e3e600.png)

Here we see that the distribution of price between the different drive-wheels categories differs. As such, drive-wheels could potentially be a predictor of price.

Descriptive Statistical Analysis

Let's first take a look at the variables by utilizing a description method.

The describe function automatically computes basic statistics for all continuous variables. Any NaN values are automatically skipped in these statistics.

This will show:

the count of that variable
the mean
the standard deviation (std)
the minimum value
the IQR (Interquartile Range: 25%, 50% and 75%)
the maximum value

We can apply the method "describe" as follows:

![image](https://user-images.githubusercontent.com/81119854/127934082-6f43bd70-49f8-4004-8067-c5b3eff674b3.png)

The default setting of "describe" skips variables of type object. We can apply the method "describe" on the variables of type 'object' as follows:

![image](https://user-images.githubusercontent.com/81119854/127934172-63753c05-0834-4e12-89e6-209bb4e57c6e.png)

Value Counts
Value counts is a good way of understanding how many units of each characteristic/variable we have. We can apply the "value_counts" method on the column "drive-wheels". Don’t forget the method "value_counts" only works on pandas series, not pandas dataframes. As a result, we only include one bracket df['drive-wheels'], not two brackets df[['drive-wheels']].

![image](https://user-images.githubusercontent.com/81119854/127934352-d06ff2db-050e-48a9-9dcc-e9c3665d909c.png)

We can convert the series to a dataframe as follows:

![image](https://user-images.githubusercontent.com/81119854/127934412-bfa7a65a-b39b-4f8e-81ab-518958613add.png)

Let's repeat the above steps but save the results to the dataframe "drive_wheels_counts" and rename the column 'drive-wheels' to 'value_counts'.

![image](https://user-images.githubusercontent.com/81119854/127934497-3a1bf2b4-fe4d-4b4a-a721-9b27090932b1.png)

Now let's rename the index to 'drive-wheels':

![image](https://user-images.githubusercontent.com/81119854/127934604-326a1546-b1c8-48fb-8fec-dc9ed698f118.png)

We can repeat the above process for the variable 'engine-location'.

After examining the value counts of the engine location, we see that engine location would not be a good predictor variable for the price. This is because we only have three cars with a rear engine and 198 with an engine in the front, so this result is skewed. Thus, we are not able to draw any conclusions about the engine location.

Basics of Grouping

The "groupby" method groups data by different categories. The data is grouped based on one or several variables, and analysis is performed on the individual groups.

For example, let's group by the variable "drive-wheels". We see that there are 3 different categories of drive wheels.

![image](https://user-images.githubusercontent.com/81119854/127936485-2f3a2f3d-c010-4458-9673-5d71f896bde1.png)

If we want to know, on average, which type of drive wheel is most valuable, we can group "drive-wheels" and then average them.

We can select the columns 'drive-wheels', 'body-style' and 'price', then assign it to the variable "df_group_one".

![image](https://user-images.githubusercontent.com/81119854/127936606-5678e8e5-e736-4ca1-8946-6a34c4d021a2.png)

We can then calculate the average price for each of the different categories of data.

![image](https://user-images.githubusercontent.com/81119854/127936713-f8132467-b610-4373-9a19-9f781fee89dd.png)

From our data, it seems rear-wheel drive vehicles are, on average, the most expensive, while 4-wheel and front-wheel are approximately the same in price.

![image](https://user-images.githubusercontent.com/81119854/127936849-c3cb83a0-51d2-4252-928b-28d4b64ea91b.png)

![image](https://user-images.githubusercontent.com/81119854/127936975-1c1d0d79-c2dc-48b2-a984-6e14c1d1984a.png)

This grouped data is much easier to visualize when it is made into a pivot table. A pivot table is like an Excel spreadsheet, with one variable along the column and another along the row. We can convert the dataframe to a pivot table using the method "pivot" to create a pivot table from the groups.

In this case, we will leave the drive-wheels variable as the rows of the table, and pivot body-style to become the columns of the table:

![image](https://user-images.githubusercontent.com/81119854/127937092-f50d84aa-ec71-4ba2-aadd-f98d3c88dd9d.png)

Often, we won't have data for some of the pivot cells. We can fill these missing cells with the value 0, but any other value could potentially be used as well. It should be mentioned that missing data is quite a complex subject and is an entire course on its own.

![image](https://user-images.githubusercontent.com/81119854/127937260-0df8dd45-55c3-4be3-bfc3-81270adc0fe6.png)

![image](https://user-images.githubusercontent.com/81119854/127937357-f8a12141-ba6d-4193-9e7c-d50421c0f8f0.png)

Let's use a heat map to visualize the relationship between Body Style vs Price.

![image](https://user-images.githubusercontent.com/81119854/127937441-21870011-7d9c-442f-9fc3-60bfbe480f62.png)

![image](https://user-images.githubusercontent.com/81119854/127937474-7107096e-e844-403b-b0a3-4dc97a8b601d.png)

The heatmap plots the target variable (price) proportional to colour with respect to the variables 'drive-wheel' and 'body-style' on the vertical and horizontal axis, respectively. This allows us to visualize how the price is related to 'drive-wheel' and 'body-style'.

The default labels convey no useful information to us. Let's change that:

![image](https://user-images.githubusercontent.com/81119854/127937715-003a01ac-606f-4fa3-aa75-5ccdfead0bec.png)

![image](https://user-images.githubusercontent.com/81119854/127937809-9fc2e717-a342-48b3-9453-94989d79354f.png)

Correlation and Causation

Correlation: a measure of the extent of interdependence between variables.

Causation: the relationship between cause and effect between two variables.

It is important to know the difference between these two. Correlation does not imply causation. Determining correlation is much simpler the determining causation as causation may require independent experimentation.

Pearson Correlation

The Pearson Correlation measures the linear dependence between two variables X and Y.

The resulting coefficient is a value between -1 and 1 inclusive, where:

1: Perfect positive linear correlation.
0: No linear correlation, the two variables most likely do not affect each other.
-1: Perfect negative linear correlation.

Pearson Correlation is the default method of the function "corr". Like before, we can calculate the Pearson Correlation of the of the 'int64' or 'float64' variables.

![image](https://user-images.githubusercontent.com/81119854/127938075-002924f8-0214-421c-a495-73e57e403e36.png)

Sometimes we would like to know the significant of the correlation estimate.

P-value

What is this P-value? The P-value is the probability value that the correlation between these two variables is statistically significant. Normally, we choose a significance level of 0.05, which means that we are 95% confident that the correlation between the variables is significant.

By convention, when the

p-value is  <  0.001: we say there is strong evidence that the correlation is significant.
the p-value is  <  0.05: there is moderate evidence that the correlation is significant.
the p-value is  <  0.1: there is weak evidence that the correlation is significant.
the p-value is  >  0.1: there is no evidence that the correlation is significant.

We can obtain this information using "stats" module in the "scipy" library.

![image](https://user-images.githubusercontent.com/81119854/127938296-353af83e-a2fd-4e5c-9660-eff09b536daf.png)

Wheel-Base vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'wheel-base' and 'price'.

![image](https://user-images.githubusercontent.com/81119854/127938472-60b47248-45a9-4963-b96d-300cd6e3bd68.png)

Conclusion: Since the p-value is  <  0.001, the correlation between wheel-base and price is statistically significant, although the linear relationship isn't extremely strong (~0.585).

Horsepower vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'horsepower' and 'price'.

![image](https://user-images.githubusercontent.com/81119854/127938569-1295a090-6708-4e91-bde3-dd763533d222.png)

Conclusion: Since the p-value is  <  0.001, the correlation between horsepower and price is statistically significant, and the linear relationship is quite strong (~0.809, close to 1).

Length vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'length' and 'price'.

![image](https://user-images.githubusercontent.com/81119854/127938670-dba167e8-da2f-4150-928b-22c351c6e70c.png)

Conclusion: Since the p-value is  <  0.001, the correlation between length and price is statistically significant, and the linear relationship is moderately strong (~0.691).

Width vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'width' and 'price':

![image](https://user-images.githubusercontent.com/81119854/127938719-04e1ff3d-d2fe-47aa-97a0-c9d5cf945588.png)

Conclusion: Since the p-value is < 0.001, the correlation between width and price is statistically significant, and the linear relationship is quite strong (~0.751).

Curb-Weight vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'curb-weight' and 'price':

![image](https://user-images.githubusercontent.com/81119854/127938866-8f5f131f-08a4-48f7-8ee2-fef19b37df80.png)

Conclusion: Since the p-value is  <  0.001, the correlation between curb-weight and price is statistically significant, and the linear relationship is quite strong (~0.834).

Engine-Size vs. Price

Let's calculate the Pearson Correlation Coefficient and P-value of 'engine-size' and 'price':

![image](https://user-images.githubusercontent.com/81119854/127938927-54b4bd40-2e28-4e5f-996d-0bc2fedb3221.png)

Conclusion: Since the p-value is  <  0.001, the correlation between engine-size and price is statistically significant, and the linear relationship is very strong (~0.872).

ANOVA

ANOVA: Analysis of Variance

The Analysis of Variance (ANOVA) is a statistical method used to test whether there are significant differences between the means of two or more groups. ANOVA returns two parameters:

F-test score: ANOVA assumes the means of all groups are the same, calculates how much the actual means deviate from the assumption, and reports it as the F-test score. A larger score means there is a larger difference between the means.

P-value: P-value tells how statistically significant our calculated score value is.

If our price variable is strongly correlated with the variable we are analyzing, we expect ANOVA to return a sizeable F-test score and a small p-value.

Drive Wheels

Since ANOVA analyzes the difference between different groups of the same variable, the groupby function will come in handy. Because the ANOVA algorithm averages the data automatically, we do not need to take the average before hand.

To see if different types of 'drive-wheels' impact 'price', we group the data.

![image](https://user-images.githubusercontent.com/81119854/127939326-2a17c365-b04b-47bc-9a23-bbd3131a5be9.png)

![image](https://user-images.githubusercontent.com/81119854/127939359-0a5ac805-4b38-414e-a693-fd3c3ca4f00f.png)

We can obtain the values of the method group using the method "get_group".

![image](https://user-images.githubusercontent.com/81119854/127939415-c8b9ddf1-5db4-4564-ace8-2d88498a8ffb.png)

We can use the function 'f_oneway' in the module 'stats' to obtain the F-test score and P-value.

![image](https://user-images.githubusercontent.com/81119854/127939472-937531d5-7f3c-4a98-ae4c-818324633025.png)

This is a great result with a large F-test score showing a strong correlation and a P-value of almost 0 implying almost certain statistical significance. But does this mean all three tested groups are all this highly correlated?

Let's examine them separately.

fwd and rwd

![image](https://user-images.githubusercontent.com/81119854/127939587-57498b69-e3e8-4f9b-8854-3dda320760e0.png)

4wd and rwd

![image](https://user-images.githubusercontent.com/81119854/127939633-e9a4928c-7c16-4732-b0f8-91dcc9ed7893.png)

4wd and fwd

![image](https://user-images.githubusercontent.com/81119854/127939673-0997a405-2c07-4b01-bbcb-8b5a55684970.png)

# Model Development

Import libraries:

![image](https://user-images.githubusercontent.com/81119854/128060605-6c62a39f-c299-4f82-8089-510e80554c8e.png)

Load the data and store it in dataframe df:

![image](https://user-images.githubusercontent.com/81119854/128060790-e8688575-5b79-4018-88cc-350ac5e7ca66.png)

1. Linear Regression and Multiple Linear Regression

Linear Regression
One example of a Data Model that we will be using is:

Simple Linear Regression
Simple Linear Regression is a method to help us understand the relationship between two variables:

The predictor/independent variable (X)
The response/dependent variable (that we want to predict)(Y)
The result of Linear Regression is a linear function that predicts the response (dependent) variable as a function of the predictor (independent) variable.

Linear Function

![image](https://user-images.githubusercontent.com/81119854/128060994-a15c91b4-bf00-4e0f-9e05-6bdcb82c6c45.png)

a refers to the intercept of the regression line, in other words: the value of Y when X is 0
b refers to the slope of the regression line, in other words: the value with which Y changes when X increases by 1 unit

Let's load the modules for linear regression:

![image](https://user-images.githubusercontent.com/81119854/128061113-ace34662-955e-47db-95b6-5310f14bd5b4.png)

Create the linear regression object:

![image](https://user-images.githubusercontent.com/81119854/128061240-48ae2963-5295-41dd-8929-98ba30755f9c.png)

How could "highway-mpg" help us predict car price?

For this example, we want to look at how highway-mpg can help us predict car price. Using simple linear regression, we will create a linear function with "highway-mpg" as the predictor variable and the "price" as the response variable.

![image](https://user-images.githubusercontent.com/81119854/128061379-97e5ef14-5a8f-4612-a778-d72739c554be.png)

Fit the linear model using highway-mpg:

![image](https://user-images.githubusercontent.com/81119854/128061438-cf1f1bc7-da24-4f8d-bd33-560a8a666225.png)

We can output a prediction:

![image](https://user-images.githubusercontent.com/81119854/128061552-cb5f0e11-a80e-4f5f-99c0-c4188bc2d4c3.png)

What is the value of the intercept (a)?

![image](https://user-images.githubusercontent.com/81119854/128061656-2bc25fc7-3127-4f8c-ae83-21a2dc5f93c2.png)

What is the value of the slope (b)?

![image](https://user-images.githubusercontent.com/81119854/128061731-31ba643b-b74d-4bae-9436-28373a1f24a7.png)

What is the final estimated linear model we get?

As we saw above, we should get a final linear model with the structure:

![image](https://user-images.githubusercontent.com/81119854/128061816-6a865bcc-9ebf-46c1-b1ec-1fd7cf9accf6.png)

Plugging in the actual values we get:

Price = 38423.31 - 821.73 x highway-mpg

![image](https://user-images.githubusercontent.com/81119854/128062013-90e821a0-57a3-4374-9ef4-ddf5502cb1a8.png)

![image](https://user-images.githubusercontent.com/81119854/128062045-a297fe76-4ea8-489f-af46-5eb5f23ed366.png)

![image](https://user-images.githubusercontent.com/81119854/128062760-4cbf94bd-741c-4b42-a00e-c432aeeb8e04.png)

![image](https://user-images.githubusercontent.com/81119854/128062835-d94b971a-1ff0-4b01-8900-0bc4270efa7e.png)

![image](https://user-images.githubusercontent.com/81119854/128062904-11931095-1035-4caa-a6bc-4e76f31d0c98.png)

![image](https://user-images.githubusercontent.com/81119854/128062934-301a1a17-7355-48ef-8e3f-46d0d0d218f6.png)

![image](https://user-images.githubusercontent.com/81119854/128063254-83d7d5d1-6a9b-4fc8-9f36-8fa01daec1a2.png)

![image](https://user-images.githubusercontent.com/81119854/128063293-7897c5b8-e5ab-43c3-a725-c66d3dd86a79.png)

![image](https://user-images.githubusercontent.com/81119854/128069132-e9df01cf-f1a2-4bee-93e3-0d3cc6593438.png)

![image](https://user-images.githubusercontent.com/81119854/128069178-7f5b3dc1-e0cc-4ad6-93d9-b4d51073a030.png)

![image](https://user-images.githubusercontent.com/81119854/128069305-f7d11f66-9538-4234-b80b-61a61664f41b.png)

![image](https://user-images.githubusercontent.com/81119854/128069338-b0495ed1-ecb4-4c87-94da-27bca4a918a0.png)

2. Model Evaluation Using Visualization

Now that we've developed some models, how do we evaluate our models and choose the best one? One way to do this is by using a visualization.

Import the visualization package, seaborn:

![image](https://user-images.githubusercontent.com/81119854/128069430-a3dd9b57-2973-472d-936a-fa95477bf2f4.png)

When it comes to simple linear regression, an excellent way to visualize the fit of our model is by using regression plots.

This plot will show a combination of a scattered data points (a scatterplot), as well as the fitted linear regression line going through the data. This will give us a reasonable estimate of the relationship between the two variables, the strength of the correlation, as well as the direction (positive or negative correlation).

Let's visualize highway-mpg as potential predictor variable of price:

![image](https://user-images.githubusercontent.com/81119854/128069590-21d9998f-5809-48ea-8648-480d5ad9863e.png)

![image](https://user-images.githubusercontent.com/81119854/128069695-490bd165-7b14-4f33-9082-12c9c645196c.png)

We can see from this plot that price is negatively correlated to highway-mpg since the regression slope is negative.

One thing to keep in mind when looking at a regression plot is to pay attention to how scattered the data points are around the regression line. This will give you a good indication of the variance of the data and whether a linear model would be the best fit or not. If the data is too far off from the line, this linear model might not be the best model for this data.

Let's compare this plot to the regression plot of "peak-rpm".

![image](https://user-images.githubusercontent.com/81119854/128069887-37b0af9b-7d7d-4a37-83a6-40d03a7af568.png)

![image](https://user-images.githubusercontent.com/81119854/128069975-7049b58a-8f87-4d05-82e5-22bad179c038.png)

Comparing the regression plot of "peak-rpm" and "highway-mpg", we see that the points for "highway-mpg" are much closer to the generated line and, on average, decrease. The points for "peak-rpm" have more spread around the predicted line and it is much harder to determine if the points are decreasing or increasing as the "highway-mpg" increases.

![image](https://user-images.githubusercontent.com/81119854/128070136-f397b7e2-3c85-4482-948f-714718c593e1.png)

![image](https://user-images.githubusercontent.com/81119854/128070210-cb1b1d59-461b-42b8-bb7c-7f027e1320de.png)

Residual Plot

A good way to visualize the variance of the data is to use a residual plot.

What is a residual?

The difference between the observed value (y) and the predicted value (Yhat) is called the residual (e). When we look at a regression plot, the residual is the distance from the data point to the fitted regression line.

So what is a residual plot?

A residual plot is a graph that shows the residuals on the vertical y-axis and the independent variable on the horizontal x-axis.

What do we pay attention to when looking at a residual plot?

We look at the spread of the residuals:

- If the points in a residual plot are randomly spread out around the x-axis, then a linear model is appropriate for the data.

Why is that? Randomly spread out residuals means that the variance is constant, and thus the linear model is a good fit for this data.

![image](https://user-images.githubusercontent.com/81119854/128070657-2a012030-f9d1-48a9-97f0-dfcac98a72f2.png)

![image](https://user-images.githubusercontent.com/81119854/128070753-90590571-a45d-43f1-8d51-ab3d15e81df3.png)

What is this plot telling us?

We can see from this residual plot that the residuals are not randomly spread around the x-axis, leading us to believe that maybe a non-linear model is more appropriate for this data.

Multiple Linear Regression

How do we visualize a model for Multiple Linear Regression? This gets a bit more complicated because you can't visualize it with regression or residual plot.

One way to look at the fit of the model is by looking at the distribution plot. We can look at the distribution of the fitted values that result from the model and compare it to the distribution of the actual values.

First, let's make a prediction:

![image](https://user-images.githubusercontent.com/81119854/128071096-d74bed26-23c8-43ed-8c27-89827597bbbf.png)

![image](https://user-images.githubusercontent.com/81119854/128071193-be92b0f7-875f-4f3c-9e9b-16de24cf448b.png)

We can see that the fitted values are reasonably close to the actual values since the two distributions overlap a bit. However, there is definitely some room for improvement.

3. Polynomial Regression and Pipelines

Polynomial regression is a particular case of the general linear regression model or multiple linear regression models.

We get non-linear relationships by squaring or setting higher-order terms of the predictor variables.

There are different orders of polynomial regression:

![image](https://user-images.githubusercontent.com/81119854/128072442-9ea90a44-fe27-4065-88c9-9816d525fc2f.png)

We saw earlier that a linear model did not provide the best fit while using "highway-mpg" as the predictor variable. Let's see if we can try fitting a polynomial model to the data instead.

We will use the following function to plot the data:

![image](https://user-images.githubusercontent.com/81119854/128072633-4af5534e-221d-44ed-a551-f26c44b88b95.png)

![image](https://user-images.githubusercontent.com/81119854/128072681-16502604-e148-43b5-8b7b-80d5d71c9e59.png)

Let's fit the polynomial using the function polyfit, then use the function poly1d to display the polynomial function.

![image](https://user-images.githubusercontent.com/81119854/128072760-44eae5ec-13c0-4d73-85f0-82044623de68.png)

Let's plot the function:

![image](https://user-images.githubusercontent.com/81119854/128072905-2dae6a97-c276-4ce9-9d95-24383708cfda.png)

![image](https://user-images.githubusercontent.com/81119854/128072967-0b8dcf04-9c72-4140-b512-f699af078675.png)

We can already see from plotting that this polynomial model performs better than the linear model. This is because the generated polynomial function "hits" more of the data points.

![image](https://user-images.githubusercontent.com/81119854/128073068-fab28f6d-b3fb-4da1-b8ce-a78150df02fb.png)

![image](https://user-images.githubusercontent.com/81119854/128073272-098a189f-038d-48de-be57-881909ae53ef.png)

![image](https://user-images.githubusercontent.com/81119854/128073332-13b40c44-220b-4341-a1ef-f8d109b58f7b.png)

The analytical expression for Multivariate Polynomial function gets complicated. For example, the expression for a second-order (degree=2) polynomial with two variables is given by:

![image](https://user-images.githubusercontent.com/81119854/128073441-227c7ed3-e06e-4620-98b3-da09ba2f5675.png)

We can perform a polynomial transform on multiple features. First, we import the module:

We create a PolynomialFeatures object of degree 2:

![image](https://user-images.githubusercontent.com/81119854/128073560-ed29ec4a-a1b1-4bec-9936-8ccdd815e01f.png)

![image](https://user-images.githubusercontent.com/81119854/128073614-e9631c20-3040-4145-a386-256b25bb83be.png)

In the original data, there are 201 samples and 4 features.

![image](https://user-images.githubusercontent.com/81119854/128073792-7fe473d2-ab5d-4a53-b29b-0af1ef7420de.png)

After the transformation, there are 201 samples and 15 features.

![image](https://user-images.githubusercontent.com/81119854/128073855-55b0f390-96da-4a4d-9848-18a87d9efeaf.png)

Pipeline

Data Pipelines simplify the steps of processing the data. We use the module Pipeline to create a pipeline. We also use StandardScaler as a step in our pipeline.

![image](https://user-images.githubusercontent.com/81119854/128073949-946e94a6-d5fa-4cec-9515-df616b097b70.png)

We create the pipeline by creating a list of tuples including the name of the model or estimator and its corresponding constructor.

![image](https://user-images.githubusercontent.com/81119854/128074083-526e7b2f-e269-47db-be25-29825a175a04.png)

We input the list as an argument to the pipeline constructor:

![image](https://user-images.githubusercontent.com/81119854/128074248-ee4cceeb-f06c-45c4-bdb8-b589ccc295e7.png)

First, we convert the data type Z to type float to avoid conversion warnings that may appear as a result of StandardScaler taking float inputs.

Then, we can normalize the data, perform a transform and fit the model simultaneously.

![image](https://user-images.githubusercontent.com/81119854/128074913-6fdc32af-1ca8-4a6c-a432-e38605c74a93.png)

Similarly, we can normalize the data, perform a transform and produce a prediction simultaneously.

![image](https://user-images.githubusercontent.com/81119854/128074994-01bafa75-3506-4a67-920a-27f824334041.png)

![image](https://user-images.githubusercontent.com/81119854/128075113-ce7b3c4b-8eef-414f-9cac-132885154a54.png)

![image](https://user-images.githubusercontent.com/81119854/128075148-6fe04d56-a1d5-4c6a-b724-79257425d274.png)




