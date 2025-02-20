# Apriori Algorithm
# Association Rule Mining with Apriori Algorithm

## Overview
This R script applies **association rule mining** using the **Apriori algorithm** from the `arules` package. It defines a small set of **transactions**, converts them into a **transactions object**, and identifies **frequent itemsets** with a minimum support threshold of **50%**. The `apriori()` function is used to extract frequent itemsets, and the `inspect()` function displays the results.

## Key Features
- Uses the **Apriori algorithm** for market basket analysis.
- Converts transactional data into a structured format for processing.
- Extracts **frequent itemsets** using a specified **support threshold**.
- Displays results using `inspect()`, allowing for easy interpretation.
- Can be extended to generate **association rules** with confidence thresholds.

## Use Cases
- **Market Basket Analysis**: Identifying frequently bought items together.
- **Recommendation Systems**: Suggesting products based on purchasing patterns.
- **Retail Analytics**: Understanding customer buying behavior.

## Installation
Ensure you have the `arules` package installed in R:
```r
install.packages("arules")
```

## Usage
```r
library(arules)

# Define transactions
transactions <- list(
  c("A", "B", "C"),  # T1
  c("A", "C"),       # T2
  c("B", "C"),       # T3
  c("A", "D"),       # T4
  c("A", "C", "D")   # T5
)

# Convert to transactions object
trans <- as(transactions, "transactions")

# Run Apriori algorithm
frequent_itemsets <- apriori(trans, parameter = list(support = 0.5, target = "frequent itemsets"))

# View results
inspect(frequent_itemsets)
```
<img width="164" alt="image" src="https://github.com/user-attachments/assets/d1161674-3562-4113-ba63-44dec85f54dc" />


## Output
The output highlights the most commonly occurring **item combinations**, which can be used for further **market analysis** and **recommendation systems**.

## Further Analysis
To extract **association rules**, modify the `apriori()` function:
```r
association_rules <- apriori(trans, parameter = list(support = 0.5, confidence = 0.7, target = "rules"))
inspect(association_rules)
```

## License
This project is open-source and can be freely used and modified.

---

Feel free to contribute or report issues!
