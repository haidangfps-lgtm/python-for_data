## 📅 Nhật ký học tập (Learning Log)

### Day 1: Automated read csv (multiple file csv) on website
- Tự động hóa việc lấy dữ liệu bóng đá từ nhiều giải đấu/mùa giải. 
- (Pandas `read_csv`), Loops, Dictionary Storage. (encoding='Latin1')
# PRJ 1 Learn filtering, extract, resharp, pivot dataframe
### Day 2: Conditional Logic & Feature Engineering
- tạo cột mới, kết hợp nhiều điều kiện với nhau
   + np.where( 'dataframe' > condition, name1 , name2...)
   + (`&`, `|`), 
   + np.select (Multi-condition Mapping)
### Day 3: isin, get duplicate data in dataframe 
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
### Day 4 select data 2 methods
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
### Day 5 
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
### Day 6 resharping table
- pivot() (reshape dataframe to get a different view to have a better analysis)
  + df.pivot(index=, columns=, values=)
- pivot_tale() (have aggreate function)
  + df.pivot_table(index =,column,values, aggfunc = )
