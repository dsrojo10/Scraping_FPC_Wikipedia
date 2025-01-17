# Scraping Colombian Professional Soccer (2004 - 2024)

This project uses the Wikipedia API and web scraping techniques to extract and analyze data from the Colombian Professional Soccer League (Fútbol Profesional Colombiano) from 2004 to 2024.

## Project Goals

The main goals of this project are:

* Extract match results, including teams, scores, dates, and stadiums, from Wikipedia pages.
* Organize and store the data in a structured format (CSV files).
* Enable further analysis and exploration of the data.

## Data Sources

The primary data source for this project is the Wikipedia API, specifically the Spanish version. The project also uses web scraping techniques to extract information from the HTML source code of relevant Wikipedia pages.

## Methodology

1. **Wikipedia API:** The project uses the `wikipedia-api` library to retrieve data from Wikipedia. It queries pages related to the Colombian Professional Soccer League, such as tournament seasons and match results.
2. **Web Scraping:** For information not available directly through the API, the project uses the `requests` and `BeautifulSoup` libraries to parse HTML content and extract specific data elements.
3. **Data Processing:** The extracted data is processed and transformed into a structured format suitable for analysis. The project uses the `pandas` library to create and manipulate dataframes.
4. **Data Storage:** The processed data is stored in CSV files for easy access and future use.

## Challenges and Solutions

A major challenge in this project was the variability in the format of the results tables on Wikipedia pages across the 2004-2024 period. The Colombian Professional Soccer League has undergone format changes, impacting the structure of these tables.

To address these changes, different scrapers were developed to handle each table format:

* **Legacy Format Scrapers:** Used for extracting information from older tables (2004-2010) with styles like `bgcolor` and `rowspan` cells. Team names could be in bold and specific table layouts had to be considered.
* **Intermediate Format Scrapers:** Used for extracting information from tables (2011-2024) with classes like `wikitable` and `collapsible`. The date header could have a specific `colspan`, and the results were presented more cleanly.
* **Column-based Format Scrapers:** Used to handle tables (2006-2007, 2009-2010) organized in two columns. The logic had to be adapted to extract the complete information for each matchday correctly. The years 2009 and 2010 also presented specific challenges due to their unique formats.

Adapting to these varying formats was crucial to ensure complete and accurate data collection.


## Files

* **`Scraping_FPC.ipynb`:** This Colab notebook contains the code for the project.
* **`todos_contra_todos`:** This folder contains CSV files with match results from different seasons.
* **`url[x].txt`:** Those txt are used for automation.
* **`README.md`:** This file provides documentation about the project.

## Usage

1. Open the `Scraping_FPC.ipynb` notebook in Google Colab.
2. Make sure the necessary libraries (`wikipedia-api`, `requests`, `BeautifulSoup`, `pandas`, `urllib.parse`, `shutil`, `os`) are installed.
3. Execute the code cells to extract and process the data.
4. The CSV files with the extracted data will be saved in the `todos_contra_todos` folder.

## Future Work

* Expand the dataset to include more seasons.
* Add features to analyze teams, player performance, and other statistics.
* Create visualizations to present the findings.

## Contributing

Feel free to contribute to this project by:

* Reporting issues.
* Suggesting improvements.
* Submitting pull requests.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).