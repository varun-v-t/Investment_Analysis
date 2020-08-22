# Investment Analysis
## Business problem:
* Spark funds wants to invest in companies depending upon global trends in investments.
* Few of the Inputs/constraints given by asset management company “Spark Funds” are
* Wants to invest where most of the other investors are investing
* Wants to invest between 5 to15Million USD per round
* Wants to Invest in English speaking countries
## Objective:
* Identify most suitable Investment type , best sectors and countries for making investments keeping in mind the
constraints given by the client
* Suggest few companies for the chosen investment type that are present in top sectors for each of the top countries.

# Problem solving methodology
1. Load companies and rounds CrunchBase dataset with encoding ‘ISO-8859-1’
2. Encode with ascii ignoring errors and decode with ascii to make dataset readable.
3. Remove the Null/zero values in category list and raised amount columns.
4. Remove few outliers from raised amount.
5. Analyze angel, venture, seed, and private equity funding types vs raised amount.
6. Choose the one which is the most suitable for client
7. Analyze the amount of investment in top 9 English speaking countries for the chosen funding type .
8. Pick the top 3 countries among them
9. Load and Correct typos in mapping dataset
10. Extract primary sector from category list, map the the main sector from the mapping dataset to the corresponding primary
sector and remove not found main sectors records.
11. Analyze the sectors where most investment is done and select top 3 sectors.
12. Analyze the investments in top 3 sectors in each top 3 countries
13. Plot the analysis done above

# Funding type Analysis
## Assumptions made
* Analysing the variations in raised amount(target variable), found few outliers
* Removed outliers where raised amount is more than 1000 million USD.
* Zero valued investments removed since the results will be skewed towards lower end and zeroed value investment is of not
use.
* Did not remove investments outside of IQR as many useful records will be removed.
* Only angel, venture, seed, and private equity funding types were used for analysis as its more suitable for early stage
investors.
* Analysis Outcomes
* Average amount of investments were calculated for each of the four funding types
* Average amount for private equity is 60.8M, venture is 11.10M, angel is 0.96M and seed is 0.72M USD
* Venture is the only funding type having average investment between 5-15M USD.
* Venture was the only one having median amount of investment in 5-15M USD range.
* Hence Venture

# Country analysis
## Assumptions
* Only amounts between 5-15M considered
* Analyse the countries where most amount investment is done between 5-15M USD for Venture Funding
* Choose the top 9 countries
* Exclude non English speaking countries like China

## Sector Analysis
* Main sector Extraction
  - Split the Category List by ‘|’ and extract the first category which is primary sector
  - Load the Mapping dataset
  - Correct the typos by replacing 0 with ‘na’
  - Get the Main sector from column name in mapping data with help of primary from master dataset
  - Remove the not found main sector column which is around 0.07%
* Analysis Outcomes
  - In USA, UK, and Canada, Most number of investment and most amount were in
    - Others
    * Social, Finance, Analytics, Advertising
    * Cleantech / Semiconductors
  - The top companies that can be invested in the corresponding top 2 sectors are
    - In USA, Virtify and Ning by Glam Media
    - In UK, Antenna Software and Antenna Software
    - In Canada, Zymeworks and QuickPlay Media
  - Total Amount invested in USA was 108017.1Millions, UK was 5394.07Millions and Canada was 3599.29Millions
  - Total number of investment in USA were 12095, UK were 622 and Canada 422
