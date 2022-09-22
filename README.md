# p8105_hw1_sk4970

# load tidyverse
library(tidyverse)

# PROBLEM 1
## install package
install.packages("palmerpenguins")

## loading dataset
data("penguins", package = "palmerpenguins")

## viewing dataset
view("penguins")

### dataset includes 8 variables: penguin species, island where the penguin is located, sex (male or female), bill length (mm), bill depth (mm), flipper length (mm), body mass (g), and year data was collected (2007-2009)

### There are 344 points of data

### mean flipper length=200.92 mm

## making a scatter plot of flipper lenth (mm) as the y and bill length (mm) as the x
ggplot(penguins, aes(x = bill_length_mm, y = flipper_length_mm)) + geom_point()

## save scatter plot
ggsave("penguin_scatter_plot.pdf")


# PROBLEM 2 

## c




