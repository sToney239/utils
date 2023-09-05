``` R
library(cowplot)
ggdraw()+
  draw_plot(p1, scale = 0.9, x = 0.02,y = 0, width = 0.5, height = 1)+
  draw_plot(p2, scale = 0.9, x = 0.44,y = 0, width = 0.5, height = 1)
```



```R
library(aplot)
library(ggplotify)
aplot::plot_list(ggplotify::as.ggplot(p, angple = 45, scale = 1.02))
```



```R
library(aplot)
ao <- p %>%
  insert_top(p2, height = 0.3) +
  insert_top(p3, width = 0.1)
```
