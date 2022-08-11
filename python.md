# Python


## Displaying full rows and columns

```

##Displaying max rows
pd.options.display.max_rows
pd.set_option('display.max_rows', None)

## Displaying max columns
pd.options.display.max_columns
pd.set_option('display.max_columns', None)

```

## Getting unique values

```
df['col'].unique()
```

## Getting column to list

```
df.columns.to_list()
```

## Checking null vaues

```
df.isnull()
```

Checking null values %

```
df.isnull().sum()*100/df.shape[0]
```

## Checking duplicate values

```
df.duplicated()
```
Checking duplicate values %

```
df.duplicated().sum()*100/df.shape[0]
```

##Drop column

```
data = data.drop(['col','id'],axis = 1)

```
