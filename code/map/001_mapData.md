map data
================

## boundary data

``` r
rgeoboundaries::geoboundaries("China", "adm2")

rnaturalearth::ne_countries(type = "countries", country = "Germany",
                     scale = "medium", returnclass = "sf")
```

## climate data

```R
geodata::worldclim_country(country = "Jamaica", var = "tmin",
                       path = tempdir())
chirps::get_chirps(location, dates = c("2020-01-01", "2022-12-31"),
                server = "ClimateSERV")
elevatr::get_elev_raster(locations = map, z = 9, clip = "locations")
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
