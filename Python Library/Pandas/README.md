# Pandas
A library to work on tabular data. To store data in the form of table. 

### Install


```python
!pip install pandas
```

    Requirement already satisfied: pandas in c:\programdata\anaconda3\lib\site-packages (0.25.1)
    Requirement already satisfied: numpy>=1.13.3 in c:\programdata\anaconda3\lib\site-packages (from pandas) (1.16.5)
    Requirement already satisfied: python-dateutil>=2.6.1 in c:\programdata\anaconda3\lib\site-packages (from pandas) (2.8.0)
    Requirement already satisfied: pytz>=2017.2 in c:\programdata\anaconda3\lib\site-packages (from pandas) (2019.3)
    Requirement already satisfied: six>=1.5 in c:\programdata\anaconda3\lib\site-packages (from python-dateutil>=2.6.1->pandas) (1.12.0)
    


```python
import numpy as np
import pandas as pd
```

##### Create a data frame


```python
user_data ={
    "MarksA":np.random.randint(10,100,5),
    "MarksB":np.random.randint(10,100,5),
    "MarksC":np.random.randint(10,100,5)
}

print(user_data)
```

    {'MarksA': array([63, 23, 64, 73, 87]), 'MarksB': array([94, 83, 61, 22, 31]), 'MarksC': array([91, 76, 54, 98, 77])}
    


```python
np.random.randint(10,100,5)
```




    array([18, 88, 34, 11, 85])



## Suppose i want to create table 


```python
df = pd.DataFrame(user_data)
print(df)
```

       MarksA  MarksB  MarksC
    0      63      94      91
    1      23      83      76
    2      64      61      54
    3      73      22      98
    4      87      31      77
    


```python
#TO display in better way
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>73</td>
      <td>22</td>
      <td>98</td>
    </tr>
    <tr>
      <td>4</td>
      <td>87</td>
      <td>31</td>
      <td>77</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Display particular n
df.head(n=3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
#To get the columns
df.columns
```




    Index(['MarksA', 'MarksB', 'MarksC'], dtype='object')



### To Export Data Into CSV Files


```python
#To export the csv file
#df.to_csv('filename.csv')
df.to_csv('marks.csv')
```


```python
my_data = pd.read_csv('marks.csv')
```


```python
print(my_data)
```

       Unnamed: 0  MarksA  MarksB  MarksC
    0           0      63      94      91
    1           1      23      83      76
    2           2      64      61      54
    3           3      73      22      98
    4           4      87      31      77
    


```python
#i dont need the first columns
my_data = my_data.drop(columns=['Unnamed: 0'] )
print(my_data)
```

       MarksA  MarksB  MarksC
    0      63      94      91
    1      23      83      76
    2      64      61      54
    3      73      22      98
    4      87      31      77
    

### To get Statistic of Data


```python
my_data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>5.000000</td>
      <td>5.0000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>62.000000</td>
      <td>58.2000</td>
      <td>79.200000</td>
    </tr>
    <tr>
      <td>std</td>
      <td>23.832751</td>
      <td>31.4436</td>
      <td>16.902663</td>
    </tr>
    <tr>
      <td>min</td>
      <td>23.000000</td>
      <td>22.0000</td>
      <td>54.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>63.000000</td>
      <td>31.0000</td>
      <td>76.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>64.000000</td>
      <td>61.0000</td>
      <td>77.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>73.000000</td>
      <td>83.0000</td>
      <td>91.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>87.000000</td>
      <td>94.0000</td>
      <td>98.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Last 5 rows
my_data.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>73</td>
      <td>22</td>
      <td>98</td>
    </tr>
    <tr>
      <td>4</td>
      <td>87</td>
      <td>31</td>
      <td>77</td>
    </tr>
  </tbody>
</table>
</div>




```python
#To get particular Row
df.iloc[3]
```




    MarksA    73
    MarksB    22
    MarksC    98
    Name: 3, dtype: int32




```python
#To get particular row & col
df.iloc[3,1]
```




    22




```python
df.iloc[3][1]
```




    22




```python
#to get index of columns
idx = [df.columns.get_loc('MarksB'),df.columns.get_loc('MarksC')]
print(idx)
# In 3rd row for 1st and 2nd col
df.iloc[3,idx]
```

    [1, 2]
    




    MarksB    22
    MarksC    98
    Name: 3, dtype: int32




```python
#take the first 3 rows and col 1&2
df.iloc[:3,idx]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>61</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[:3,[1,2]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>61</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
##Sort your data frame on basis of marks

my_data.sort_values(by=["MarksA"],ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>4</td>
      <td>87</td>
      <td>31</td>
      <td>77</td>
    </tr>
    <tr>
      <td>3</td>
      <td>73</td>
      <td>22</td>
      <td>98</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
  </tbody>
</table>
</div>




```python
my_data.sort_values(by=["MarksA"],ascending=True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>73</td>
      <td>22</td>
      <td>98</td>
    </tr>
    <tr>
      <td>4</td>
      <td>87</td>
      <td>31</td>
      <td>77</td>
    </tr>
  </tbody>
</table>
</div>




```python
#One with highest marks in c then in A
my_data.sort_values(by=["MarksC","MarksA"],ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>MarksA</th>
      <th>MarksB</th>
      <th>MarksC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3</td>
      <td>73</td>
      <td>22</td>
      <td>98</td>
    </tr>
    <tr>
      <td>0</td>
      <td>63</td>
      <td>94</td>
      <td>91</td>
    </tr>
    <tr>
      <td>4</td>
      <td>87</td>
      <td>31</td>
      <td>77</td>
    </tr>
    <tr>
      <td>1</td>
      <td>23</td>
      <td>83</td>
      <td>76</td>
    </tr>
    <tr>
      <td>2</td>
      <td>64</td>
      <td>61</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>



## Pandas Into Numpy Arrays


```python
data_array = my_data.values
```


```python
print(type(my_data))
print(my_data.shape)
```

    <class 'pandas.core.frame.DataFrame'>
    (5, 3)
    


```python
print(data_array)
print(type(data_array))
print(data_array.shape)
```

    [[63 94 91]
     [23 83 76]
     [64 61 54]
     [73 22 98]
     [87 31 77]]
    <class 'numpy.ndarray'>
    (5, 3)
    

## Numpy Arrays Back Into Data Frame


```python
new_df = pd.DataFrame(data_array,dtype='int32',columns=["Physics","Chemistry","Maths"])
```


```python
print(new_df)
```

       Physics  Chemistry  Maths
    0       63         94     91
    1       23         83     76
    2       64         61     54
    3       73         22     98
    4       87         31     77
    


```python
new_df.to_csv("PCM.csv",index=False)
```


```python
#to read documentation
#new_df.to_csv?
```


```python
pcm = pd.read_csv('PCM.csv')
```


```python
print(pcm)
```

       Physics  Chemistry  Maths
    0       63         94     91
    1       23         83     76
    2       64         61     54
    3       73         22     98
    4       87         31     77
    


```python
import pandas as pd 
import matplotlib.pyplot as plt 
  
# create 2D array of table given above 
data = [['E001', 'M', 34, 123, 'Normal', 350], 
        ['E002', 'F', 40, 114, 'Overweight', 450], 
        ['E003', 'F', 37, 135, 'Obesity', 169], 
        ['E004', 'M', 30, 139, 'Underweight', 189], 
        ['E005', 'F', 44, 117, 'Underweight', 183], 
        ['E006', 'M', 36, 121, 'Normal', 80], 
        ['E007', 'M', 32, 133, 'Obesity', 166], 
        ['E008', 'F', 26, 140, 'Normal', 120], 
        ['E009', 'M', 32, 133, 'Normal', 75], 
        ['E010', 'M', 36, 133, 'Underweight', 40] ] 
  
# dataframe created with 
# the above data array 
df = pd.DataFrame(data, columns = ['EMPID', 'Gender',  
                                    'Age', 'Sales', 
                                    'BMI', 'Income'] ) 
print(df)
  
# create histogram for numeric data 
df.hist() 
  
# show plot 
plt.show() 
```

      EMPID Gender  Age  Sales          BMI  Income
    0  E001      M   34    123       Normal     350
    1  E002      F   40    114   Overweight     450
    2  E003      F   37    135      Obesity     169
    3  E004      M   30    139  Underweight     189
    4  E005      F   44    117  Underweight     183
    5  E006      M   36    121       Normal      80
    6  E007      M   32    133      Obesity     166
    7  E008      F   26    140       Normal     120
    8  E009      M   32    133       Normal      75
    9  E010      M   36    133  Underweight      40
    


    <Figure size 640x480 with 4 Axes>



```python

```
