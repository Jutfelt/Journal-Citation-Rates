# Journal Citation Rates Website

This is the GitHub Pages website for the Journal Citation Rates database.

## Setup

The website is automatically deployed from the `gh-pages` branch to GitHub Pages.

**To enable GitHub Pages:**
1. Go to your repository Settings
2. Navigate to **Pages**
3. Select **Deploy from a branch**
4. Choose `gh-pages` as the source branch
5. Your site will be live at: `https://jutfelt.github.io/Journal-Citation-Rates/`

## File Structure

```
├── index.html                          Landing page with navigation
├── ecophysiology/index.html            23 journals, 1 group, 450 data points
├── ecology-evolution-marine/index.html 103 journals, 9 groups, 2326 data points
├── biology-curated/index.html          94 journals, 0 groups, 2126 data points
├── biology-top-500/index.html          496 journals, 18 groups, 9893 data points
├── tamzins-list/index.html             40 journals, 6 groups, 902 data points
└── .nojekyll                           Disables Jekyll processing
```

## Collections Overview

- **Ecophysiology** - Comparative physiology and ecology journals (23 journals)
- **Ecology, Evolution & Marine** - Ecology, evolution, physiology, behaviour, marine biology, conservation, ecotoxicology and fisheries (103 journals)
- **Biology (Curated)** - Hand-picked cross-section of biology journals (94 journals)
- **Biology Top 500** - Top journals across 18 biology subfields (496 journals)
- **Tamzin's List** - Ecotoxicology and environmental science journals (40 journals)

All collections contain citation rate data spanning 2000-2025.

## Adding Journal Data

Each journal list page can be populated with interactive tables containing:
- Journal names
- Citation rates (by year)
- Impact factors
- Category/group information
- Trend data

To populate the tables, add the journal data to each collection's `index.html` file.
