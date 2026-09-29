# Airbnb Price Predictions

Predicting the nightly price of Airbnb listings in New York City from the data Airbnb publishes about them, plus crime and walkability data joined in around each listing. This was a three-week team project and my first machine learning project.

More context is on my portfolio at [billyyork.com](https://billyyork.com).

## Results

The final model, a tuned Random Forest, roughly halved the error of the linear regression baseline:

| Model | MAPE | R² |
| --- | --- | --- |
| Linear regression baseline | 0.629 | 0.410 |
| Tuned Random Forest with NYPD complaint data | 0.311 | 0.537 |

Most of that improvement came from switching model types and adding complaint data from around each listing. The walkability data added less than expected.

## My part

I did the feature engineering. The main idea was to convert each listing's coordinates into polar coordinates, a distance and an angle from a center point, so that "how far from the middle of things is this" becomes a single feature. I tried two versions, one measured from the center of New York City and one from the center of each borough, along with a reviews-per-stay estimate built from reviews per month and each listing's minimum stay. Against the linear baseline, the city-center version made the model slightly worse (R² 0.405), the borough-center version slightly better (0.415), and reviews per stay barely changed anything, though polar coordinates looked more useful once they were reintroduced alongside the Random Forest.

## Running it

The notebook reads its data from `data/`. `listings.csv` is included; the NYPD complaint and walkability data are too large, so [data/Datasets.md](data/Datasets.md) explains where to download them. The notebook expects the NYPD data already filtered down and saved as `data/nypd_complaint_filtered.csv`.

## Team

Built with Peter Clark and Jessica Tanel.

## Data

- Airbnb listings from [Inside Airbnb](https://insideairbnb.com/get-the-data/), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- [NYPD Complaint Data (Historic)](https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i/about_data) from NYC Open Data
- [Walkability Index](https://catalog.data.gov/dataset/walkability-index8) from the EPA
