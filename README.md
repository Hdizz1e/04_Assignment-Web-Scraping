# 04_Assignment-Web-Scraping
Wiki Pages
    List of largest companies by revenue
    - https://en.wikipedia.org/wiki/List_of_largest_companies_by_revenue#By_country
    GDP by Country
    - https://www.worldometers.info/gdp/gdp-by-country/?source=wb&region=worldwide&year=2024&metric=nominal
Tables selected
    Wiki table containing top 50 companies by revenue
    Worldometer table containing country GDP stats
Cleaning Steps
    Company Data
    - Extracted company table
    - Flattened multi-level column hheaders into a single level
    - Renamed columns
    - Recovered State-owned feature and made it a boolean
    - Removed unnecessary columns such as reference identifiers
    - Converted revenue and profit values to numeric
    GDP Data
    - Extracted GDP table
    - Filtered data to only include countries from company dataset
    - Removed currency symbols, commas, and percentage symbols
    - Converted GDP values, per capita values, growth, and share of world GDP into numeric
    - Corrected character encoding issues from negative GDP growth values
Merge Process
    - Merged using the country column as common key
    - Left join
Challenges and Limitations
    - The state-owned column was not text, it had to be extracted from HTML class values
    - The GDP table contained weird encodings that caused negative growth values to display incorrectly
    - One company was missing profit, I preserved it as missing instead of imputing
