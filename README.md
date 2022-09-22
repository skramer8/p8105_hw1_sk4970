#HW 1 - Sara Kramer

## load tidyverse
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

## creating random sample of 10 from st. norm distrib
samp = rnorm(10)

## creating logical vector indiciated whether elements are > 0
norm_samp_pos = samp > 0

## character vector of l = 10, factor vector of l = 10, with diff 'levels'
samp = tibble(
  vec_numeric = 11:20,
  vec_char = c("I", "have", "been", "to", "more", "than", "ten", "countries", "so", "far"),
  vec_logical = c(TRUE, TRUE, TRUE, FALSE, FALSE, TRUE, FALSE, FALSE, TRUE, FALSE),
  vec_factor = factor(c("alone", "family", "family", "friends", "alone", "friend", "friends", "alone", "family", "friends"))
)

## taking the means
mean(samp$vec_numeric)
### mean=15.5

samp %>% 
  pull(vec_char) %>% 
  mean()
### does not work

samp %>% 
  pull(vec_logical) %>% 
  mean()
### mean=0.5

samp %>% 
  pull(vec_factor) %>% 
  mean()
### does not work

eval = FALSE
as.numeric(samp$vec_char)
### get a warning message that it is not possible. Explains why I could not get a mean

as.numeric(samp$vec_logical)
### turns the true/false into 1's and 0's. This is why I could get a mean

as.numeric(samp$factor)
### get a warning message that it is not possible. Explains why I could not get a mean


