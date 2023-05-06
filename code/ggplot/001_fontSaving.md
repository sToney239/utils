Font saving
================

``` r
sysfonts::font_add("SyHei", "C:\\Users\\sToney\\AppData\\Local\\Microsoft\\Windows\\Fonts\\SourceHanSerifSC-Regular.otf")
# showtext::showtext_begin()
showtext::showtext_auto()
ggsave(here::here("plots/xxxx.jpg"),width = 10,height = 6, dpi = 300)
# showtext::showtext_end()
```
