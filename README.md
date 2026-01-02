# Fragrantica Brand & Product Data Scraper

## 📌 Project Overview (Client Perspective)

This project is a **high-reliability web data extraction system** designed to collect structured brand and product information from **Fragrantica** at scale.

It delivers clean, well-organized CSV datasets containing:
- Brand-level information
- Product-level details
- Ratings, accords, descriptions, images, and metadata

The solution is built to handle **thousands of URLs**, avoid IP bans, and ensure data consistency — making it ideal for:
- Market research
- Competitive analysis
- Data analytics
- E-commerce enrichment
- Machine learning datasets

### ✅ Key Business Benefits
- **Scalable**: Handles thousands of brand & product pages
- **Reliable**: Uses premium proxy rotation via ScrapingBee
- **Accurate**: Structured extraction with fallback handling
- **Cost-Efficient**: Optimized JS rendering (used only when necessary)
- **Production-Ready Output**: Clean CSV ready for analysis or import

---

## 📊 Extracted Data Fields

### Brand-Level Data
- Country
- Parent Company
- Parent Company URL
- Main Activity
- Brand Name
- Brand Description
- Brand Website
- Brand Image

### Product-Level Data
- Product Name
- Release Year
- Main Accords
- Product Description
- Sub Description
- Rating
- Number of Ratings
- Product Image
- Product URL

---

## 🛠 Technical Overview (Developer Perspective)

### Architecture Highlights
- **Python-based scraper**
- **ScrapingBee API** for:
  - IP rotation
  - Anti-bot bypass
  - Optional JavaScript rendering
- **Multithreading** using `ThreadPoolExecutor`
- **Thread-safe CSV writing**
- **Memory-efficient batch saving**
- **Graceful error handling & retry-safe design**

### Why This Design?
- Brand pages require JS → rendered selectively  
- Product pages load faster → scraped without JS  
- Concurrency is limited to avoid rate limiting  
- Batch CSV writing ensures progress is never lost  

---

## ⚙️ Tech Stack

- Python 3.9+
- Requests
- BeautifulSoup (lxml parser)
- Pandas
- ScrapingBee API
- ThreadPoolExecutor
- TQDM (progress tracking)

---

## 🚀 How It Works

1. Load brand URLs from CSV
2. Scrape brand metadata + product links
3. Concurrently scrape product details
4. Normalize & merge brand + product data
5. Save results incrementally to CSV

---

## 📁 Input & Output

### Input
```text
fragrantica_brands.csv
