# GAM

---

[An introduction to GAM(M)s](https://stefanocoretta.github.io/gamm-workshop/)

## gam中的平滑

#### `bs="re"`

 - `s(location, bs = "re")`相当于 `(1|location)`
 - `s(location, by = species, bs = "re")`get a random intercept for the groups formed by the interaction of location and species
 - `s(temperature, group, bs = "re")`相当于`(0 + temperature | group)`

```r
s(group, bs = "re") + s(temperature, group, bs = "re")  #gam
(1 | group) + (0 + temperature | group)                 #glm
# maybe shorthand (temperature || group)
```

#### `bs = "fs"`

`s(year, station, bs = "fs")` 相当于 `year:station`
`t2(x, f, bs = c('cr','re'), full = TRUE)`

```R
# GS (Global smoother | individual effects | Shared penalty)
log(uptake) ∼ s(log(conc), k=5, m=2) +
           s(log(conc), Plant_uo, k=5, bs="fs", m=2)
# GI (Global smoother | individual effects | Individual penalties)
log(uptake) ∼ s(log(conc), k=5, m=2, bs="tp") +
          s(log(conc), by=Plant_uo, k=5, m=1, bs="tp") +
          s(Plant_uo, bs="re", k=12)
# note "re"(random effect) part
# note m=1 and m=2
```





## [案例](https://stats.stackexchange.com/questions/451218/specifying-hierarchical-gam-for-ecological-count-data-annual-bird-migration-co)

```r
modGS <- bam( # used bam() to speed things up
  count ~
    s(doy) +
    s(doy, year, bs = "fs") +
    offset(log(minutes)), # account for daily observer effort
  data = df,
  method = "fREML",
  family = nb()
)
```


year discrete

```r
s(doy) + 
## first order effects
s(species, bs = 're') + s(year, bs = 're') + s(site, bs = 're') +
## second & third order random effects
s(site, species, bs = 're') +
s(year, site, species, bs = 're') +

s(year, site, bs = 're') +
s(year, species, bs = 're') +
## second order functional effects
s(doy, site, bs = 'fs') +
s(doy, species, bs = 'fs') +
s(doy, year, bs = 'fs') +
## higher order functional effects
t2(doy, species, year, bs = c('cr', 're', 're'), full = TRUE) +
t2(doy, species, site, bs = c('cr', 're', 're'), full = TRUE) +
t2(doy, site, year, bs = c('cr', 're', 're'), full = TRUE) +
t2(doy, species, site, year, bs = c('cr', 're', 're', 're'), full = TRUE)
```

year continuous

```r
s(doy) + 
## first order random effects
s(species, bs = 're') + s(year) + s(site, bs = 're') +
## second & third order random effects
s(site, species, bs = 're') +
ti(year, site, species, bs = c('cr', 're', 're')) +
## second order functional effects
s(doy, site, bs = 'fs') +
s(doy, species, bs = 'fs') +
ti(doy, year) +

s(year, site, bs = 'fs') +
s(year, species, bs = 'fs') +
## higher order functional effects
ti(doy, year, species, bs = c('cr', 'cr', 're')) +
ti(doy, species, site, bs = c('cr', 're', 're')) +
ti(doy, year, site, bs = c('cr', 'cr', 're')) +
ti(doy, year, species, site, bs = c('cr', 'cr', 're', 're'))

```


If you had more sites over a range of lat and long, you could also model the spatial effect via a spatial smooth `s(long, lat, bs = 'ds')` for example.