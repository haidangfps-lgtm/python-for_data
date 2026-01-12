## 📅 Nhật ký học tập (Learning Log)

### Day 1: Automated read csv (multiple file csv) on website
Tự động hóa việc lấy dữ liệu bóng đá từ nhiều giải đấu/mùa giải.
Sử dụng: (Pandas `read_csv`), Loops, Dictionary Storage.
### Day 2: Conditional Logic & Feature Engineering
tạo cột mới, kết hợp nhiều điều kiện với nhau
Sử dụng: `np.where( 'dataframe' > condition, name1 , name2...)` 
, (`&`, `|`), 
`np.select` (Multi-condition Mapping):
danh sách điều kiện (`conditions list`) 
danh sách giá trị (`values list`). 
`np.where` (nested if-else).
 encoding='Latin1'
### Day 3: isin, get duplicate data in dataframe 
isin(['...','...']) find many conditions show condition by a list[]
duplicate() to get the duplicate in dataframe use [~duplicate] to get the non duplicate
+ keep = first
+ keep = last
+ false = we are not going to keep neither first duplicate value nor the last one
~ is not operator
drop_duplicates() remove duplicate element
+ ignore index, inplace : update dataframe
unique() to get unique element into a list 
nunique() to get number of unique the same with len function (excludes NA value)


