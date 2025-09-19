# parser GoodFon.ru

A web scraping tool for downloading wallpaper images from [GoodFon.ru](https://www.goodfon.ru/) based on user queries.

## Project Overview

`parser_good_fon_ru` automates the collection of wallpaper image links and downloads images from GoodFon.ru. The parser utilizes Selenium WebDriver with Firefox to mimic human browsing behavior, bypassing bot detection and navigating site pages for specific search queries.

### Features

- **Custom Image Search:** Input any search term to retrieve wallpapers matching your query.
- **Automated Browsing:** Navigates multiple result pages, mimics human actions, and scrolls to ensure all images are loaded.
- **Image Link Collection:** Extracts and saves unique wallpaper page URLs for later downloading.
- **Image Download Automation:** Visits each saved wallpaper page link, extracts the direct image URL, and saves it to disk.
- **Duplicate Removal & Organization:** Utilities for organizing directories, removing duplicate links, and structured output files.
- **Configurable User-Agent:** Loads custom user-agent strings from environment variables to evade bot detection.

## Technologies Used

- **Python 3:** Main programming language.
- **Selenium WebDriver (Firefox):** Automated browser interactions and navigation.
- **GeckoDriver:** Bridge for Selenium to control Firefox.
- **Dotenv:** Loads environment variables (e.g., user-agent) from `.env` files.
- **Standard Python Libraries:** `os`, `time`, `random` for file and process handling.

## Main Components

- **main_parser.py:** Orchestrates user input, starts the scraping process, collects wallpaper page links, and organizes results.
  - Initializes Selenium Firefox WebDriver with custom preferences.
  - Accepts search terms, navigates result pages, and creates directories for storing output.
- **parser_image.py:** Reads collected links and downloads images.
  - Iterates through each saved wallpaper page link, interacts with page elements, and saves image URLs.
- **helper/**: Utilities for directory/file creation, duplicate removal, and random delays to mimic human behavior.
  - `Helper`: File and directory operations, duplicate link removal.
  - `DriverHelper`: WebDriver navigation and session management.
  - `ElementChecker`: Checks for the existence of page elements.
- **config/**: Loads configuration such as user-agent from environment variables.

## Example Workflow

1. **Search and Collect Links:**
   - Run `main_parser.py`.
   - Enter your desired image keyword (e.g., "nature").
   - The script will scrape GoodFon.ru for matching wallpapers and save page links in a structured directory.

2. **Download Images:**
   - Run `parser_image.py`.
   - It will iterate through the saved links and extract/download image URLs.

## Setup and Execution

### 1. Clone the Repository

```bash
git clone https://github.com/mihaiapostol14/parser_good_fon_ru.git
cd parser_good_fon_ru
```

### 2. Create and Activate a Virtual Environment

**Install Python**

If you don't have Python installed, follow [this link](https://www.python.org/downloads/) and download the latest version of Python. Then you can check your version of Python using the command lines below:

```bash
# Create a virtual environment
python -m venv venv  

# Activate the virtual environment
source venv/bin/activate  # Linux/MacOS  
venv\Scripts\activate     # Windows  
```

### 3. Install the Required Libraries

```bash
pip install -r requirements.txt
```


## License

Currently, no license specified. Please consult the repository owner for usage permissions.


## Author
[Mihai Apostol](https://github.com/mihaiapostol14)