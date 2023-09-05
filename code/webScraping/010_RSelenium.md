Web Scrape
================

## Preparation

``` cmd
# run the code in cmd
cd C:\Program Files\R_scripts\selenium
java -jar selenium-server-standalone-4.0.0-alpha-2.jar
```

``` r
library(RSelenium)
library(rvest)
library(tidyverse)


remDr <- remoteDriver(
  remoteServerAddr = "localhost",
  port = 4444L,
  browserName = "firefox"
)


remDr$open()
# set the window size
remDr$setWindowSize(1000,1000)
# change the web site
remDr$navigate("https://cloud.h2os.com/#/album")
```

## Specific Use

### wait for specific element loaded

``` r
waitForLoad <- function(sleepmin=0.5,sleepmax=1){
  remDr <- get("remDr",envir=globalenv())
  webElemtest <-NULL
  while(is.null(webElemtest)){
    webElemtest <- tryCatch({remDr$findElement(using = 'css', ".edit a")},
                            error = function(e){NULL})
  }
  randsleep <- sample(seq(sleepmin, sleepmax, by = 0.001), 1)
  Sys.sleep(randsleep)
}
```

### get path and download file

``` r
downloadFile <- function(i) {
  read_html(remDr$getPageSource()[[1]]) %>% 
    html_element(".edit a") %>% 
    html_attr("href") %>% 
    download.file(paste0("C:\\Users\\sToney\\Desktop\\img\\",i,'.jpg'),
                  method = "curl")
  # get back
  # remDr$executeScript("document.querySelector('div.arr',':before').click();")
}
```

### wrap the whole workflow

``` r
for (i in 816:827) {
  # click the specific element
  remDr$executeScript("document.querySelector('div.photo-right').click();")
    waitForLoad()
  cat(paste0(scales::percent_format()(current_state[1]/current_state[2]),"                                                 "))
  Sys.sleep(0.5)
}
```







```python
#Scroll a little bit to load all the elements
driver.execute_script("window.scrollTo(0, 500);")
 
XPath = "//*[@class='recharts-layer recharts-bar-rectangle']"
bar = driver.find_elements('xpath',XPath)[-1] #Since I want to get the latest data
ActionChains(driver).move_to_element(bar).perform()

#Now get the data
XPATH_TOOLTIP = "//div[@class='PriceHistory--tooltip']"
data = driver.find_element('xpath',XPATH_TOOLTIP).text
print(data)

```
