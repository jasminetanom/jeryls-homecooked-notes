# importance of pandas
slicing: loc , iloc, ix
fucntions: info, describe, isnull .. ..

ETL: extract, transform, load
json: python dictionary

# Databases
1. SQL rows and column, pri and second key, relational db mgment system
2. no SQL databases: mongodb, operate based on documents.
document = json eg. collection of documents
3. graph database: neo4j super relational. store as network
querying is cypher

outputing: 
- package to parse noSQL from pandas
- output direct to SQL
- CANNOT neo4j

# pd.read_csv converts csv into df

# head(), tail()
df.head() returns first 5 rows
df.tail()
reports columns

can use df[col].head() df[col] is a panda series 

# attributes
.shape is a attribute, no ()
.columns

# dataframe
Panda is a dataframe containing series(cols)
df[col] is series
df[[col]] is a dataframe, useful to extract > 1 cols

df.col = df['col']

#  loc, iloc, ix
indexing (row, column)
loc: label, iloc: index

new_index_values = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q']
drug.index = new_index_values

# create index for df
drug.index = drug['age']

drug.head()

OR reset index
drug.reset_index(drop=True, inplace=True)
drug.head()

empty cell always above index

# Creating df
mydata = pd.DataFrame({'Letters':['A','B','C'], 'Integers':[1,2,3], 'Floats':[2.2, 3.3, 4.4]})

key= column
value= rows

# Changing column names
mydata.rename(columns={mydata.columns[1]:'int'}, inplace=True) # inplace = True updates mydata
print(mydata.columns)

# Important panda methods
1. df.info(): missing values, unexpected types, dirty data(commas $), blank nonull characters
> investigate objects, cast to particular dtype

2. df.describe(): descriptive stats on dataframe / series

3. df.mean(): mean of every column


# Plotting in python
import matplotlib.pyplot as plt

%matplotlib inline

use df.plot()
df.hist() - hist of 1 COLUMN

# Filter logic
drug[drug['marijuana-use'] > 20]
drug[(drug['marijuana-use'] > 20) & (drug.n > 4000)]

return(drug columns which fulfill true)

# Flowchat
1. info
2. describe
3. consider objects, null values. check all columns have same no. of rows
4. converting non-null into null and change value / drop rows


# Data cleaning

- Format errors
- clean nulls
- impute nulls, impute a missing value, vis insert which is add
- imputed values: median(column)
if > 30% of column is empty, dont use col!
- Forward fill, backward fill (* sort dependent)
- type differences
- exact duplicates

# Strats

    - Remove missing values.
    - Remove incorrect values.
    - Update incorrect values.
        -Removing invalid characters.
        -Truncating part of a value.
        -Adding an extra numeral or string-based data.
    - Imputate missing or invalid data.
        -Calculating the mean/median/mode of a column, sometimes within group subsets.
        -Implementing model-based imputation (K-Nearest Neighbors, MICE, etc.).
    - Backfill or forward fill.


# Feature selection
- keep feature with higher variance, 
- drop those with lower relative variance (one dataset)

# panda object dtypes
The main data types in pandas objects are:

    float
    int
    bool
    datetime64
    timedelta
    category
    object

# functions
.apply() : applies function to DATAFRAME
.map(): applies function to elements in series
.value_counts()

dft.get_dtype_counts().astype(list) - number of cols of each type


df.apply(np.mean, axis=0) , column, axis=1 is row

chrisalbon.com

# Red Flags
.info shows that particular column not full entries
uniquee values : remove nan and weird non-dtype entries

