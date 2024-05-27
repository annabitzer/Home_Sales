# Home_Sales
In this activity, Spark SQL was used to query a Home Sales database to analyze data of home prices based on various features of the homes. Spark SQL was used to aggregate average prices by year the homes were built, and filter based on features such as number of bedrooms, number of bathrooms, and square footage. 

After performing the initial queries, Spark SQL was then used to cache and partition the data in parquet format to analyze the affect on query speed. The same query was run before and after the data was partitioned, and it actually ran slower after the partition. However, when looking at the query it became clear that the variable that was being partitioned into parquet format ("date_built") was not a relevant variable to the query that was being executed (which was grouped by "view"). If a query which grouped by or aggregated using "date_built" was run, it would be expected to run faster after partitioning by "date_built" vs before.