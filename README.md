# InstaBridalTrends: IG Wedding Dress Scraping & Analysis

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/) [![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-green)](https://pandas.pydata.org/) [![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-orange)](https://matplotlib.org/) [![Instaloader](https://img.shields.io/badge/Instaloader-4.9%2B-purple)](https://instaloader.github.io/)

An end-to-end Python tool to **scrape Instagram posts** for wedding dress trends and **analyze** them using NLP and data visualization. Focuses on Egyptian bridal fashion: extract keywords, classify styles (e.g., Princess, Modest), detect fabrics, and visualize engagement/modesty trends.

Built with Python, Pandas, Matplotlib, and Instaloader for ethical scraping.

## 🚀 Features
- **Automated Scraping**: Collect public Instagram posts from hashtags like `#bridalegypt`, `#weddingdress` (up to 100+ posts).
- **Data Cleaning & NLP**: Extract top words from captions/comments, classify dress styles (Princess, Mermaid, Modest), detect fabrics (Chiffon, Lace).
- **Trend Analysis**: Time-series trends for modesty ratio, engagement by style, keyword frequency (log-scale charts).
- **Visualizations**: Interactive dashboards with heatmaps, bar charts, and statistical summaries.
- **Output**: Clean CSV datasets + high-res PNG charts for reports/research.
- **Ethical**: Respects Instagram ToS (public data only, rate limits, no private accounts).

## 📊 Demo Output
- **Keyword Distribution**: Log-scale horizontal bar chart of top 30 keywords (e.g., "تحفة", "فستان").
- **Style Heatmap**: Engagement matrix (Style × Keyword).
- **Top Words**: Separate charts for captions vs. comments.
- **Trends**: Multi-panel dashboard for yearly modesty/engagement evolution.

Example Chart: [Keyword Distribution (Log Scale)](keyword_distribution_log_en.png)

## 🛠️ Installation
1. Clone the repo:
   ```
   git clone https://github.com/ahmedelsany29/InstaBridalTrends.git
   cd InstaBridalTrends
   ```

2. Create virtual environment (recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
   
   **requirements.txt** (create this file):
   ```
   pandas>=2.0
   numpy>=1.24
   matplotlib>=3.7
   seaborn>=0.12
   instaloader>=4.9
   arabic-reshaper>=3.0
   python-bidi>=0.4
   nltk>=3.8
   scikit-learn>=1.3
   ```

## 📖 Usage

### 1. Scraping Instagram Data
Run the scraping script to collect fresh data:
```bash
python scrape_instagram.py
```
- **Input**: Hashtags list (default: `['bridalegypt', 'weddingdress', 'egyptianbride']`).
- **Output**: `instagram_wedding_data_YYYYMMDD.csv` (captions, likes, comments, hashtags).
- **Params**: Edit `max_posts=100` in the script for more data.
- **Note**: Requires Instagram login (optional for public data). Use a test account to avoid bans.

### 2. Analysis & Visualization
Load scraped CSV and run analysis:
```bash
python analyze_wedding_data.py
```
- **Input**: CSV from scraping (or use sample: `sample_wedding_data.csv`).
- **Output**:
  - Processed CSV: `research_dataset_with_top_words.csv` (with `top_caption_word`, `dress_style_category`, etc.).
  - Charts: `keyword_distribution_log_en.png`, `top_words_caption_vs_comment.png`, `impact_heatmap_en.png`.
- **Customization**: Edit `hashtags` or `style_keywords` dict in the script for your focus (e.g., add "قمر" for beauty keywords).

### Example Workflow
```python
# Quick run in Jupyter (wedding_dress_analysis_FINAL.ipynb)
import pandas as pd
df = pd.read_csv('instagram_wedding_data.csv')
# Run cells for cleaning, NLP, and plots
```

## 📁 Data Structure
The output CSV includes:
| Column | Description |
|--------|-------------|
| `year` | Post year (extracted from date) |
| `top_caption_word` | Most frequent meaningful word in caption (e.g., "تحفة") |
| `top_comment_word` | Most frequent meaningful word in comments (e.g., "بكام") |
| `dress_style_category` | Classified style (Princess, Modest, Other) |
| `fabrics` | Detected fabrics (e.g., ["Lace", "Chiffon"]) |
| `total_engagement` | Likes + Comments + Shares |
| `likes`, `post_comments_total`, `shares` | Raw metrics |

## 🔍 Key Insights (From Sample Data)
- **Top Keywords**: "تحفة" (masterpiece), "فستان" (dress), "محتشمة" (modest).
- **Trends**: Modesty ratio rising from 20% (2018) to 35% (2024).
- **Engagement**: "Luxury" styles get 2x more likes than "Other".

## ⚠️ Ethical & Legal Notes
- **Instagram ToS**: Only public posts; no private data. Use delays (e.g., `time.sleep(5)`) to avoid rate limits.
- **Privacy**: Anonymize user data; comply with GDPR.
- **Rate Limits**: Instaloader handles this, but monitor for blocks.
- **Alternatives**: For production, use official Instagram Graph API (requires app approval).

## 🤝 Contributing
1. Fork the repo.
2. Create a branch: `git checkout -b feature/add-new-style`.
3. Commit changes: `git commit -m 'Add mermaid style classification'`.
4. Push: `git push origin feature/add-new-style`.
5. Open a Pull Request.

Ideas: Add Selenium for dynamic sites, ML for auto-style detection, or Arabic sentiment analysis.

## 📄 License
MIT License — feel free to use, modify, and distribute. See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments
- Inspired by Egyptian bridal fashion trends on Instagram.
- Tools: Instaloader for scraping, NLTK for NLP, Matplotlib for viz.

## 📞 Contact
- **Portfolio**: [Ahmed El Sany's Portfolio](https://ahmedelsany29.github.io/my-portfolio/)
- **CV**: [Download CV](https://drive.google.com/file/d/1m_8JJHyUvr9ifQ1F7hdhy1Sk-z-J_sb4/view?usp=drive_link)
- **LinkedIn**: [Ahmed El Sany on LinkedIn](https://www.linkedin.com/in/ahmedelsany12)
- **GitHub**: [@ahmedelsany29](https://github.com/ahmedelsany29)
- **Email**: ahmedelsany29@gmail.com (or from LinkedIn)
- Questions? Open an issue!

---

⭐ **Star this repo if it helps your fashion data project!**  
Built with ❤️ for data-driven bridal insights.
