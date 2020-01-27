``` r
view(gapminder)
```

``` r
ggplot(data = gapminder) +
  geom_point(mapping = aes(x = pop, y = lifeExp))
```

![](participation_2_files/figure-markdown_github/basic%20ggplot-1.png)

``` r
ggplot(data = gapminder, aes(x = gdpPercap, y = lifeExp, colour = continent, size = pop))+
  geom_point() 
```

![](participation_2_files/figure-markdown_github/aestheic%20color%20option-1.png)

``` r
ggplot(data = gapminder) +
  geom_point(mapping = aes(x = pop, y = lifeExp)) +
  facet_wrap(~  continent, nrow = 2)
```

![](participation_2_files/figure-markdown_github/faceting-1.png)

``` r
ggplot(data = gapminder) +
  geom_smooth(mapping = aes(x = pop, y = lifeExp))
```

    ## `geom_smooth()` using method = 'gam' and formula 'y ~ s(x, bs = "cs")'

![](participation_2_files/figure-markdown_github/smoothed%20line-1.png)

``` r
ggplot(data = gapminder, mapping = aes(x = continent, y = lifeExp))+
  stat_summary(fun.ymin = min, 
               fun.ymax = max, 
               fun.y = median,
               alpha = .9) +
  geom_point() + 
  coord_flip() 
```

![](participation_2_files/figure-markdown_github/flipping%20coordinate%20system-1.png)

``` r
ggplot(data = gapminder, aes(x = gdpPercap, y = lifeExp))+
  geom_point() +
  scale_x_log10() 
```

![](participation_2_files/figure-markdown_github/log%20scale-1.png)
