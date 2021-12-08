# biele

#install.packages('tidyverse')
library(tidyverse)
library(skimr)
# install.packages('janitor')
library(janitor)
#install.packages('ggrepel')
library(ggrepel)
library(car)
# install.packages('nortest')
library(nortest)
require(nlme)
require(mlmRev)
library(sjPlot)
library(glmmTMB)
library(afex)
library(emmeans)
library(multcomp)
# install.packages('multcompView')
library(multcompView)
library(viridis)
# install.packages('hrbrthemes')
library(hrbrthemes)
#install.packages('ggsignif')
library(ggsignif)
#install.packages('ggpubr')
if(!require(devtools)) install.packages("devtools")
devtools::install_github("kassambara/ggpubr")
library(ggpubr)
#install.packages('ggpval')
library(ggpval)


# get working dir 
setwd('xxxxxxxxx')
# check for files in working dir
dir(pattern = '.csv')



# add error bars(SEM) from raw data
p1 + geom_errorbar(data = plot_model,
                   mapping = aes(x = genotype, y = emmean,
                                 ymin = emmean - SE,
                                 ymax = emmean + SE, width = 0.2),
                   position = position_dodge(0.9)) + 
  labs(title = 'XXXXXX',
       y = 'XXXXXXXX',
       x = element_blank(),
       caption = 'bars = mean model\nerrorbars = model\njitter = raw data points\nred triangle = mean exp. data') +
  theme_minimal() + theme(axis.text.x = element_text(angle = 45, hjust = 1)) -> p1

p1 
