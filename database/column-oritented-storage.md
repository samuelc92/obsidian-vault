It doesn't store all the values from one row together, but store all the value from each column together instead. If each column is stored in a separate file, a query only need to read and parse those columns that are used in that query which can save a lot of work.

| data_key | product_sk  | store_sk |
| -------- | ----------- | -------- |
| 140102   | 69          | 4        |
| 140102   | 69          | 5        |
| 140103   | 74          | 3        |

Column storage layout:

data_key file contents: 140102, 140102, 140103
product_sk file contents: 69, 69, 74
store_sk file contents: 4, 5, 3


