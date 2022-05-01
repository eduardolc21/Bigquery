### Selecting Peru in a column ### 

```
SELECT * FROM `bigquery-public-data.covid19_ecdc_eu.covid_19_geographic_distribution_worldwide`
WHERE 
countries_and_territories = 'Peru'
```
### When was the worst COVID day in Peru, regarding daily_confirmed cases ##

```
SELECT date, daily_confirmed_cases
FROM `bigquery-public-data.covid19_ecdc_eu.covid_19_geographic_distribution_worldwide`
WHERE daily_confirmed_cases = (
  SELECT MAX(daily_confirmed_cases) FROM `bigquery-public-data.covid19_ecdc_eu.covid_19_geographic_distribution_worldwide` WHERE countries_and_territories = 'Peru'
)
```

### How many years does this COVID dataset refered to?

```
SELECT distinct(year) 
FROM `bigquery-public-data.covid19_ecdc_eu.covid_19_geographic_distribution_worldwide`
WHERE countries_and_territories = 'Peru'
```

