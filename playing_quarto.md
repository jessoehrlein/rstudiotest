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

![](playing_quarto_files/figure-commonmark/graphity%20graph%20graph-1.png)
