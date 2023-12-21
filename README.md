# Business case



# Virtuaaliympäristön luonti ja käyttö

`/c/Users/emmah/AppData/Local/Programs/Python/Python311/python -m venv --copies .venv`
`source .venv/scripts/activate`  
`deactivate`  

EI ONNISTUNUT EHKÄ

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
**src**
- ohjelmointitavaraa

# Tietokannan luonti 

*dbt init 








