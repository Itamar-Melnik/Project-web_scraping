# Used Car Price Prediction – Part 1: Data Collection & Scraping

**Academic end-to-end ML project (2024) – Part 1/3**

Automated web scraper that collects real used-car listings from ad.co.il. **This implementation focuses on a single manufacturer (Peugeot)** as per assignment requirements, extracting 54 records with 20+ features for machine learning analysis.

---

## 📋 Project Overview

This repository implements a robust web scraping pipeline that:
- Crawls used car listings from https://www.ad.co.il/car (single manufacturer)
- Extracts comprehensive vehicle information (20+ features)
- Integrates with Israeli Ministry of Transport API for supply metrics
- Produces clean, structured datasets ready for ML modeling

### Assignment Context
Each team was assigned to collect data for **one specific manufacturer**. This implementation scrapes **Peugeot** vehicles (manufacturer code: 13896).

## 🎯 Features Extracted

**Basic Information:**
- Manufacturer & Model
- Year of manufacture
- Mileage (km)
- Previous ownership (hand)
- Area & City

**Technical Specifications:**
- Engine type (Petrol/Diesel/Hybrid/Electric)
- Engine capacity (cc)
- Color

**Market Data:**
- Listed price
- Test (טסט) days remaining
- Number of photos
- Publish & republish dates
- Description text

**Engineered Features:**
- `supply_score` – Number of similar vehicles in market (via Gov API)

## 📁 Repository Structure

```
.
├── project.ipynb           # Main scraping & initial cleaning notebook
├── output (1).csv          # Collected dataset (54 Peugeot records)
└── README.md              # This file
```

## 🛠️ Technologies

- **Python 3.8+**
- **requests** – HTTP requests
- **BeautifulSoup4** – HTML parsing
- **pandas** – Data manipulation
- **Jupyter Notebook** – Interactive development
- **Israeli Gov Open Data API** – Vehicle supply data

## 🚀 How to Run

### Prerequisites
```bash
pip install requests beautifulsoup4 pandas jupyter
```

### Execution
```bash
# Launch Jupyter Notebook
jupyter notebook project.ipynb

# Run all cells to execute scraping pipeline
# Output: output (1).csv
```

**Note:** Scraping is for educational purposes only. The implementation respects robots.txt and implements rate limiting during development.

## 📊 Results Snapshot

- **54 unique Peugeot listings** collected
- **20+ features** per record
- **Supply score** feature engineered via API integration
- **Clean structured format** (CSV) for downstream ML

### Dataset Size Note
The assignment required each team to scrape **one manufacturer only**. To collect data for all manufacturers, modify the `base_url` in the `main()` function:

```python
# Current implementation (Peugeot only):
base_url = "https://www.ad.co.il/car?sp261=13896"

# To scrape all manufacturers:
base_url = "https://www.ad.co.il/car?"
```

## 🔗 Full Pipeline Overview

| Stage | Repository | Description |
|-------|------------|-------------|
| **1** | **[used-car-price-prediction-01-scraping](https://github.com/Itamar-Melnik/used-car-price-prediction-01-scraping)** | **Real-data collection via scraping (this repo)** |
| 2 | [used-car-price-prediction-02-ml](https://github.com/Itamar-Melnik/used-car-price-prediction-02-ml) | Cleaning messy data & ElasticNet modeling |
| 3 | [used-car-price-prediction-03-deployment](https://github.com/Itamar-Melnik/used-car-price-prediction-03-deployment) | Flask web app for live price prediction |

## 📝 License

MIT License

**Academic project (July 2024) · No active maintenance**

---

*This is part of an academic ML pipeline demonstrating real-world data collection, model training, and deployment.*
