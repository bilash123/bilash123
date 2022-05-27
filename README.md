- 👋 Hi, I’m @bilash123
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
bilash123/bilash123 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# plots 


# we can find teh relationship between variable and the spread of a variable by many ways
# 1. base r
# 2. package called a ggplot


mat=matrix(data=1:9,nrow=3,ncol=3,byrow=TRUE)
mat
mat[3,2]

# different data type - is a list

# create a list having A vector,character,matrix
my_list=list(1:9,'sakshi',matrix(data=1:9,nrow =3,ncol = 3,byrow =TRUE))
my_list

# list has different object [[1]],[[2]],[[3]]

# inside the object,we have elements 


# we can name the object also


my_list=list(vec=1:9,char='sakshi',mat=matrix(data=1:9,nrow = 3,ncol = 3,byrow = TRUE))
my_list


# if we want to extract a particular vaiue inside the matrix,

my_list[[3]]


# extract 8 from the matrix 

my_list[[3]],[3,2]


# common way 

my_list$mat

my_list$char


my_list[['char']]

# generic function
# no of object in the list

length(my_list)


# contents of the list 

str(my_list)

# summary of the list 
summary(my_list)

# add a new objet in the list

my_list$new<-100

my_list


# delete an object in the list 

my_list$new <-NULL

my_list

list2<-list(10,'neha','riya')


# combine the my_list and the list2

# concatenate function


c(my_list,list2)


str(comb_list)


# list is heterrogeneous,so while loading data or running function,lists are created


# it servers as a building block for other Data Structers like DF

# table - dataframe in R 

# columns-variable names
# rows-observation



# created a df (dataframe)

# 3 vector 

name <-c('ram','sham','pooja')
age <-c(10,12,15)
marks <-c(100,199,200)


# combine these vector using data.frame
df1<-data.frame(name,age,marks)

df1

# column

colname(df1)

row.name(df1)

# pass the row names 
df1<-data.frame(name,age,marks,row.names=c('r1','r2','r3'))

df1

help("data.frame")

# in a from or csv or xlsx from

# import it in R as a data frame 

read.csv()

# import a csv file in labs


# 1. uplode the file o the server 

# 2. read.csv('location of the file/filename.csv)


# working directory-where the files are stored

# more tab>> set as working directory

# check the working directory
getwd()


setwd('/home/labsuser/folder-name')

car<-read.csv('/home/labsuser/May 22/CARS.csv')

car

# tabubr from 

View(car)


View(car)

# get the first 6 rows

head(car)

head(car)

# structer of the data frame 
srt(car)

vec <-c('male','female','male','female')
vec

fact_gen <-as.factor(vec)

fact_gen

# factor - avariable used to categorise and store the data as levels 


# when r gets character data,it stores as factor 

# to prevent this 

car<-read.csv('/home/labsuser/May 22/CARS.csv',stringsAsFactors =FALSE)

str(car)

# no of rows of the df nrow(car)

# no of the columns 
ncol(car)

# share 
dim(car)


# summary of the data frame 

summary(car)

# last few rows

tail(car,5)

# 2nd row,2nd col
# by the location of the index

car[2,2]

# by the name of the index 
car[1,'model']


# get the entire rows and the variale model-vector output 

char['model']


car[,2]


# common way is to use $
cat$model


# get the 20th row in model column

car$model[20]


# boolean indexing

# get all the cars satifying a condition like wt>4000

# take a vector
v1 <-c(10,20,100)
v1

# whereever the value is TRUE,than that is returned


v1[c(TRUE,TRUE,FALSE)]


V1>50

V1[C(FALSE,FALSE,TRUE)]

# just substitute the condition

v1[v1>50]
car$weight>4000

# model names and the et of the car>4000


car[car$weight>4000,c('model','weight')]

# get the weight,mode,hp of the cars where wt>4000 and hp>300


car[car$weight>4500 & car$Horsepower>300,c('Model','Weight','Horsepower')]

g-and
-or


# dont use gg and || - these are logical operator 


# extracted rows and columns by base R 


# packages in r -
installed.packages()


# install a package


install.packages('name_of_package')
yes


# after instaling a package,we need to load in the R memory


# library('package_name')


# dplyr - data manipulation using r 


# datasets which are preloaded

data()


View(mtcars)

# copy the mtcars dataset into a new dataframe -df

df<-mtcars

help(mtcars)


# use base r to perfrom the operation and then use dplyr

library('dplyr')


# get all the package which are loaded 


search()




# select mpg and wt 
df[,c('mpg','wt')]

# select-columns

# select(dataframe,col1,col2,...)


select(df,mpg,wt)

# select all variables staring with 'm'

select(df,starts_with('m'))


# select all variable ending with 't' 
select(df,ends_with('t'))


# all columns containing 'a'
select(df,contains('a'))


# get the wt column first and all other colunmns in the same order 


df<-select(df,wt,everything())


# extract the rows based on a condition

# get all cars wt>4.5

df$wt>4.5


# in dplyr we have a function,filter


# filter will extrac the rows which satisfy a given codition


# filter(data,condition)

filter(df,wt>4.5)

# apply multiple condition

# get the cars where wt>4500 and hp>300


car[car$Weight>4500&car$Horsepower>300]
car
car


filter(car,weight>4500,Horsepower>300)
filter(car,weight>4500&Horsepower>300)

# or condition


filter(car,Weight>4500|Horsepower>300)

# mtcars dataset,we want mpg>20 and wt>3,only the mpg and wt


data<-filter(df,wt>3&mpg>20)
select(data,mpg,wt)


select(filter(df,wt>3&mpg>20),mpg,wt)


# suppose we have nested function,f1(f2(f3(x)))

f3>f2>f1


filter(select(df,wt,mpg),wt>3,mpg>20)


# pipe oprator

%>%-pipe-ctrl+shift+m

%>%

# sequence of the oprations 
  
# suppose we have nested function f1(f2(f3(x)))
  
  
  f3(x)%%f2(x)%>%f1(x)

sqrt(16+9)


(16+9) %>% sqrt()

# mtcars dataset,we want mpg>20 and wt >3,only the mpg and wt

df%%filter(mpg>20,wt>3)%>% select(mpg,wt)


# Group By functionality
car %>% group_by(Type)




# spit the data frame by the  distinct value of group by 
# apply the function on the column
# combine the result


# average wt of cars y type - summarise

car%>%group_by(Type)%>%summarise(avg_wt=mean(Weight))

data()

# average wt of cars by type and the max hp

car%>%group_by(type)%>%summarise(avgwt=mean(weight),maxhp=max(Horsepower))

# short the row based a column like dac wt 

car%>%arrange(weight)



# short the rows based on a column like  dese wt

car%>%arrange(dase(weight))


# create new variables

# mutate

# new_wt=10% increase over at 

car%>%mutate(new_wt=1.1*weight)

head(car)


# we can also use the base r mthod 
car$new_wt<-car$weight *1.1

select the variable - select

select the rows satisfying a candition-filter

group_by


arrange-sorting


mutate-mainpulating variable
