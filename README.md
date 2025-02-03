# Amazon Web Scraper

## Overview

This project is a Python-based web scraper designed to extract product information from Amazon's website. It collects data such as product titles, images, ratings, and the number of reviews for products listed on Amazon. The scraped data is saved in a CSV file for further analysis or use.

The project is built using Python and utilizes libraries like `BeautifulSoup` for parsing HTML, `csv` for handling CSV files, and `os` for file operations. Additionally, it includes a custom `print` module for colored terminal output to enhance readability during execution.

---

## Features

1. **Web Scraping**:
   - Extracts product details such as title, image URL, rating, and number of reviews from Amazon product pages.
   - Handles pagination to scrape multiple pages of search results.

2. **Data Storage**:
   - Saves scraped data in a CSV file (`data.csv`) with columns: `title`, `image`, `rating`, and `number of reviews`.
   - Ensures no duplicate entries by maintaining a hash map of existing items.

3. **Error Handling**:
   - Detects and skips invalid or empty rows in the CSV file.
   - Alerts the user if the CSV file is corrupt (contains duplicate entries).

4. **Colored Terminal Output**:
   - Uses custom `print` functions to display messages in different colors for better readability:
     - **Red**: Error messages or warnings.
     - **Blue**: Informational messages (e.g., file creation, new items found).
     - **Yellow**: Status updates (e.g., number of products found on a page).

5. **Pagination Support**:
   - Automatically detects the last page of search results and stops scraping.

---

## Prerequisites

Before running the script, ensure you have the following installed:

1. **Python 3.x**: The script is written in Python.
2. **Required Libraries**:
   - `BeautifulSoup`: For parsing HTML content.
   - `requests`: For making HTTP requests to fetch web pages.
   - `csv`: For handling CSV file operations.
   - `os`: For file path operations.
   - `re`: For regular expression-based string manipulation.

Install the required libraries using pip:

```bash
pip install beautifulsoup4 requests
```

---

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/adarshsharma-18/amazon-Webscarper)
   cd <repository-folder>
   ```

2. **Run the Script**:
   Execute the `main.py` script:
   ```bash
   python main.py
   ```

3. **Output**:
   - The script will create or update a CSV file (`data.csv`) in the specified directory (`C:/Users/Adarsh Sharma/code/project/ML project/indian-e-commerce-scaper-master/indian-e-commerce-scaper-master/amazon/`).
   - The CSV file will contain the scraped product data.

4. **Customization**:
   - Update the `file_name` variable in `main.py` to change the output file path.
   - Modify the `get_soup` function in `utils.py` to scrape a different Amazon search URL or category.

---

## Code Structure

### Files

1. **`main.py`**:
   - The main script that orchestrates the scraping process.
   - Handles CSV file operations and ensures no duplicate entries.
   - Uses helper functions from `utils.py` and colored print functions from `print.py`.

2. **`utils.py`**:
   - Contains helper functions:
     - `get_soup(page_number)`: Fetches and parses the HTML content of a specific page.
     - `get_star_elements(page)`: Extracts product elements from the parsed HTML.
     - `is_last_page(page)`: Checks if the current page is the last page of search results.
     - `get_key(title, image)`: Generates a unique key for each product based on its title and image URL.
     - `get_item_from_star_element(element)`: Extracts product details from a product element.

3. **`print.py`**:
   - Defines custom print functions for colored terminal output:
     - `print_red(msg)`: Prints messages in red.
     - `print_green(msg)`: Prints messages in green.
     - `print_yellow(msg)`: Prints messages in yellow.
     - `print_blue(msg)`: Prints messages in blue.
     - `print_magenta(msg)`: Prints messages in magenta.
     - `print_cyan(msg)`: Prints messages in cyan.
     - `print_white(msg)`: Prints messages in white.

---



## Future Enhancements

1. **Dynamic Search URL**:
   - Allow users to input a custom Amazon search URL or category to scrape.

2. **Advanced Error Handling**:
   - Handle network errors, CAPTCHAs, or IP bans during scraping.

3. **Multithreading**:
   - Implement multithreading to speed up the scraping process.

4. **Database Integration**:
   - Store scraped data in a database (e.g., SQLite, MySQL) for better scalability.

5. **GUI**:
   - Develop a graphical user interface (GUI) for easier interaction with the scraper.

---

## Notes

- **Ethical Use**: Ensure you comply with Amazon's terms of service and scraping policies. Use this script responsibly and avoid overloading their servers.
- **Rate Limiting**: Add delays between requests to avoid being blocked by Amazon.

---

## Author

**Adarsh Sharma**

---

## License

This project is open-source and available under the MIT License. Feel free to modify and distribute it as needed.
