# Project Structure

```
KEREM-ALCI-DSA-210-PROJECT/
│
├── README.md                          # Main project documentation
├── requirements.txt                   # Python dependencies for the project
├── test_results.py                    # Test/utility script
│
├── analysis/                          # 📊 Analysis scripts and results
│   ├── README.md                      # Analysis folder documentation
│   ├── analyze_data.py                # Main analysis script
│   └── ANALYSIS_SUMMARY.md            # Comprehensive findings and insights
│
├── data/                              # 💾 All data files
│   ├── README.md                      # Data folder documentation
│   │
│   ├── raw/                           # Raw scraped data (unprocessed)
│   │   ├── sahibinden/
│   │   │   ├── sahibinden_enriched_listings.xlsx
│   │   │   ├── sahibinden_local_listings.xlsx
│   │   │   └── sahibinden_local_listings_backup.xlsx
│   │   │
│   │   ├── emlakjet/
│   │   │   ├── emlakjet_listings.xlsx
│   │   │   └── emlakjet_listings_with_coordinates.xlsx
│   │   │
│   │   └── hepsiemlak/
│   │       └── hepsiemlak_listings.xlsx
│   │
│   └── processed/                     # Cleaned and merged data
│       └── combined_rental_data.xlsx  # Final dataset for analysis
│
├── scrapers/                          # 🕷️ Web scraping scripts
│   ├── README.md                      # Scrapers folder documentation
│   │
│   ├── sahibinden/                    # Sahibinden.com scrapers
│   │   ├── requirements.txt           # Specific dependencies
│   │   ├── run_scraper.bat           # Batch script for Windows
│   │   ├── scraper_sahibinden.py     # Main scraper
│   │   └── scraper_sahibinden_uc.py  # Undetected Chrome version
│   │
│   ├── emlakjet/                      # Emlakjet.com scraper
│   │   └── scraper_emlakjet.py
│   │
│   └── hepsiemlak/                    # Hepsiemlak.com scraper
│       └── scraper_hepsiemlak.py
│
└── visualizations/                    # 📈 Generated charts and plots
    ├── README.md                      # Visualizations folder documentation
    ├── analysis_overview.png          # Main analysis visualizations
    ├── distance_analysis.png          # Distance-related plots
    ├── analysis_results.png           # Summary results
    └── merged_analysis_plots.png      # Combined plots

```

## Folder Purposes

### 📊 analysis/
Contains all analysis-related code and documentation. Run `python analyze_data.py` from this folder to perform the complete analysis.

### 💾 data/
- **raw/**: Original scraped data from each website, organized by source
- **processed/**: Cleaned, standardized, and merged datasets ready for analysis

### 🕷️ scrapers/
Web scraping scripts organized by source website. Each subfolder contains the scraper(s) for that specific platform.

### 📈 visualizations/
All generated charts and plots from the analysis. Automatically created/updated when running the analysis script.

## Workflow

1. **Collect Data**: Run scrapers from `scrapers/*/` folders → saves to `data/raw/*/`
2. **Analyze**: Run `python analyze_data.py` from `analysis/` folder
3. **Results**: 
   - Visualizations → saved to `visualizations/`
   - Processed data → saved to `data/processed/`
   - Findings → documented in `analysis/ANALYSIS_SUMMARY.md`

## Notes

- Each major folder contains its own README.md with specific documentation
- All paths in scripts use relative references for portability
- Virtual environment (`.venv/`) and git files (`.git/`) are excluded from version control of data
