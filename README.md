# Restaurant-Data-Scraper-RAG-based-Chatbot repository contains web scraping and menu extraction notebooks for various restaurants, along with the extracted data and ChatBOT Notebooks

## Contents

- Web Scraping
- Menu Scraping
- Data Preprocessing
- RAG Chatbot 

## 1) Web Scraping
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



##Other restaurant scrapers (Rick’s Bar, Spicy Duck, Avartana ITC Maurya, Avartana ITC Maratha, Avartana ITC Kolkata, Capital Kitchen): We can use a standard code, but using different specific codes for these different websites helped us get more dependable data and information for our knowledge base.

### Overview

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
