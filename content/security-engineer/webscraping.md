## Webscraping 

netloc contains the domain itself it is the "network location"
simple sample webscraper
```
import requests
from bs4 import BeautifulSoup
from urllib.parse import urljoin, urlparse
import re

def scrape_emails(url):
    try:
        response = requests.get(url)
        response.raise_for_status()
        soup = BeautifulSoup(response.content, 'html.parser')
        links = soup.find_all('a', href=True)
        html_links = [link['href'] for link in links if link['href'].endswith('.html')]
        email_pattern = r'[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}'
        emails = re.findall(email_pattern, soup.get_text())
        return emails, html_links

    except request.exceptions.RequestException as e:
        print(f"error acessing url {e}")
        return [],[]

def crawl_website(baseURL, max=10):
    visited = set()
    to_visit = [baseURL]
    all_emails = []
    while to_visit and len(visited) < max:
        current_url = to_visit.pop(0)
        if current_url in visited:
            continue
        visited.add(current_url)
        emails, urls = scrape_emails(current_url)
        print(emails)
        all_emails.extend(emails) #add a check here to see if the email is already in the list

        for link in urls:
            full_url = urljoin(baseURL, link)
            if urlparse(baseURL).netloc == urlparse(full_url).netloc and full_url not in visited:
                to_visit.append(full_url)

    return all_emails
baseURL = 'http://10.102.17.32'
emails = crawl_website(baseURL)
for email in emails:
    print(email)
```
