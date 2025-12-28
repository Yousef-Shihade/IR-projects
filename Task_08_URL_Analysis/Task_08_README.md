# Task 8: URL Analysis & Robots.txt Crawler Permissions

## Project Overview
This project demonstrates key Information Retrieval concepts related to web crawling and link analysis. It breaks down complex URLs into their fundamental components and evaluates server-side crawling permissions.

## Key Technical Features
* **Protocol Analysis:** Extracts TLD, Domain, Subdomain, Path, and Query parameters.
* **Advanced Domain Logic:** Correctly parses multi-level TLDs common in Israel (`.ac.il`) and the UK (`.ac.uk`).
* **Robots.txt Parser:** * Fetches live `robots.txt` files using custom `User-Agent` headers.
    * Identifies disallowed paths and formats them as full URLs.
    * Detects `Crawl-delay` and specific `User-agent` restrictions.

## Libraries Used
* `urllib.parse` & `urllib.request`
* `pandas` (for structured data output)
