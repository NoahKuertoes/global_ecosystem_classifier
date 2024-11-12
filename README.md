# __INTRODUCTION__

With the climate rapidly changing and humans having increasing impact on global ecosystems, today it is not longer sufficient to classify and analyse ecosystems based on their geographical location. In this study we aim to seek factors to classify ecosystems based on their wider geoecological parameters. The goal is to create a classifier that allows us to dynamically classify ecosystems to predict expected values as i.e. species richness, species extinction rates, soil status, soil detioration and eventually ecosystem collapse <br>

### Project objective

**Minimal viable product (MVP):** [Website](link.to.website) that shows the development of ecosystems over time.

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
|[Noah Kürtös](https://github.com/NoahKuertoes)|Conceptualization <br> Research and conclusions|

**Rules:** Collabotors ought to work in independent branches and merge into main need to be approved by at least one other collabotor

**Tools:** For team communications this [miro board](https://miro.com/app/board/uXjVLRd7MDI=/?share_link_id=695364651737) is used

**Data sources**
<table>
  <tr>
    <th>Name</th>
    <th>Content</th>
    <th>Data URL</th>
    <th>Notes</th>
  </tr>
  <tr>
    <td rowspan="2"><a href="https://www.earthdata.nasa.gov/">EarthData</a></td>
    <td rowspan="2">Library of accumulated satellite data</td>
    <td><a href="https://disc.gsfc.nasa.gov/datasets/GLDAS_NOAH025_M_2.1/summary">GLDAS Noah Land Surface Model L4 monthly 0.25 x 0.25 degree V2.1 (GLDAS_NOAH025_M)</a></td>
    <td>From 2000-2024</td>
  </tr>
  <tr>
    <td><a href="https://disc.gsfc.nasa.gov/datasets/GLDAS_NOAH025_M_2.0/summary">GLDAS Noah Land Surface Model L4 monthly 0.25 x 0.25 degree V2.0 (GLDAS_NOAH025_M)</a></td>
    <td>From 1948-2014</td>
  </tr>
  <tr>
    <td><a href="https://www.meteostat.net/">Meteostat</a></td>
    <td>Library of global weatherstations</td>
    <td>Data is sourced through the python library <code>meteostat</code> <a href=https://meteostat.net/en/blog/analyze-historical-weather-data-python>(documentation)</a></td>
    <td>Representation bias towards EU and NA</td>
  </tr>
  <tr>
    <td><a href="https://www.iucnredlist.org/">IUC Red List</a></td>
    <td>List of endangered species</td>
    <td></td>
    <td></td>
  </tr>
</table>

---

# __WORKFLOW__

## 1. Literature research

20241018: 

Relevant files are stored in the `/papers` directory named as `<year>_<authors>_<shorttitle>.pdf` 


## 2. Data acquisition

## 3. Modelling 

## 4. Web integration

## 5. (Optional) Parameter prediction


