# Amazon Product Selection Method 2 – Data Scraping Strategy

## Introduction

"Best-sellers" on Amazon show exceptional performance in rankings and sales, often achieving rapid ranking growth in a short time. By leveraging this logic, we can scrape Amazon ranking data to identify potential best-sellers.

Stop wasting time on proxies and CAPTCHAs! ScraperAPI's simple API handles millions of web scraping requests, so you can focus on the data. Get structured data from Amazon, Google, Walmart, and more. Start your free trial today! 👉 [https://www.scraperapi.com/?fp_ref=coupons](https://www.scraperapi.com/?fp_ref=coupons)

---

## How to Identify Data Trends for Best-Sellers?

Once we understand the process of how a best-seller emerges, the next step is to find the data trends. While other sellers' traffic and order volume remain confidential, ranking changes are accessible and can be analyzed.

### Steps for Data Scraping and Product Selection:
1. Choose a broad product category on Amazon.
2. Use a scraping program (or third-party tools like Octoparse if you lack programming skills) to scrape ranking information from up to 400 pages in the selected category.
3. Set a data scraping update cycle, recommended between 4–12 hours.
4. Import the scraped data into analytics software or build a model to evaluate which products have potential to become best-sellers.
5. Optimize the listings of potential products systematically before they dominate the market.

---

## Steps to Analyze Scraped Data

### Step 1: Establish a Product Exit Mechanism
Use data analysis to identify the characteristics of "unpopular" products. For example, a product's rank typically follows this pattern as its sales decline: fewer sales → reduced traffic → eventual zero sales → rapid rank drop.

- On average, when a listing has no orders, its rank increases by about 30,000 per day. Use this trend to create an exit mechanism. For instance, if a product's rank increases by 30,000 per day over a period of 3–30 days (depending on category competition), classify it as "unpopular" and exclude it from the selection pool.

### Step 2: Eliminate Stable Best-Sellers
Exclude stable products since their ranking and sales have already plateaued. For instance:
- Listings with a rank standard deviation below 50,000 generally hold a stable position in Amazon's A9 algorithm.
- Listings with rank standard deviation between 50,000–100,000 show less stability but can still attract potential customers.
- Listings with a rank standard deviation above 100,000 indicate instability and little chance of securing a stable search position.

### Step 3: Identify Potential Products
Focus on two types of potential products:
1. **Rising Rankings**: Listings with rapidly improving rankings (lower rank values).
2. **Unstable Rankings**: Listings with high rank standard deviations, indicating untapped potential due to insufficient optimization or algorithmic mismatches.

### Step 4: Track Rankings in Real-Time
After identifying potential products, monitor their rankings over time. If a product shows stable growth and strong sales, it's likely a hot-selling item ready for immediate listing.

---

## Optimizing the Selection Process

To ensure success, it's critical to streamline the process from data analysis to product launch within 21 days. Here's how to achieve that:

### Solution 1: Utilize Wholesale Platforms
1. Collect data on potential products and check if they are available on platforms like **1688 (Alibaba)**.
2. Purchase small batch orders to test quality and demand.
3. Ship the batch directly to Amazon FBA for sales testing.
4. Based on performance, decide whether to scale production or continue sourcing from 1688.

### Solution 2: Begin Production Early
1. Collect data on potential products and start creating samples immediately.
2. Ship the samples within 10–15 days for quality verification.
3. Complete production within 25 days and send the products to Amazon FBA.

---

## Leveraging Competitor Data for Selection

Many small to medium Amazon sellers source their products from wholesale websites like 1688 and resell them on Amazon. By analyzing competitors' data from these platforms, you can identify trending products and replicate their success.

For instance, search for "Amazon dresses" on 1688. Use scraping tools to gather sales data and analyze fluctuations. Products with significant sales growth are likely trending on Amazon, making them ideal for selection.

---

## Advantages and Challenges of Data Scraping for Product Selection

### Benefits:
- Real-time competitor tracking to identify potential best-sellers.
- Objective and data-driven evaluations save costs and time.
- Eliminates guesswork in product testing.

### Challenges:
- Ranking data may have slight delays.
- High technical skills and data analysis capabilities are required.
- Efficient algorithms are essential to minimize processing time.
- Demands a robust supply chain to keep up with selected products.

By systematically tracking and analyzing product rankings, Amazon sellers can stay ahead of competitors and identify hidden gems to maximize sales potential.
