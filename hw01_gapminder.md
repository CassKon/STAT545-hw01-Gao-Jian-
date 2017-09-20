---
title: "hw01_gapminder"
output:
  html_document: default
  pdf_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

```{r}
install.packages("gapminder",repos="http://cran.rstudio.com/")
library(gapminder)
str(gapminder)
install.packages("tidyverse",repos="http://cran.rstudio.com/")
library(tidyverse)
head(gapminder)
tail(gapminder)
summary(gapminder)
names(gapminder)
ncol(gapminder)
length(gapminder)
dim(gapminder)
nrow(gapminder)
plot(lifeExp ~ year, gapminder)
plot(lifeExp ~ gdpPercap, gapminder)
plot(lifeExp ~ log(gdpPercap), gapminder)
head(gapminder$lifeExp)
summary(gapminder$lifeExp)
hist(gapminder$lifeExp)
summary(gapminder$year)
table(gapminder$year)
class(gapminder$continent)
summary(gapminder$continent)
levels(gapminder$continent)
nlevels(gapminder$continent)
str(gapminder$continent)
table(gapminder$continent)
barplot(table(gapminder$continent))
## we exploit the fact that ggplot2 was installed and loaded via the tidyverse
p <- ggplot(filter(gapminder, continent != "Oceania"),
            aes(x = gdpPercap, y = lifeExp)) # just initializes
p <- p + scale_x_log10() # log the x axis the right way
p + geom_point() # scatterplot
p + geom_point(aes(color = continent)) # map continent to color
p + geom_point(alpha = (1/3), size = 3) + geom_smooth(lwd = 3, se = FALSE)
p + geom_point(alpha = (1/3), size = 3) + facet_wrap(~ continent) +
  geom_smooth(lwd = 1.5, se = FALSE)
```

## Description on How I made the Gapminder markdown file 
- First I create a new markdown file (HTML) under the project 
- I delete all the description and insert the R script
- I installed the gapminder data set and tidyverse. Then, I anaylsed the data based on the command. 
- I knited the R to preview and after this I commit and pused to Github

## Feedback 
The Rmarkdown is fair and I have seeked for help from youtube and class notes. However, the plot and tables shows up in knitr but disappeared when I upload to the Github.
```



