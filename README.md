## 📅 Nhật ký học tập (Learning Log)

### Automated read csv (multiple file csv) on website
- Tự động hóa việc lấy dữ liệu bóng đá từ nhiều giải đấu/mùa giải. 
- pd.Dataframe({ : ,  : }) to create a dataframe
- (Pandas `read_csv`), Loops, Dictionary Storage. (encoding='Latin1')
# PRJ 1 Learn filtering, extract, resharp, pivot dataframe
### Conditional Logic & Feature Engineering
- tạo cột mới, kết hợp nhiều điều kiện với nhau
   + np.where( 'dataframe' > condition, name1 , name2...)
   + (`&`, `|`), 
   + np.select (Multi-condition Mapping)
### isin, get duplicate data in dataframe 
- isin(['...','...']) find many conditions show condition by a list[]
- duplicate() to get the duplicate in dataframe use [~duplicate] to get the non duplicate
   + keep = first
   + keep = last
   + false = we are not going to keep neither first duplicate value nor the last one
- ~ is not operator
- drop_duplicates() remove duplicate element
- ignore index, inplace : update dataframe
- unique() to get unique element into a list 
- nunique() to get number of unique the same with len function (excludes NA value)
### select data 2 methods
- select method to get data we want
  + loc['rowlabel','column'] (label)
  + iloc[number, :] (position)
- .set_index() to set the column into an index in dataframe
- df[['...']] select many columns (copy table)
- .index[] to get top in dataframe 
  + update data .loc[] = ... set new value 
  + np.nan convert data into NaN 
- Two method to drop columns or rows
  + axis 0 : column , 1 : row .drop([...], axis = ...,)
  + parameter (index = [...]) (columns = [...])
- .drop(index = [...], )
### sample datafranem,filter with .query, convert df lambda
- sample.()
  + .sample(10, #random_state = 36)
  + extract 20% sample of df
    + df.sample(frac = 0.2, random_state)
    + if frac > 1 : increasing sample dataframe (Note: replace parameter has to be True)
- filter data with .query()
we have 2 ways to select and filter
  + .query("label > condition")
  ('not(label > condition)')
  + df[df["lable"] > condition]
  df[~(df['label'] > condition)]
- convert type
  + .dtypes() to check out dataframe types
  + .astype() to convert
    + df[] = df[].astype()
    + df[].dt.year to convert all to year only
- .apply() apply method
  + apply function ,operation df.apply(test, axis = 1)
  + ** 2 = binh`phuong
- lambda function
  + lambda_function = lambda x:action for x
  + .apply(lambda x:...) (when manipulate dataframe with lambda we must use with .apply(lambda x:...) )
  +   df['long_name'].str.upper() (we have to use  str (attribute) therefor lambda is more convenience)
- .copy() will not reflect 
  three ways to copy
  + df0 = df.copy() (deep = true) then not reflected on copy df
  + df1 = df.copy(deep = false) will be reflected with the original df
  + df2 = df (exactly the same with deep = true)
### resharping table
- pivot() (reshape dataframe to get a different view to have a better analysis)
  + df.pivot(index=, columns=, values=)
- pivot_tale() (have aggreate function)
  + df.pivot_table(index =,column,values, aggfunc = )
# project 2 Visualization 
- dropna() (drop null values)
- .plot(kind = line/bar/pie/box/hist/scatter, color, xlable, ylable, title, figsize=(x,y)) (visualization)
- index.isin() single/multi to find variables barplot
- df.T (**transpose** / pivot single index)
- to_excel('name file') exported file to excel
- import matplotlib.pyplot as plt (libraly use to manage plot)
- plt.savefig() / plt.show()
- df.iplot() to interact with plot
### aggreate function groupby
* numeric_only = True to select only number in df
- .agg('function')
- different agg percolumn have to  create a dict .agg({['':','],[]})
  + we can also agg over the column
- set index for agg .agg(x = (), y = ())

- .groupby('column', asindex = False, dropna = ...).sum()     False not drop null value in your groupby 
- .groups to group attribute and key  - .groups.keys() to take the key
- .get_group() to take the group 

- isnull().sum()  to find  null values
- .filter() + def
### concatenate, merging dataframe
- pd.concat()  (axis = 0 to concat vertically // 1 to horizontally)
- df1.merge(df2, on = , how = inner / outer / left) to join 2 df  (like sql inner join is default)
  + we can also use pd.merge(df1,df2,on) the same result with method 1
  + indicator = True: take the _merge column (exclutive join) that indicate the data where it's in 
    + use .query(_merge = left or .. to take that data where it's belonging to)
### regular expression (import re.) re to search and findall digits
- re.findall(r'', df) , re.search(r'', df)
- \d digit
- \D no digit
- \w word character
- \W not word character
- \s the blank space
- \s not blank space (take all except space)
- . take all character except new line
- \ ignore any character
- ^ take beginning of a string 
- $ to take the end of a stringb
- () group 
- {} to take the number {3,6}
- [] matches characters in range a-z 1-5   [^ ] to take matches is not in the range
- |   (9|8) \d{2} to find 9 or 8 following by two digits
- \b word boundary
- \1 reference   (123-)\1\1 to take many times 123- instead of write many times 123-
#### Quantifiers
- * 0 or more character
- + 1 or more character
- ? 0 or 1 character
- {n} extract number character !{n}
- {n, } to take all, {3,4} range of the number
# project 3 Cleaning dataframe
### cleaning
- .mode to take the mean but that is the string in df
- backward, forward
- backward, forward
  + df.fillna(method='bfill') ,df.fillna(method='ffill')
- change string to upper, lower, title
  + df[].str.lower()
  + df[].apply(lambda x : x.upper())
- removeblank space with strip(), lstrip(), rstrip()
  + strip() to trip all blank
  + rstrip() to strip right side 
  + lstrip() to strip left side
- replace(), sub() to replace string 
  +difference between str.replace() and replace()
      + str.replace(): perform string or regex substitution on string data.
      + replace():  can replace any type of data
### Machine learning
- import statsmodels.api, fr sklearn import linear_moodel,  seaborn, matplotlib.pyplot
- Liner regression hoi quy tuyen tinh EQUATION = y = ax+b 
  + define dependent or independent variable (OLS stand for ordinary list square to estimate liner regression)
  + .add_constant() add independent variable
  +  .OLS(variable).fit(x,y) (x = dependent, y = indepentdent) , .predict(), .summary()
  + plotting the line
    + plt.figure(tight_layout = True)
    + sns.scatterplot(x, y, data = df)
    + sns.lineplot(x,y,data, color)
    + plt.savefig(..) to plt.show
  +  with linear_model we dont need add constant
    + linear_model.LinearRegression() show array
    + lm.score(X,y), lm.coef, lm.intercept_
# project 4 binary text classification
- !pip install imblearn To blance data automatically (sklearn, imblearn)
  + from imblearn.under_sampling  import RandomUnderSample
    + RandomUnderSampler(random_state = 0)
    + .fit_sample(df[[]] (to get output), series) (two elements)
  + from imblearn.model_selection import train_test_split
    + train, test = train_test_split(df, test_size, random_state)
- Bag of words order (BoW) is count vectorizer
  + from sklearn.feature_extraction.text import CountVectorizer
    + CountVectorizer(stop_word = 'english')
    + .fit_transform
- TF term frequency is number of time word appear
- IDF
  + from sklearn.feature_extraction.text import TfidfVectorizer
    + tfidf.fit_transform
- from sklearn.svm import SVC (support vector machines)
  + svc = SVC(kernel='linear')
- from sklearn.tree import DecisionTreeClassifier
- from sklearn.naive_bayes import GaussianNB
- from sklearn.linear_model import LogisticRegression
- from sklearn.metrics import confusion_matrix
- mean accuracy
  + model.score(test_x_vector, test_y)
- from sklearn.metrics import f1_score
- from sklearn.metrics import classification_report
- tuning the model maximize model performance
  + from sklearn.model_selection import GridSearchCV
    + svc = SVC()
    + svc_grid = GridSearchCV(svc, parameters, cv=5)