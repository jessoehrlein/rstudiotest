# Playing with git

## Trying things

Let’s make a graph.

``` r
penguins |>
  select(bill_len, bill_dep, island) |>
  na.omit() |>
  ggplot() +
  aes(x = bill_len, y = bill_dep, color = island) +
  geom_point() +
  geom_smooth(method = "lm", se = FALSE) +
  theme_bw() +
  labs(
    x = "Bill length (mm)",
    y = "Bill depth (mm)"
  )
```

    `geom_smooth()` using formula = 'y ~ x'

![](playing_quarto_files/figure-commonmark/graphity%20graph%20graph-1.svg)

``` r
penguins |>
  select(flipper_len, bill_dep, island) |>
  na.omit() |>
  ggplot() +
  aes(x = flipper_len, y = bill_dep, color = island) +
  geom_point() +
  geom_smooth(method = "lm", se = FALSE) +
  theme_bw() +
  labs(
    x = "Flipper length (mm)",
    y = "Bill depth (mm)"
  )
```

    `geom_smooth()` using formula = 'y ~ x'

![](playing_quarto_files/figure-commonmark/a%20different%20graph-1.svg)

``` r
penguins |>
  group_by(island) |>
  summarize(
          mean_bill_len = mean(bill_len),
          mean_bill_depth = mean(bill_dep)
          )
```

    # A tibble: 3 × 3
      island    mean_bill_len mean_bill_depth
      <fct>             <dbl>           <dbl>
    1 Biscoe             NA              NA  
    2 Dream              44.2            18.3
    3 Torgersen          NA              NA  
