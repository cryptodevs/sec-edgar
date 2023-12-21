# SEC EDGAR Scrapping and Extraction

## Intro

Normally we want to just pull financial data directly from portals like Yahoo Finance or Morningstar. The problem is that many of those providers make almost impossible to dowload historical data for each symbol. SEC provides financial data by enabling EDGAR as a repository for reports like Q-10 or K-10, which gives valuable information to make investment decisions.


## XBRL Format
The SEC's EDGAR (Electronic Data Gathering, Analysis, and Retrieval) system uses XBRL (eXtensible Business Reporting Language) to improve the accessibility and analysis of financial statements and other disclosures. XBRL is an XML-based language that tags financial data with standardized, machine-readable labels.

Here's how XBRL is used in EDGAR and how you can retrieve specific data programmatically from a downloaded XBRL file:

### How SEC EDGAR Uses XBRL Format

1. **Standardized Reporting**: XBRL allows companies to report financial and business information in a standardized format. This standardization makes it easier for investors, analysts, and the SEC itself to compare and analyze data across different companies and time periods.

2. **Tagging Financial Data**: Each piece of financial data in a report is tagged with a unique identifier. These tags are defined in a taxonomy (a dictionary of tags), which provides a common framework for categorizing financial information.

3. **Enhanced Accessibility and Analysis**: Because the data is tagged and structured, it can be more easily accessed and analyzed using software tools. This improves the efficiency of financial analysis and regulatory oversight.

### Retrieving Data Programmatically from an XBRL File

To retrieve specific data from an XBRL file, you can follow these steps:

1. **Download the XBRL File**: XBRL files are available on the SEC's EDGAR database. You can download them directly from the website.

2. **Choose a Programming Language**: Common choices for working with XBRL include Python, Java, and R. Python, with its strong support for data manipulation and analysis, is a popular choice.

3. **Use XBRL Libraries/Tools**: There are several libraries and tools available for parsing and analyzing XBRL files. For Python, libraries like `Arelle`, `XBRL US GAAP Taxonomies`, and `Python XBRL` can be useful.

4. **Parse the XBRL File**: Use the chosen library to parse the XBRL file. This involves reading the file and extracting the data structured according to the XBRL taxonomy.

5. **Query Specific Data**: Once the file is parsed, you can query specific tags to retrieve the data you need. For instance, if you want to get the net income of a company, you would look for the tag related to net income in the taxonomy.

6. **Data Analysis and Manipulation**: After extracting the data, you can use data analysis tools (like pandas in Python) to manipulate and analyze the data as per your requirements.

### Example Code Snippet in Python
```python
import xbrl

# Load the XBRL file
xbrl_file = xbrl.XBRL('path_to_file')

# Retrieve specific data (e.g., net income)
net_income = xbrl_file.get_item('NetIncome')

print(net_income)
```

## Data Access

* Refer to this [link](https://www.sec.gov/os/accessing-edgar-data).
* All symbols can be obtained here: ftp://ftp.nasdaqtrader.com/SymbolDirectory/ (check the nasdaqlisted.txt file) 


