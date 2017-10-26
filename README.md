# p8105_hw4_hz2510_problem1

Project lead: Huijuan Zhang  
Collaborator: Yeyi Zhang

```{r}
library(tidyverse)
library(janitor)

pups_data = read_csv("./FAS_pups.csv", col_types = "ciiiii") %>%
  clean_names() %>%
  gather('pd_ears', 'pd_eyes', 'pd_pivot', 'pd_walk', key = "pd_outcome", value = "pd_days")

library(ggthemes)

ggplot(pups_data, aes(x = pd_outcome, y = pd_days)) + 
  geom_violin(aes(fill = pd_outcome), color = "blue", alpha = .5) + 
  stat_summary(fun.y = median, geom = "point", color = "blue", size = 2) +
  labs(
    title = "Distribution of post-natal days for Developmental landmarks",
    x = "Post-natal days",
    y = "Developmental landmark"
  ) + 
  theme(legend.position = "bottom")
```

p8105_hw4_hz2510_problem1/problem 1 plot.png
