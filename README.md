# __INTRODUCTION__

With the climate rapidly changing and humans having increasing impact on global ecosystems, today it is not longer sufficient to classify and analyse ecosystems based on their geographical location and historical data. Here, we classify ecosystems based on their wider geoecological parameters. The goal is to create a classifier that allows us to dynamically classify ecosystems. Perspectively, used to predict i.e. expected species richness, species extinction rates, soil status, soil detioration and eventually ecosystem collapse. <br>

### Project objective

**Minimal viable product (MVP):** On [EcoVerse](link.to.website) we show the development of ecosystems over time.

**Goal:** Showing a trend of ecosystem development and migration over time

**Validation:** Highlighting renaturation efforts of the past decade such as [Great Green Wall Initiative](https://www.unccd.int/our-work/ggwi), [Chinese Loess Plateau Rehabilitation](https://sustainabledevelopment.un.org/content/dsd/dsd_aofw_mg/mg_success_stories/csd8/SARD-16.htm) and the [Netherlands’ Marker Wadden](https://www.ecoshape.org/en/cases/marker-wadden/)



### Disclaimer

This project is designed and pursued in the context of the *Data Analytics Consulting Bootcamp 2024-2* from *neuefische GmbH*. During which a capstone project is to be designed for the timeframe of four weeks, including setup, data retrieval, analysis and integration.

**Collaborators:** 
|Member|Role|
|-|-|
|[Heiko Främbs](https://github.com/HeikoFrae)|Communications <br> Project management|
|[Soma	Pasumarthy](https://github.com/pasumaso/pasumaso)|Web integration <br> Database maintainance|
|[Alexander Schmidt](https://github.com/aschmidtphil/aschmidtphil)|Data acquisition <br> Data handling|
|[Noah Kürtös](https://github.com/NoahKuertoes)|Conceptualization <br> Scripts|

**About the repository:** Collabotors ought to work in independent branches and merge into main need to be approved by at least one other collabotor. For team communications this [miro board](https://miro.com/app/board/uXjVLRd7MDI=/?share_link_id=695364651737) is used.

# __DATA__

<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
    <th>Content</th>
    <th>Data URL</th>
    <th>Notes</th>
  </tr>
  <tr>
    <td rowspan="5"><a href="https://www.earthdata.nasa.gov/">EarthData</a></td>
    <td rowspan="5">Library of accumulated satellite data</td>
    <td rowspan ="2">Radiation based climate data (detailed <a href=https://hydro1.gesdisc.eosdis.nasa.gov/data/GLDAS/GLDAS_NOAH025_M.2.1/doc/README_GLDAS2.pdf>here </a>)</td>
    <td><a href="https://disc.gsfc.nasa.gov/datasets/GLDAS_NOAH025_M_2.1/summary">GLDAS Noah Land Surface Model L4 monthly 0.25 x 0.25 degree V2.1 (GLDAS_NOAH025_M)</a></td>
    <td>From 2000-2024</td>
  </tr>
  <tr>
    <td><a href="https://disc.gsfc.nasa.gov/datasets/GLDAS_NOAH025_M_2.0/summary">GLDAS Noah Land Surface Model L4 monthly 0.25 x 0.25 degree V2.0 (GLDAS_NOAH025_M)</a></td>
    <td>From 1948-2014</td>
  </tr>
  <td>Elevation data relative </td>
  <td><a href=https://asterweb.jpl.nasa.gov/gdem.asp>ASTER Advanced Spaceborne Thermal Emission and Reflection Radiometer </a></td>
  <td>From 2009 as <code>.geotif<code> </td>
  </tr>
  <td> Night time illumination data</td>
  <td><a href=https://ladsweb.modaps.eosdis.nasa.gov/missions-and-measurements/products/VNP46A1/>VNP46A1 - VIIRS/NPP Daily Gridded Day Night Band 500m Linear Lat Lon Grid Night </a></td>
  <td>From 2012 onward as <code>.geotif<code> <br> <a href=https://ladsweb.modaps.eosdis.nasa.gov/api/v2/content/archives/Document%20Archive/Science%20Data%20Product%20Documentation/VIIRS_Black_Marble_UG_v1.3_Sep_2022.pdf> Black marble </td>
  </tr>
  <td> Vegetation index (NDVI)</td>
  <td><a href=https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD13A2>MOD13A2.061 Terra Vegetation Indices 16-Day Global 1km  </a></td>
  <td>Earth engine snippets as <code>.geotif<code>  </td>
  </tr>
  <tr>
    <td><a href=https://dashboard.dataspace.copernicus.eu> Copernicus </a></td>
    <td>Sentinel mission satellite data. 90m global resolution (TanDEM-X mission)</td>
    <td>Elevation data absolute </td>
    <td><a href=https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM> Copernicus DEM - Global and European Digital Elevation Model  </a></td>
    <td>Mission: from 2011-2015.<br> Data availble: from 2019-2026 <br> Earth engine snippets as <code>.geotif<code></td>
  </tr>
  <tr>
    <td> <b>DEPRECIATED<b> <br> <a href="https://www.meteostat.net/">Meteostat</a></td>
    <td>Library of global weatherstations</td>
    <td> Weather data </td>
    <td>Data is sourced through the python library <code>meteostat</code> <a href=https://meteostat.net/en/blog/analyze-historical-weather-data-python>(documentation)</a></td>
    <td>Representation bias towards EU and NA</td>
  </tr>
    <tr>
    <td> <b>DEPRECIATED<b> <br> <a href="https://open-elevation.com/">Open elevation</a></td>
    <td>Free API alterntavie to Google</td>
    <td> Elevation data absolute </td>
    <td>Data is sourced through the API <a href="scripts/open_elevation_request.py">open_elevation_request.py</a> </td>
    <td>Open elevation data doesn't feature data from <code>lat > 60°<code> </td>
  </tr>
</table>

---

# __WORKFLOW__

## 1. Literature research

NASA's [EarthData](https://www.earthdata.nasa.gov/) features a wide range of global satellite data which can be used to infer climate paramters. These parameters are already widely used for local studies featured in their ["News"](https://www.earthdata.nasa.gov/news) section. Moreover, there is a ["Global Ecosystem Viewer"](https://rmgsc.cr.usgs.gov/ecosystems/dataviewer.shtml) from the [United states geological survey](https://www.usgs.gov/) for global ecosystems (27.10.2016). 

Hence, the focus of this project was to integrate and automate the classification of ecosystems using dynamically updated satellite data.

## 2. Data acquisition and storage

All data is acquired through EarthData or through the GoogleEarth engine. The data is stored on an AWS postgreSQL server. Currently migrating. 

### 2.1 Exemplary visualisation of input data

1.) *VIIRS* night time illumination

![image](https://github.com/user-attachments/assets/64901a8b-13ee-469e-b9b4-165d236c13b9)

---

2.) *MODIS* vegetation index 

![image](https://github.com/user-attachments/assets/362c6f73-69bc-4bfa-9429-436374585388)

---

3.) *Copernicus* elevation data

![image](https://github.com/user-attachments/assets/7b5c0f56-360c-40e2-9351-8c0866b568ea)


## 3. Modelling 

For modelling all parameters were aggregated for each grid cell and a model was trained on 73 different locations of 15 different ecosystems using `RandomForestClassifier` from `sklearn`.

```
label_encoder = LabelEncoder()
scaler = StandardScaler()

#define model data
X = df.drop(columns=["ecosystem", "name"])
y = label_encoder.fit_transform(df["ecosystem"])

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

#split data
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

#modelling
model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)
```

### 3.1 Training data (2020)

![image](https://github.com/user-attachments/assets/9a3f938b-aac0-4050-a140-53f5cf34da81)

### 3.2 Classification (2012)

![image](https://github.com/user-attachments/assets/94658c5a-c612-4de1-8781-79424dd4cd11)


## 4. Forecasting

For forecasting `LinearRegression` from `sklearn` was performed for each parameter per grid cell individually.

```
# Prepare data for the model
X, y = np.array(df_pixel["year"]).reshape(-1, 1), np.array(df_pixel[parameter])

# Check if there is enough data to fit the model
if len(X) > 1:
    # Fit the model and calculate R-squared
    model.fit(X, y)
    r_squared = model.score(X, y)
    predict_val = model.predict(np.array([[predict_year]]))[0]  # Extract single value
```

### 4.1 Classification of forecast for 2030

![image](https://github.com/user-attachments/assets/e46a7b0a-475c-4b60-b6ca-9a0816167f44)

### 4.1 Classification of forecast for 2100

![image](https://github.com/user-attachments/assets/4613cb37-1e20-4aad-bb41-f755159b70fd)





