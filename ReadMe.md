# Strobes and More Master SKU List Report
### Master_SKU_list – Notes:
- Length of DataFrame: 279,997 rows
- Columns: ['CatalogID', 'ProductID', 'SKU', 'Name', 'Labels']

Column descriptions are as follows:
`CatalogID` – The unique Identifier to each product
`ProductID` - The root SKU to every product
- SKU - The unique SKU to every combination of options within the website
- Name – Name of the product
- Labels – The partnumber names that go with each combination of SKUs, joined by an
underscore
#### Data was requested from the Shift4Shop API, aggregated and prepped for coding process.
#### Coding process: The description of the functions used to create the SKUs are below. Please
ask if you have any questions.
-----Functions used to create SKUs:
1) get_tuples_for_all_categories, get_tuples_for_all_labels:
These functions get us the partnumbers and featurenames for all the categories associated with
each product. The function returns tuples of the partnumber and the sorting number, which in
theory is how the partnumbers should be ordered for the SKUs.
2) generate_combinations:
The combination function generates all combinations of the partnumbers, with consideration of
order using the 'sorting' column from the dataframe. The functions creates lists of all the possible
outcomes and then returns the largest list as some sets of SKUs come out with 1, 2, or 3
options(more options can be added to the function if need be).
3) create_combo_dataframe:
This is the function that puts all these parts together. It iterates through the dataframe and gets all
the labels, partnumbers, and combinations and then appends them to a new dataframe composed
of the catalogid, productid, the SKU, and the description of the SKU.

#### Checks: Manual SKUs
Some of the SKUs were inaccurately ordered according to the website. These were:
CatalogIDs: 3483, 4136,4311, 4413, 6174
Checks were made against the website to get correct ordering. For the last 4 catalogids, the issue
was partnumbers for car models(?) were listed as a second order instead of third. An example is
‘MKEZ94’. If possible, I recommend an overwrite in the API to fix future inventory problems.

#### Finished with general data cleaning, and length/null checks.

#### Products Omitted from dataframe:
There were several products that had up to 20 billion combinations due to the number of options
and option choices. These were omitted from the dataframe.

#### Options not on website/for sale:
Products that were not seen from the viewer side on the website were separated for inventory
purposes in a different csv. (SKUs_offWebsite.csv). These are kept for records but no SKUs
were generated in the Master SKU list. In the API these products were listed as “Hidden” or
“NotForSale”

#### Columns to CSV: [‘CatalogID’,’SKU’]
- CatalogID – The unique Identifier to each product
- ProductID - The root SKU to every product

#### Questions/Contact Me:
- 631-252-1859
- Alevinton151@gmail.com


```python

```
