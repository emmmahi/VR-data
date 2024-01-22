# Business case



# Virtuaaliympäristön luonti ja käyttö

`/c/Users/emmah/AppData/Local/Programs/Python/Python311/python -m venv --copies .venv`
`source .venv/scripts/activate`  
`deactivate`  

Tuli ongelma dbt buildien kanssa, joten siirryin toisenlaiseen kehitysympäristöön

# DEV CONTAINERIN KÄYTTÖ

- python3
- 3.11bullseye

# Tarvittavia kansioista/filuja

**.gitignore**
````
.venv/
data/
````
**data/**
- alle datalake (staging) ja warehouse (tietokanta)
- tuodaan data tänne alikansioihin VR APIsta

**requirements.txt**
```` 
duckdb==0.9.*       
dbt-duckdb==1.7.*  
ipykernel
polars==0.19.*   
pyarrow==14.0.*
`````

`pip install -r requirements.txt`  

**src**  
- ohjelmointitavaraa

# Tietokannan luonti 

`dbt init dbt_vr`
Syntyy kansio dbt_vr. Luo sinne alle **profiles.yml**

# Katalogin teko tietokannasta

`dbt docs generate`
`dbt docs serve`

----

# VR API https://rata.digitraffic.fi/

**src/playground/get_raw_vrdata.ipynb**

- Tiedot kaikista junista, parametrina päivämäärä(t)
- tiedostot json-muodossa
- "array of lists"

# Raakadata tietokantaan

**src/playground/polars_json_schmea**
- polkujen ja scheman määrittely
- polars df luonti
- yhteys ja vienti tietokantaan
- tulee sourceksi

# Data silverille

Eka tapa (ei näy dbt docsissa): 
**src/playground/data_to_silver.ipynb**
- unnest timetablerows 
- kiinnostus myöhästymisissä 

Toinen tapa:
**dbt_vr\models\silver\vr\method_b_silvertrain.sql**
- SQL-lause on sama kuin toisessa
- `dbt build` toimii ja tulee docsiin näkyviin

# Data goldille

**src\playground\data_to_gold.ipynb**
- eristetään Kajaania koskevat tiedot














