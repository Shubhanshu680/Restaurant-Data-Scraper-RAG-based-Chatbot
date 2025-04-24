# Restaurant-Data-Scraper-RAG-based-Chatbot 
### This repository contains web scraping and menu extraction notebooks for various restaurants, along with the extracted data and ChatBOT Notebooks

## Contents

- Web Scraping
- Menu Scraping
- Data Preprocessing
- RAG Chatbot 

# 1) Web Scraping
Here is a **brief overview of the selected hotels for scraping**

- **Avartana (ITC Maurya, New Delhi & ITC Maratha, Mumbai)**
- **Southern Culinary Mosaics (ITC Royal Bengal, Kolkata)**
- **Rick’s (The Taj Mahal Hotel, New Delhi)**
- **Spicy Duck (Diplomatic Enclave, New Delhi)**
- **Emperor Lounge (Taj Mahal, New Delhi)**
- **Capital Kitchen (Diplomatic Enclave, New Delhi)**


-*Summary*: The selected hotels are high-end establishments in major Indian cities (New Delhi, Mumbai, Kolkata), primarily within ITC and Taj group properties. They offer a range of cuisines, with a special emphasis on innovative South Indian and multi-cuisine offerings, and are known for their premium dining experiences and unique culinary presentations.

Also, scraping data with all authentic information, along with the detailed menu and descriptions, was relatively easy.

# Capital Kitchen Restaurant Scraper

This project demonstrates web scraping and menu extraction for **Capital Kitchen**, a multi-cuisine restaurant at Taj Palace, New Delhi.

## Project Overview

- **Goal:**  
  Extract restaurant details (name, location, contact, timings) and menu items (from the official PDF menu links) for Capital Kitchen.
- **Tech Stack:**  
  Python, Requests, BeautifulSoup, PyPDF2, Pandas

## How It Works

1. **Scrape Restaurant Details:**  
   The script fetches the restaurant’s name, address, contact info, and dining hours directly from the [official website](https://www.tajhotels.com/en-in/hotels/taj-palace-new-delhi/restaurants/capital-kitchen).

2. **Find and Download Menu PDF:**  
   The code locates the downloadable menu PDF link on the page.

3. **Extract Menu Items:**  
   Menu items, prices, and descriptions are parsed from the PDF using PyPDF2.

4. **Save Results:**  
   - Restaurant details are saved as `restaurant_details.json`
   - Menu items are saved as `capital_kitchen_menu.csv` and `capital_kitchen_menu.json`

## Example Output

```
Name: Capital Kitchen
Location: 2 Sardar Patel Marg Diplomatic Enclave, New Delhi, 110021, India
Contact: 1-800-111-825 | reservations@ihcltata.com

Timings:
 Breakfast: 6:30 am to 10:30 am
 Lunch: 12:30 pm to 2:45 pm
 Dinner: 7:00 pm to 11:00 pm

Sample Menu Item:
| section    | item                | price  | description                                    |
|------------|---------------------|--------|------------------------------------------------|
| Menu Items | PIZZA PEPPERONI     | ₹1450  | Pork pepperoni, crushed tomatoes, mozzarella   |
```

## How to Run

1. Clone this repo or open the notebook in Google Colab.
2. Install dependencies:
   ```python
   !pip install requests beautifulsoup4 PyPDF2 pandas
   ```
3. Run all cells in `capital_Scrap-1.ipynb`




## Other restaurant scrapers (Rick’s Bar, Spicy Duck, Avartana ITC Maurya, Avartana ITC Maratha, Avartana ITC Kolkata, Capital Kitchen): We can use a standard code, but using different specific codes for these different code files helped me get more dependable, targeted and diverse data and information for our knowledge base.

## Overview

- **Goal**: Automatically extract up-to-date restaurant information (name, location, contact, cuisine, timings) and menu items (dish names, prices, descriptions) for (Rick’s Bar, Spicy Duck, Avartana ITC Maurya, Avartana ITC Maratha, Avartana ITC Kolkata, Capital Kitchen).
- **Technologies**: Python, Requests, BeautifulSoup, Pandas, (optionally) PyPDF2 for PDF menu extraction.

## How It Works

1. **Scrape Restaurant Details**  
   The script fetches the restaurant’s name, address, contact info, cuisine, and dining hours from the official website.

2. **Extract Menu Items**  
   - If the menu is available as HTML, dish names, prices, and descriptions are parsed directly.
   - If the menu is a downloadable PDF, the script uses PyPDF2 to extract menu items.

3. **Save Results**  
   - Restaurant details are saved as `[restaurant_name]_details.json`
   - Menu items are saved as `[restaurant_name]_menu.csv` and `[restaurant_name]_menu.json`

   
## Usage

1. Clone this repository or open the notebook in Google Colab.
2. Install required libraries:
   ```python
   !pip install requests beautifulsoup4 pandas PyPDF2
   ```
3. Run the notebook or script.  
   The output files will be saved in the current directory.

## Example Output

```
Name: [Restaurant Name]
Location: [Address]
Contact: [Phone] | [Email]
Cuisine: [Cuisine]
Timings: [Timings]

Sample Menu Item:
| section    | item           | price  | description                   |
|------------|----------------|--------|-------------------------------|
| Appetizers | Potato cracker | ₹600   | with tamarind ghee glaze      |
```
# 2) Menu Extractor

This provides a reproducible workflow for extracting restaurant menu data from structured or semi-structured sources (such as PDFs, websites, or HTML tables) into a clean, tabular format for further analysis or application use.

## Overview

- **Goal:** Automatically extract menu sections, item names, prices, and descriptions from restaurant menu sources.
- **Output:** A structured table (DataFrame/CSV) with columns: `section`, `name`, `price`, `description`.

## How It Works

1. **Input:**  
   - The notebook accepts menu data from PDFS, HTML, or preformatted text sources.
2. **Extraction:**  
   - Parses menu sections, item names, prices, and descriptions using Python (e.g., regular expressions, BeautifulSoup, PyPDF2).
3. **Cleaning:**  
   - Handles missing values, removes extraneous text, and standardises price formats.
4. **Output:**  
   - Saves the cleaned menu data to a CSV file for downstream use (e.g., analytics, chatbot training).

## Example Output

| section     | name                   | price  | description                                  |
|-------------|------------------------|--------|-----------------------------------------------|
| Menu Items  | PIZZA PEPPERONI        | ₹1450  | Pork pepperoni, crushed tomatoes, mozzarella  |
| Menu Items  | THE CAPITAL PIZZA      | ₹1150  | Barbecued chicken, red onion, fresh coriander |
| Menu Items  | CLASSIC PIZZA MARGHERITA| ₹1150 | Mozzarella, fresh basil, tomato sauce         |
| Menu Items  | PIZZA FUNGI            | ₹1150  | N/A                                          |

## How to Use

1. **Open the notebook:**  
   Open `Menu_Extract.ipynb` in Jupyter or Google Colab.

2. **Install dependencies:**  
   Make sure you have the required Python packages:
   ```python
   !pip install pandas beautifulsoup4 PyPDF2
   ```

3. **Run the notebook:**  
   Follow the cells in order to extract, clean, and export menu data.

4. **Exported data:**  
   The cleaned menu will be saved as a CSV file in the working directory.

## Project Structure

```
Menu_Extract.ipynb        # Main notebook for menu extraction
menu_data.csv             # (example) Output CSV with extracted menu
```

## Notes

- The extraction logic may need minor adjustments for different menu formats or layouts.
- For dynamic (JavaScript) web menus, consider using Selenium.
- For scanned PDFs, OCR (e.g., pytesseract) may be required.


**Brief:**  
This menu extractor is designed for rapid, reliable extraction and cleaning of restaurant menu data for data science, analytics, or AI applications.

# 3) Data Processing for Training

## Overview

- **Goal:**  
  To create a unified, structured dataset of restaurant details and menu items from multiple sources (web scraping, PDFs, JSON, CSV) suitable for training retrieval-augmented generation (RAG) models or other NLP systems.

- **Data Sources:**  
  - In JSON format, restaurant details (name, location, contact, timings, cuisine).
  - Menu items (section, item, price, description, location) in CSV format, merged from various scrapers and extractors.

---

## Data Files

- **Restaurant Details JSONs:**  
  - `restaurant_details.json`, `spicy_duck_details.json`, `emperors_lounge_details.json`, `ricks_bar_details.json`, `avartana_itcmaurya_details.json`, `avartana_itcmaratha_details.json`, `avartana_details.json`
    - Each file contains structured information about a specific restaurant, including name, location, contact, cuisine, timings, and (where available) menu URLs.

- **Menu Data CSVs:**  
  - `final_merged_menu.csv`, `final_merged_menu_with_location.csv`, `cleaned_FINAL_BY_ME_Merged.csv`
    - These files contain menu items for all restaurants with columns such as `restaurant`, `section`, `item`, `price`, `description`, and (optionally) `location`, `latitude`, `longitude`.

---

## Data Processing Workflow

1. **Scraping & Extraction:**  
   - Restaurant details are scraped from official websites and stored as JSON files.
   - Menu items are extracted from PDFs, HTML pages, or web APIs, and saved as CSV files.

2. **Cleaning & Standardization:**  
   - All menu CSVs are cleaned to ensure consistent columns (e.g., `restaurant`, `item`, `price`, `description`).
   - Missing values are handled, and prices are standardised to a common format (e.g., "₹1450").
   - Locations and coordinates are added where available.

3. **Merging:**  
   - Individual restaurant menu files are merged into a single CSV (`final_merged_menu.csv` or `cleaned_FINAL_BY_ME_Merged.csv`) for unified access.
   - Each menu item is associated with its restaurant and, where possible, its location.

4. **Enrichment:**  
   - Additional metadata (e.g., latitude, longitude, cuisine) is added from the details JSONS or external sources.

5. **Ready for Training:**  
   - The merged and cleaned CSV is now suitable for:
     - Training retrieval-augmented generation (RAG) chatbots
     - Fine-tuning language models for restaurant Q&A

---

## Example: Unified Menu Data

| restaurant        | section                | item                   | price  | description                                      | location                    |
|-------------------|------------------------|------------------------|--------|--------------------------------------------------|-----------------------------|
| Capital Kitchen   | Menu Items             | SEAFOOD PIZZA          | ₹1450  | Calamari, shrimp, smoked salmon, confit garlic   |                             |
| Capital Kitchen   | FROM THE STONE OVEN    | CAESAR SALAD           | ₹875   | Romaine lettuce, crispy bacon, grilled chicken   |                             |
| Rick's Bar        | Menu Items             | Glenfarclas            | ₹1954  |                                                  |                             |
| Emperor Lounge    |                        | Curried vegetable turnover | 350 | Puff pastry, mix vegetable masala                |                             |
| Kolkata (ITC Royal Bengal) |               | Potato cracker         | N/A    | with tamarind ghee glaze                         | Kolkata (ITC Royal Bengal)  |

---

## How to Use

1. **For Data Science/ML Training:**
   - Load the merged CSV (e.g., `cleaned_FINAL_BY_ME_Merged.csv`) using pandas:
     ```python
     import pandas as pd
     df = pd.read_csv('cleaned_FINAL_BY_ME_Merged.csv')
     ```
   - Use the JSON files to enrich menu items with metadata (e.g., cuisine, timings).

2. **For RAG Chatbot Training:**
   - Use the merged CSV as your knowledge base.
   - Each row (menu item) can be indexed for retrieval.
   - Restaurant details JSONs can be used for context enrichment.

---

## Notes

- **Missing Data:** Some menu items or restaurants may have missing fields (e.g., price or description) due to source limitations.
- **Location Data:** Where available, latitude and longitude are included for geospatial applications.
- **Extensibility:** The pipeline can be extended to new restaurants by adding new JSON/CSV files and re-running the merge/cleaning scripts.

---

**Summary:**  
This repository provides a robust, extensible pipeline for collecting, cleaning, and merging multi-restaurant menu and metadata, ready for use in AI/ML training or analytics.
