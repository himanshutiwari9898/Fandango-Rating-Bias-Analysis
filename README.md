# Fandango Ratings Bias Analysis
🔍 Project Overview

This analysis investigates whether Fandango displays inflated movie ratings compared to other popular review platforms such as Rotten Tomatoes, Metacritic, and IMDb.

The motivation comes from public criticism that Fandango rounds and boosts ratings to encourage ticket sales. Using real movie rating data, this project validates that claim using data normalization, visual analysis, and worst-case inspection.

 ## Methodology
##  Data Sources

Fandango ratings (STARS & displayed RATING)

Rotten Tomatoes (Critics & Users)

Metacritic (Critics & Users)

IMDb (User ratings & vote counts)

Only movies present across all platforms were compared using an inner merge to ensure fairness.


## Normalization (0–5 Scale)

Since platforms use different rating scales, all ratings were normalized to a 0–5 star scale:

Platform	Original Scale	Normalization
Rotten Tomatoes	0–100	÷ 20
Metacritic	0–100	÷ 20
IMDb	0–10	÷ 2
Fandango	0–5	unchanged


## Distribution Comparison
KDE & Histogram Analysis

Kernel Density Estimation (KDE) and histogram plots reveal that:

Fandango ratings are heavily skewed toward 4–5 stars

Other platforms show a broader and more realistic spread

Low ratings are almost absent on Fandango

📸 Screenshots:

analysis/03_kde_all_sites.png

analysis/04_hist_all_sites.png

## Correlation & Clustering
Heatmap

A correlation heatmap shows that while platforms broadly agree on movie quality, Fandango consistently rates higher, especially for poorly reviewed films.

Clustermap

Clustering normalized ratings groups movies into:

Highly rated movies

Poorly rated movies

Even in the worst movie cluster, Fandango ratings remain unusually high.

## Worst Movies Analysis
Bottom 10 Movies (by Rotten Tomatoes Critics)

The 10 lowest-rated movies according to Rotten Tomatoes critics were extracted and compared across platforms.

Findings:

Critics & users rate these movies between 0–2 stars

IMDb and user ratings are modest (2–3)

Fandango still shows 3.5–4.5 stars

## Case Study: Taken 3 (2015)
Platform	Normalized Rating
RT Critics	0.4
RT Users	2.3
Metacritic	1.3
Metacritic Users	2.3
IMDb	3.0
Fandango STARS	4.5
Fandango RATING	4.1

Despite an average rating of ~1.86 across other platforms, Fandango prominently displays 4.5 stars.

# Final Conclusion

This analysis provides strong, data-driven evidence that:

Fandango ratings are systematically inflated

Poorly reviewed movies are presented as “good”

The bias is consistent across distributions, correlations, and worst-case scenarios

📌 Key Takeaway

When bad movies still look good, the rating system is broken.
