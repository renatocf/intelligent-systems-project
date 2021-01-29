# Data

For this project, we will use data from an [open source dataset][1]
made by [Elo7][2], the largest online handcrafts marketplace in Brazil.
It contains data based on Elo7's search engine usage.

For the first part of this project, sample data is available in a
[CSV][3] file named `sample_producs.csv`. It contains a **header**
and **38k rows**.

For the second part of this project, test data is available in a
[CSV][3] file named `test_producs.csv`. It contains a **header**
and **500 rows**.

The fields composing each row are specified in the table below:

| **Field**           | **Description**                                                                              |
| ------------------- | -------------------------------------------------------------------------------------------- |
| `product_id`        | Product numeric identification                                                               |
| `seller_id`         | Seller numeric identification                                                                |
| `query`             | The text inserted by users                                                                   |
| `search_page`       | The page number the product appeared (min 1 and max 5)                                       |
| `position`          | The position the product appeared in the search page (min 0 and max 38)                      |
| `title`             | Product title                                                                                |
| `concatenated_tags` | Product tags inserted by the seller                                                          |
| `creation_date`     | The date of product registration in Elo7 platform                                            |
| `price`             | The product price (R$)                                                                       |
| `weight`            | The weight (grams) of a product unit                                                         |
| `express_delivery`  | Indicates if the product has already been made (1) or not (0)                                |
| `minimum_quantity`  | The minimum quantity the seller sells the product                                            |
| `view_counts`       | The number of times the product was clicked in the last three months                         |
| `order_counts`      | The number of times the product was purchased in the last three months                       |
| `category`          | Product category                                                                             |

[1]: https://github.com/elo7/data7_oss/tree/master/elo7-search
[2]: https://elo7.com.br/sobre
[3]: https://en.wikipedia.org/wiki/Comma-separated_values
