---
title: "A Comparison of Data Visualisation"
output: 
  html_document: 
    code_folding: hide
    keep_md: yes
    preserve_yaml: false
---

# A comparison of data visualisation on Python and R

In this notebook, I'll show different plot options in both Python and R to show you the basic differences in both coding and plotting. Even though it is theoretically possible to do everything in both; it would consume an unnecessary amount of time. Therefore, we use libraries to make plotting more convenient. 

To explain basic differences simply, I'll explain libraries in one by comparison.

|  Python|  R|
|--:|--:|
|  matplotlib|  Base|
|  Seaborn|  ggplot2|

The reason I'm using this system is, matplotlib is almost at the same level of complexity as native R. It doesn't mean matplotlib is weak, it's just due to R is more suitable for plotting. On the other hand, Seaborn is built on top of matplotlib which provides more beautiful and versatile plots while ggplot is all about giving a user more options. 

Please note that I'm using Python through Reticulate package that is available in R. This could mean some small differences from using the same code in Python. 

### Data

I will use Iris dataset which is publicly available and contains no NA. 

## Seaborn vs ggplot2 Plotting Capabilities.












```r
library(ggplot2)

scatter <- ggplot(data=iris, aes(x = Sepal.Length, y = Sepal.Width)) 
scatter + geom_point(aes(color=Species, shape=Species), size=3) +
  xlab("Sepal Length") +  ylab("Sepal Width") +
  ggtitle("A gglot2 Scatterplot")
```

![](visualisation_comparison_files/figure-html/unnamed-chunk-3-1.png)<!-- -->



```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

iris_pd = r.iris

ax = sns.scatterplot(x='Sepal.Length', y='Sepal.Width', data=iris_pd, hue="Species", style="Species")
ax.set_title("A Seaborn Scatterplot")
```

<img src="visualisation_comparison_files/figure-html/unnamed-chunk-4-1.png" width="672" />


