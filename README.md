
# AI Web Scraper

This project is an AI-powered web scraper designed to extract and parse specific information from websites. It leverages a combination of Selenium for web scraping, BeautifulSoup for HTML parsing, and Llama 3.1 for AI-based text processing. The application is built with Streamlit, making it interactive and user-friendly.

## Features

- **Scrape Websites:** Fetch content from any given URL.
- **Extract Body Content:** Isolate the main body content from the scraped HTML.
- **Clean Content:** Remove unnecessary scripts and styles for cleaner data.
- **Parse Content with Llama 3.1:** Use an AI model to extract specific information based on user-provided descriptions.

## Project Structure

- `main.py`: Contains the Streamlit-based user interface and integrates the web scraping and parsing functionalities.
- `scrape.py`: Handles the scraping of websites using Selenium and processes HTML content using BeautifulSoup.
- `parse.py`: Utilizes Llama 3.1 to parse and extract information from the cleaned web content.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/vedanth005/ai-web-scraper.git
   cd ai-web-scraper
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up the Selenium WebDriver connection with your API key:
   - Replace `'API KEY'` in `scrape.py` with your actual Scraping Browser API key.

## Usage

1. **Run the Application:**
   ```bash
   streamlit run main.py
   ```

2. **Using the Web Scraper:**
   - Open the Streamlit app in your browser.
   - Enter the URL of the website you want to scrape in the input field.
   - Click the "Scrape Website" button to fetch and display the content.

3. **Parsing the Content:**
   - After scraping, you can provide a description of what specific information you want to extract.
   - Click the "Parse Content" button to use Llama 3.1 to extract the desired information based on your description.

## Code Overview

### main.py

- Initializes the Streamlit UI.
- Manages user input for URL and parsing descriptions.
- Calls scraping and parsing functions and displays results.

### scrape.py

- **scrape_website(url):** Connects to a remote browser via Selenium, navigates to the specified URL, and retrieves the HTML source.
- **extract_body_content(html_content):** Extracts the `<body>` content from the HTML.
- **clean_body_content(body_content):** Cleans the extracted content by removing scripts, styles, and unwanted whitespace.
- **split_dom_content(dom_content, max_length=7000):** Splits large DOM content into manageable chunks for processing.

### parse.py

- **parse_with_ollama(dom_chunks, parse_description):** Uses the Llama 3.1 model to parse DOM content chunks based on user-provided descriptions. Only extracts the requested information, ensuring the output is concise and relevant.

## Dependencies

- `Streamlit`: For the interactive UI.
- `Selenium`: For web scraping.
- `BeautifulSoup`: For HTML parsing.
- `Llama 3.1 (OllamaLLM)`: For AI-based parsing.
- `langchain_core`: For managing AI model prompts.

## Future Enhancements

- **API Integration**: Replace the local Llama 3.1 model with a cloud-based LLM API (e.g., OpenAI’s GPT-4) for better scalability and access to more advanced models.
- **Improved Error Handling**: Enhance error handling for network issues, API limits, and complex HTML structures, with clear user feedback.
- **Multi-Language and Export Support**: Add support for parsing multiple languages and export options (CSV, JSON).
- **Performance and Monitoring**: Optimize performance, enhance CAPTCHA handling, and add real-time content monitoring with automated alerts.


