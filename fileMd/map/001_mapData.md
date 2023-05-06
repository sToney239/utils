map data
================

## boundary data

``` r
rgeoboundaries::geoboundaries("China", "adm2")
```

## geocoding

``` r
tidygeocoder::geocode(city, method = 'osm', lat = lat , long = lon)
```

## read geojson

``` r
states_json <- geojsonio::geojson_json(
  states, 
  geometry = "polygon", 
  group = "group"
)
```
