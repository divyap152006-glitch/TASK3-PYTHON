# TASK3-PYTHON
# Task 3: Web Scraper for News Headlines

## 📌 Objective

Scrape top news headlines from a public website using Python, Requests,
and BeautifulSoup.\
This script collects all `<h2>` headings from BBC News and saves them
into a `headlines.txt` file.

------------------------------------------------------------------------

## 🛠 Tools Used

-   **Python**
-   **requests** (for downloading webpage HTML)
-   **BeautifulSoup (bs4)** (for parsing the HTML)

------------------------------------------------------------------------

## 📂 Files Included

-   `news_scraper.py` --- Python script to scrape headlines\
-   `headlines.txt` --- Output text file where headlines will be saved\
-   `README.md` --- Description & instructions

------------------------------------------------------------------------

## ▶️ How the Script Works

1.  Send an HTTP request to the news website\
2.  Parse the HTML using BeautifulSoup\
3.  Extract all `<h2>` headline tags\
4.  Print headlines on the screen\
5.  Save the headlines to `headlines.txt`

------------------------------------------------------------------------

## 📄 Code Used

``` python
import requests
from bs4 import BeautifulSoup

def scrape_news():
    url = "https://www.bbc.com/news"
    response = requests.get(url)
    soup = BeautifulSoup(response.text, "html.parser")
    headlines = soup.find_all("h2")

    with open("headlines.txt", "w", encoding="utf-8") as file:
        for h in headlines:
            title = h.get_text(strip=True)
            if title:
                print(title)
                file.write(title + "\n")

    print("\n✔ Headlines saved to headlines.txt")

if __name__ == "__main__":
    scrape_news()
```

------------------------------------------------------------------------

## 🧪 How to Run the Script

### 1️⃣ Install Required Libraries

    pip install requests beautifulsoup4

### 2️⃣ Run the Script

    python news_scraper.py

### 3️⃣ Output

A file named **headlines.txt** will be created containing all scraped
headlines.

------------------------------------------------------------------------

## ✔️ Outcome

You will automate headline extraction from a news website and save them
for offline use or analysis.
