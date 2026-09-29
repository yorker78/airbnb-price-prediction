
**Datasets & How to Download**

- **NYPD Complaint Data (Historic)**: https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i/about_data
	- Open the link, click **Export → CSV** to download the full CSV.
    - Save the file to `data/nypd_complaint.csv`
	- Notes: file can be large (millions of rows). If you need a subset, consider filtering afterwards or using the API to apply conditionals before downloading.

- **Walkability Index (Walkability-Index8)**: https://catalog.data.gov/dataset/walkability-index8
	- Open the data.gov page, follow the dataset links under **Access & Use** or **Download** to get the distribution file(s).
    - Click the distribution link to download or copy the direct download URL.
	- Save the file to `data/Natl_WI.gdb` after unzipping.

- **InsideAirbnb — Get the Data**: https://insideairbnb.com/get-the-data/
	- Open the page, choose the city (New York City) and the snapshot date you want, then download
    - Save the file to `data/listings.csv`.
