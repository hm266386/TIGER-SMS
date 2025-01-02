
# How to Scrape Google News with Python (2025 Guide)

Scraping Google News can be an effective way to gather articles related to specific topics, enabling businesses, researchers, or analysts to automate the collection of real-time news. In this tutorial, we'll guide you on how to scrape Google News using Python to extract details like article titles, sources, publishing times, authors, and links.

---

Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Get structured data from Amazon, Google, Walmart, and more. Start your free trial today! 👉 [ScraperAPI](https://www.scraperapi.com/?fp_ref=coupons)

---

## What You’ll Learn
In this tutorial, we’ll cover:
- Setting up a Python environment with required libraries.
- Configuring a search query to scrape targeted articles.
- Extracting relevant details from Google News using `requests` and `BeautifulSoup`.
- Saving the results to a CSV file for further use.

## Prerequisites
Before you begin, ensure you have Python installed on your machine. You'll also need the following libraries:
- `requests` for making HTTP requests.
- `BeautifulSoup` from the `bs4` package for parsing HTML content.
- `pandas` for data manipulation and saving results as a CSV file.

Install these libraries using pip:

```bash
pip install requests beautifulsoup4 pandas
```

---

## Step 1: Set Up a Search Query

The first step is to define the topic or term for which you want to scrape Google News articles. This will be your search query.

```python
query = 'US Economy'
```

To ensure the query is URL-safe, we’ll encode special characters using the `encode_special_characters` function.

---

## Python Code to Scrape Google News

Below is the complete Python code for scraping Google News and saving the results to a CSV file:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

# Search Query
query = 'US Economy'

# Encode special characters in a text string
def encode_special_characters(text):
    encoded_text = ''
    special_characters = {'&': '%26', '=': '%3D', '+': '%2B', ' ': '%20'}
    for char in text.lower():
        encoded_text += special_characters.get(char, char)
    return encoded_text

query_encoded = encode_special_characters(query)
url = f"https://news.google.com/search?q={query_encoded}&hl=en-US&gl=US&ceid=US%3Aen"

response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')

articles = soup.find_all('article')
links = [article.find('a')['href'] for article in articles]
links = [link.replace("./articles/", "https://news.google.com/articles/") for link in links]

news_text = [article.get_text(separator='\n') for article in articles]
news_text_split = [text.split('\n') for text in news_text]

news_df = pd.DataFrame({
    'Title': [text[2] for text in news_text_split],
    'Source': [text[0] for text in news_text_split],
    'Time': [text[3] if len(text) > 3 else 'Missing' for text in news_text_split],
    'Author': [text[4].split('By ')[-1] if len(text) > 4 else 'Missing' for text in news_text_split],
    'Link': links
})

# Write to CSV
news_df.to_csv('news.csv', index=False)
```

---

## Code Explanation

1. **Encoding Special Characters**  
   The `encode_special_characters` function ensures the query string follows web standards by replacing characters like `&` and spaces with encoded equivalents.

2. **Requesting Google News**  
   The `requests.get()` function fetches the HTML content of the Google News search results page.

3. **Parsing HTML with BeautifulSoup**  
   The `BeautifulSoup` library extracts all `<article>` tags and retrieves essential details like titles, sources, and links.

4. **Handling Missing Data**  
   If an article lacks publishing time or author details, the code replaces them with "Missing."

5. **Saving to CSV**  
   The results are saved into a CSV file (`news.csv`) using `pandas`.

---

## How to Extract Top Stories

To scrape the latest top stories, modify the URL:

```python
url = "https://news.google.com/home?hl=en-US&gl=US&ceid=US%3Aen"
```

This fetches the homepage of Google News, displaying the most recent and trending articles.

---

## Customizing Location and Language

To adjust the location and language settings for the news articles, modify the URL parameters:
- `hl`: Specifies the language (e.g., `en-US` for English).
- `gl`: Specifies the country (e.g., `US` for the United States).
- `ceid`: Combines country and language preferences (e.g., `US:en`).

Example:

```python
url = "https://news.google.com/search?q=technology&hl=fr&gl=FR&ceid=FR%3Afr"
```

This URL fetches French-language articles related to "technology" in France.

---

## Key Takeaways
- Scraping Google News with Python is straightforward and efficient using `requests`, `BeautifulSoup`, and `pandas`.
- Customizing the search query and URL parameters allows precise targeting of articles.
- Automating the process saves time and provides structured data for analysis.

---

Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Start your free trial today! 👉 [ScraperAPI](https://www.scraperapi.com/?fp_ref=coupons)

---

By following this guide, you can easily build a Google News scraper to collect and analyze news articles for your desired topics. Happy scraping!
