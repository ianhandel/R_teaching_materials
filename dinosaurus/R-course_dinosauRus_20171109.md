# DinosauRus





From (https://www.autodeskresearch.com/publications/samestats)

## The dataset...

```r
datasaurus_dozen
```

```
## # A tibble: 1,846 x 3
##    dataset       x       y
##      <chr>   <dbl>   <dbl>
##  1    dino 55.3846 97.1795
##  2    dino 51.5385 96.0256
##  3    dino 46.1538 94.4872
##  4    dino 42.8205 91.4103
##  5    dino 40.7692 88.3333
##  6    dino 38.7179 84.8718
##  7    dino 35.6410 79.8718
##  8    dino 33.0769 77.5641
##  9    dino 28.9744 74.4872
## 10    dino 26.1538 71.4103
## # ... with 1,836 more rows
```

## Summary statistics


```r
summary_stats <- datasaurus_dozen %>% 
  group_by(dataset) %>% 
  mutate_at(vars(x, y), funs(mean, sd)) %>% 
  mutate(cor = cor(x, y)) %>% 
  select(-x, -y) %>% 
  distinct() %>% 
  mutate_if(is_double, round, 2)

kable(summary_stats, format = "html")
```

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> dataset </th>
   <th style="text-align:right;"> x_mean </th>
   <th style="text-align:right;"> y_mean </th>
   <th style="text-align:right;"> x_sd </th>
   <th style="text-align:right;"> y_sd </th>
   <th style="text-align:right;"> cor </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> dino </td>
   <td style="text-align:right;"> 54.26 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.06 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> away </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.06 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> h_lines </td>
   <td style="text-align:right;"> 54.26 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.06 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> v_lines </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> x_shape </td>
   <td style="text-align:right;"> 54.26 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.93 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> star </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.93 </td>
   <td style="text-align:right;"> -0.06 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> high_lines </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> dots </td>
   <td style="text-align:right;"> 54.26 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.93 </td>
   <td style="text-align:right;"> -0.06 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> circle </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.76 </td>
   <td style="text-align:right;"> 26.93 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> bullseye </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> slant_up </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> slant_down </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.84 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> wide_lines </td>
   <td style="text-align:right;"> 54.27 </td>
   <td style="text-align:right;"> 47.83 </td>
   <td style="text-align:right;"> 16.77 </td>
   <td style="text-align:right;"> 26.94 </td>
   <td style="text-align:right;"> -0.07 </td>
  </tr>
</tbody>
</table>

## Scatter plots


```r
ggplot(datasaurus_dozen, aes(x, y, colour = dataset)) +
  geom_point() +
  facet_wrap(~ dataset) +
  theme(legend.position = "none") +
  labs(x = NULL, y = NULL)
```

![](R-course_dinosauRus_20171109_files/figure-html/unnamed-chunk-4-1.png)<!-- -->
