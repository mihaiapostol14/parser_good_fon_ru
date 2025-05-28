# Parser GoodFonRu

A Python-based web parser for scraping and downloading images from the GoodFon.ru wallpaper website. This project automates the process of searching, collecting, and saving image links and files using Selenium with Firefox WebDriver.

---

## Table of Contents

- [Project Objective](#project-objective)
- [Key Features](#key-features)
- [Technical Details](#technical-details)
- [Quick Start: Cloning the Repository](#quick-start-cloning-the-repository)
- [Setup Instructions](#setup-instructions)
- [Usage Guide](#usage-guide)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)

---

## Project Objective

**Parser GoodFonRu** is designed for automated collection and download of wallpapers from GoodFon.ru. It allows users to specify search queries, scrapes image links, and saves both links and images to local directories, handling anti-bot measures via dynamic user-agent and randomized delays.

---

## Key Features

- **Automated Image Search:**  
  Search for wallpapers on GoodFon.ru with a user-provided keyword and a configurable page range.

- **Link Extraction and Storage:**  
  Collects all wallpaper page links for a given search and saves them to a text file.

- **Image Download Automation:**  
  Parses the collected links, navigates to each wallpaper page, and downloads the direct image source.

- **Anti-Bot Evasion:**  
  Utilizes custom user-agent, disables WebDriver detection, randomizes pauses, and handles exceptions robustly.

- **Configurable via .env:**  
  User-agent is set via a `.env` file for flexibility and privacy.

---

## Technical Details

- **Main Language:** Python
- **Core Libraries:**  
  - Selenium (web automation)  
  - dotenv (for environment management)
- **Structure:**
  - `main_parser.py`: Handles searching and scraping wallpaper page links.
  - `parser_image.py`: Navigates image pages and downloads actual images.
  - `helper/`: Contains utility classes for browser automation and element verification.
  - `config/`: Loads user-agent from `.env`.

#### Example Core Classes & Functions

- `MainParser`: Orchestrates the search, link extraction, and file writing.
- `ParserItemInfo`: Loads links from file, navigates, downloads images.
- `Helper`: Utility methods for file operations and random delays.
- `ElementChecker`: Checks for existence of DOM elements robustly.

---

## Quick Start: Cloning the Repository

To get started, clone the repository to your local machine:

```sh
git clone "https://github.com/mihaiapostol14/parser_good_fon_ru.git"
```

---

## Setup Instructions

1. **Create Virtual Environment & Install Requirements:**  
   [Live Demo](https://mihaiapostol14.github.io/make-python-virtual-environment-live-demo/)

2. **Environment Configuration:**
   - Create a `.env` file inside the `config` directory.
   - Add:
     ```
     USER_AGENT='Firefox user agent'
     ```

3. **Run Scripts:**
   - First, run `main_parser.py` to collect image links.
   - Then, run `parser_image.py` to download images.

---

## Usage Guide

- **main_parser.py:**  
  Prompts for a search keyword, then scrapes image page links for that keyword.
- **parser_image.py:**  
  Reads the saved links and downloads the images to your local directory.

**Note:**  
Make sure GeckoDriver is available at the specified path (`GeckoDriver/geckodriver.exe`).

---

## Contribution Guidelines

- Fork this repository and clone your fork.
- Create a new branch for your feature or bugfix.
- Submit a pull request with a clear description of your changes.

---

## License

_No license file specified. If you intend to add one, consider creating a `LICENSE` file._

---

## Links

- GitHub: [mihaiapostol14/parser_good_fon_ru](https://github.com/mihaiapostol14/parser_good_fon_ru)