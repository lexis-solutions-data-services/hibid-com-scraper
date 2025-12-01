![banner](https://lexis-solutions-apify.fra1.cdn.digitaloceanspaces.com/banners/hibid.png)

# HiBid Auction Scraper

This Apify actor scrapes auction information from [HiBid.com](https://www.hibid.com), a popular online auction platform. The actor can extract detailed auction data including lot details, auction information, payment terms, shipping information, and more. It outputs the data in JSON format.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-mmANep9u6KeNtAEh1-cw7EMuLckJ-channels4_profile.jpg" alt="Hibid.com Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/hibid-com-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


## Table of Contents

- [HiBid Auction Scraper](#hibid-auction-scraper)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Input](#input)
  - [Output](#output)
  - [Usage](#usage)
  - [Limitations](#limitations)
  - [Need to scrape more auction information?](#need-to-scrape-more-auction-information)


## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.0.4` |
| **Last Update** | Dec 1, 2025 |

---



## 💻 Integration Examples

This repository includes example code showing how to integrate the `hibid-com-scraper` actor into your projects.

You can find example implementations in the [`examples/`](./examples) folder:
- **TypeScript/JavaScript**: See [`examples/typescript/`](./examples/typescript) for a complete TypeScript example
- **Python**: See [`examples/python/`](./examples/python) for a complete Python example

Each example includes:
- Ready-to-use code templates
- Setup instructions
- Documentation links

---


## Features

- Scrapes detailed auction information including:
  - Lot details (title, images, category)
  - Auction company information
  - Bidding history
  - Auction dates and times
  - Payment terms and buyer premium
  - Shipping information
  - Terms and conditions
- Handles multiple auction listings
- Outputs data in JSON format for easy integration with other tools

## Input

The actor accepts the following input parameters in JSON format:

- `startUrls` (array): List of URLs to start the scraping process from. It can be an auction listing or specific lot URL.

  ```json
  {
    "startUrls": [
      {
        "url": "https://hibid.com/lot/247953547/franklin-mint-captain-america-motorcycle?ref=lot-list"
      }
    ]
  }
  ```

- `maxPages` (integer): Maximum number of pages to scrape.
- `proxyConfiguration` (object): Proxy settings for the scraping process.

## Output

The actor produces output in JSON format with the following structure:

```json
{
  "url": "https://hibid.com/lot/247953547/franklin-mint-captain-america-motorcycle",
  "companyName": "John M. Hess Auction Service, Inc.",
  "primaryImage": "https://cdn.hibid.com/img.axd?id=8143275931&wid=&rwl=false&p=&ext=&w=600&h=450&t=&lp=&c=true&wt=false&checksum=aRlVmDg0tPbybrOtrTXOgzT1u1XgzBGX",
  "bitHistory": "8 Bids",
  "category": [
    "Lots",
    "Toys",
    "Vintage / Antique Toys"
  ],
  "lotShipping": "Shipping Available",
  "auctionInfo": {
    "Name": "6/2/25 Antiques, Collectibles & Housewares Online Auction",
    "Auctioneer": "John M. Hess Auction Service, Inc.",
    "Type": "Online Only Auction",
    "Date(s)": "5/14/2025 - 6/2/2025",
    "Location": "768 Graystone RoadManheim, PA 17545",
    "Buyer Premium": "15% Buyer Premium added to purchases"
  },
  "paymentInfo": {
    "Currency": "USD",
    "Buyer Premium": "15% Buyer Premium added to purchases",
    "Payment Terms": "Credit Cards are processed following the auction."
  },
  "shippingInfo": "Items must be picked up at 768 Graystone Rd., Manheim PA by Tuesday, June 3rd from 9am - 6pm."
}
```

## Usage

1. Create a new task: In the Apify console, create a new task for the HiBid Auction Scraper actor.

2. Configure input: Provide the necessary input parameters as described above.

3. Run the task: Start the task to begin scraping data.

4. Retrieve output: Once the task is complete, download the output in JSON format.

## Limitations

- The scraper is subject to the limitations and restrictions of HiBid.com, including potential rate limits and CAPTCHAs.
- The actor's performance may vary based on the website's response times and structure changes.
- Some auction information may vary depending on the auction house and specific auction terms.

## Need to scrape more auction information?

👉 Scrape GoDaddy Auctions with [GoDaddy Auctions Scraper](https://apify.com/lexis-solutions/godaddy-auctions-scraper)

👉 Scrape SeLoger with [SeLoger Scraper](https://apify.com/lexis-solutions/seloger-scraper)

👉 Scrape Shopgoodwill with [Shopgoodwill Scraper](https://apify.com/lexis-solutions/shopgoodwill-scraper)


---

👀 p.s.

Got feedback or need an extension?

Lexis Solutions is a [certified Apify Partner](https://apify.com/partners/find). We can help you with custom solutions or data extraction projects.

Contact us on our [website](https://www.lexis.solutions/?ref=apify-profile), [Email](mailto:scraping@lexis.solutions), or [LinkedIn](https://www.linkedin.com/company/lexis-solutions).
