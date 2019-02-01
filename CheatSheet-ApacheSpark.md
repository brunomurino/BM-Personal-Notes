# Spark

## Show list of columns in a dataframe
```python
df.columns
```

## Show number of rows in a dataframe
```python
df.count()
```

## Trim column names
```python
for col in df.columns:
    df = df.withColumnRenamed(col, col.strip())
```

## Change column data type
```python

for col in df.columns:
    if col = 'source':
        continue
    df = df.withColumn(col, df[col].cast('double'))

df = df.withColumn("my_column", df["my_column"].cast('new_data_type'))
```

## Spark to Pandas
```python
pandas_df = spark_df.toPandas()
```

## Pandas to Spark
```python
spark_df = createDataFrame(pandas_df)
```

## Drop column from dataframe
As argument, it supports: a Column to drop, or a list of string name of the columns to drop.
```python
new_df = df.drop("col1", "col2")
new_df = df.drop.col1
new_df = df.drop.col2
```

## Remove thousand's coma from spark (string) column
```python
df = df.withColumn("my_col",regexp_replace(df["my_col"], "[^0-9]", ""))
```

The term `"[^0-9]"` selects any character that is not a number from 0 to 9, so it keeps only the numbers. This is useful then removing `$` from currencies, for example. To just remove comas the following is simpler:
```python
df = df.withColumn("my_col",regexp_replace(df["my_col"], ",", ""))
```
A good guide on Regular Expressions is [this](https://medium.com/tech-tajawal/regular-expressions-the-last-guide-6800283ac034).




