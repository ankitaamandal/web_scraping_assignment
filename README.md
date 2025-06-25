EudraGMDP Database Scraping
# Authorization Holder Scraper and Cleaner

This project automates the extraction of Authorization Holder names and their Site Addresses from a webpage using Selenium, filters and cleans the data, and then optionally performs Google searches based on the extracted names.

---

## Requirements

- Python 3.x
- Selenium
- A ChromeDriver (or other browser driver) compatible with your browser version

Install requirements:
```bash
pip install requirements.txt

## Approach
The first step was to become familiar with the structure of the EudraGMDP database. This involved reviewing documents and annexes to understand the terminology used

#### Assumptions
* The site did not display product names explicitly, which were originally intended for extraction.
* Through documentation review, I found that plasma products are categorized under Blood Products.
* Based on this, I enabled "Enable Operations Search" and selected Blood Products in the annexes related to Manufacture and Import.
* I filtered results to only include Authorization Holders ending with "GmbH" or "AG". This decision was made because many entries were hospitals, which likely focus on research or transfusion rather than manufacturing or importing products.

#### Limitations
* Although the database provides an Export to Excel option, it consistently resulted in errors during download.
* As a workaround, I automated the extraction using Selenium, page by page.
* Product names were not included in the csv, as they did not appear directly on the website. Retrieving this information would require additional manual research or cross-referencing with external sources.

### Scaling it up
Due to time constraints, this project focused on extracting and cleaning the most essential information. However, there are several areas that could be expanded or improved in the future:
*Since product names were not available directly on the EudraGMDP website, future work could involve linking authorization holders to external data sources—such as official product registries or company websites to associate specific products with each manufacturer or importer.

## Development Notes

- The current implementation is written in a Jupyter Notebook, which allowed for rapid prototyping and easier inspection during the early stages of development.
- For future iterations, the project can be refactored into standalone Python scripts with a clear command-line interface (CLI). 
- This would make the tool more reusable and accessible for other users, allowing it to be executed without modifying the core code.


