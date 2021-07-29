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

