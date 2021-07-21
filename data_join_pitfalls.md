# Overview
  * Joining data tables can give meaningful insights, but there are some pitfalls that we need to be mindful of. Here are types of joins (for more information, check [here](https://docs.trifacta.com/display/DP/Join+Window)):
      1. *Cross join*: combines each row of the first dataset with each row of the second dataset, where every combination is represented in the output
      2. *Inner join*: requires the key values exist in both tables for the records to appear in the results table. Records appear in the merge only if there are matches in both tables for the key values.
      3. *Left join*: Each row in the left table appears in the results, regardless of whether there are matches in the right table.
      4. *Right join*: the reverse of a left join. Each row in the right table appears in the results, regardless of whether there are mathces in the left table.
