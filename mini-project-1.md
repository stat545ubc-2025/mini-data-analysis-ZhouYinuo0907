# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.2
    ## ✔ ggplot2   4.0.0     ✔ tibble    3.3.0
    ## ✔ lubridate 1.9.4     ✔ tidyr     1.3.1
    ## ✔ purrr     1.1.0     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2024>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/158528/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2024 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R.html)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: *parking_meters*

2: *cancer_sample*

3: *steam_games*

4: *vancouver_trees*

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

``` r
##First, I'll use glimpse to get an overview of each dataset and see the class type of it.
  class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
  glimpse(steam_games)
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
##I'm interested in the discount pattern of games, so I'll then use summarise to see the number of missing data and the maximum and minimum values of the price before and after discount.

steam_games %>%
 summarise(
   n_NA_original_price = sum(is.na(original_price)),
   n_NA_discount_price = sum(is.na(discount_price)), 
   max_origanal = max(original_price, na.rm = TRUE), 
   min_original = min(original_price, na.rm = TRUE), 
   max_discount = max(discount_price, na.rm = TRUE), 
   min_discount = min(discount_price, na.rm = TRUE))
```

    ## # A tibble: 1 × 6
    ##   n_NA_original_price n_NA_discount_price max_origanal min_original max_discount
    ##                 <int>               <int>        <dbl>        <dbl>        <dbl>
    ## 1                5353               26290       730640            0         963.
    ## # ℹ 1 more variable: min_discount <dbl>

``` r
#I'm particularly interested in the well-received games, so I'm using mutate to create a new variable based on the reviews.
steam_games <- steam_games %>%
  mutate(review_level = case_when(
      grepl("^Very Positive", all_reviews) ~ "Very Positive",
      grepl("^Positive", all_reviews)      ~ "Positive",
      grepl("^Mixed", all_reviews)         ~ "Mixed",
      TRUE                                 ~ "Other" ))
```

``` r
#I'm now going to see the mean price of games grouped by review levels I just created.
steam_games %>%
  group_by(review_level)%>%
  summarise(mean_original_price = mean(original_price, na.rm = TRUE ))
```

    ## # A tibble: 4 × 2
    ##   review_level  mean_original_price
    ##   <chr>                       <dbl>
    ## 1 Mixed                        16.0
    ## 2 Other                        45.4
    ## 3 Positive                    202. 
    ## 4 Very Positive                15.0

``` r
#Now, I'll take a glimpse at vancouver_trees.
 glimpse(vancouver_trees)
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

``` r
 class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
#I'll explore the general features of the trees grouped by species, using the summarise grammar.
vancouver_trees %>%
  group_by(species_name) %>% 
  summarise(
    mean_height = mean(height_range_id), 
    mean_diameter = mean(diameter))
```

    ## # A tibble: 283 × 3
    ##    species_name   mean_height mean_diameter
    ##    <chr>                <dbl>         <dbl>
    ##  1 ABIES                 3.28         12.9 
    ##  2 ACERIFOLIA   X        4.63         20.8 
    ##  3 ACUMINATA             2.57         10.9 
    ##  4 ACUTISSIMA            2.76          8.87
    ##  5 AILANTHIFOLIA         5            32   
    ##  6 ALBA                  3.12         19.4 
    ##  7 ALBA-SINENSIS         2.67          8.67
    ##  8 ALNIFOLIA             1.77          5.23
    ##  9 ALPINUM               2             8   
    ## 10 ALTISSIMA             3.5          15.9 
    ## # ℹ 273 more rows

``` r
#I'm also interested in the number and diversity of trees in different neighbourhoods.

vancouver_trees %>%
  group_by(neighbourhood_name) %>% 
  summarise(
    n_trees = n(),                            
    n_species = n_distinct(species_name))
```

    ## # A tibble: 22 × 3
    ##    neighbourhood_name       n_trees n_species
    ##    <chr>                      <int>     <int>
    ##  1 ARBUTUS-RIDGE               5169       121
    ##  2 DOWNTOWN                    5159        79
    ##  3 DUNBAR-SOUTHLANDS           9415       161
    ##  4 FAIRVIEW                    4002       119
    ##  5 GRANDVIEW-WOODLAND          6703       146
    ##  6 HASTINGS-SUNRISE           10547       176
    ##  7 KENSINGTON-CEDAR COTTAGE   11042       159
    ##  8 KERRISDALE                  6936       138
    ##  9 KILLARNEY                   6148       122
    ## 10 KITSILANO                   8115       171
    ## # ℹ 12 more rows

``` r
#Now, I'll get started with parking_meters.
class(parking_meters) 
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
glimpse(parking_meters)
```

    ## Rows: 10,032
    ## Columns: 22
    ## $ meter_head     <chr> "Twin", "Pay Station", "Twin", "Single", "Twin", "Twin"…
    ## $ r_mf_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_mf_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_sa_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_sa_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ r_su_9a_6p     <chr> "$2.00", "$1.00", "$1.00", "$1.00", "$2.00", "$2.00", "…
    ## $ r_su_6p_10     <chr> "$4.00", "$1.00", "$1.00", "$1.00", "$1.00", "$1.00", "…
    ## $ rate_misc      <chr> NA, "$ .50", NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ time_in_effect <chr> "METER IN EFFECT: 9:00 AM TO 10:00 PM", "METER IN EFFEC…
    ## $ t_mf_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_mf_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_sa_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_sa_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ t_su_9a_6p     <chr> "2 Hr", "10 Hrs", "2 Hr", "2 Hr", "2 Hr", "3 Hr", "2 Hr…
    ## $ t_su_6p_10     <chr> "4 Hr", "10 Hrs", "4 Hr", "4 Hr", "4 Hr", "4 Hr", "4 Hr…
    ## $ time_misc      <chr> NA, "No Time Limit", NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ credit_card    <chr> "No", "Yes", "No", "No", "No", "No", "No", "No", "No", …
    ## $ pay_phone      <chr> "66890", "59916", "57042", "57159", "51104", "60868", "…
    ## $ longitude      <dbl> -123.1289, -123.0982, -123.1013, -123.1862, -123.1278, …
    ## $ latitude       <dbl> 49.28690, 49.27215, 49.25468, 49.26341, 49.26354, 49.27…
    ## $ geo_local_area <chr> "West End", "Strathcona", "Riley Park", "West Point Gre…
    ## $ meter_id       <chr> "670805", "471405", "C80145", "D03704", "301023", "5913…

``` r
#I'd like to know the number of each type of parking meters and whether they accept credit card.
parking_meters %>%
  group_by(meter_head, credit_card)%>%
  summarise(n= n())
```

    ## `summarise()` has grouped output by 'meter_head'. You can override using the
    ## `.groups` argument.

    ## # A tibble: 13 × 3
    ## # Groups:   meter_head [7]
    ##    meter_head          credit_card     n
    ##    <chr>               <chr>       <int>
    ##  1 Pay Station         Yes           314
    ##  2 Pay Station         <NA>           12
    ##  3 Single              No            634
    ##  4 Single              Yes           121
    ##  5 Single / Disability No             66
    ##  6 Single / Disability Yes            12
    ##  7 Single / Disability <NA>            4
    ##  8 Single Motorbike    No            152
    ##  9 Twin                No           7369
    ## 10 Twin                Yes          1245
    ## 11 Twin / Disability   No              4
    ## 12 Twin / Disability   Yes             4
    ## 13 Twin Bay Single     Yes            95

``` r
#I'm also interested in the distribution of parking meters in different areas.

parking_meters %>%
  group_by(geo_local_area)%>%
  summarise(n= n())
```

    ## # A tibble: 18 × 2
    ##    geo_local_area               n
    ##    <chr>                    <int>
    ##  1 Arbutus-Ridge              148
    ##  2 Downtown                  3771
    ##  3 Fairview                  1624
    ##  4 Grandview-Woodland         312
    ##  5 Hastings-Sunrise             7
    ##  6 Kensington-Cedar Cottage    50
    ##  7 Kerrisdale                 139
    ##  8 Killarney                   32
    ##  9 Kitsilano                  920
    ## 10 Mount Pleasant             898
    ## 11 Renfrew-Collingwood         43
    ## 12 Riley Park                 280
    ## 13 Shaughnessy                 15
    ## 14 South Cambie                91
    ## 15 Strathcona                 508
    ## 16 Sunset                      77
    ## 17 West End                   940
    ## 18 West Point Grey            177

``` r
#I'll explore cancer_sample now.
 class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
 glimpse(cancer_sample)
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

``` r
#I'll see some of the mean features based on the diagnosis.
cancer_sample %>%
  group_by(diagnosis)%>%
  summarise(
    mean_radius = mean(radius_mean),
    mean_texture = mean(texture_mean),
    mean_perimeter = mean(perimeter_mean),
    mean_area = mean(area_mean))
```

    ## # A tibble: 2 × 5
    ##   diagnosis mean_radius mean_texture mean_perimeter mean_area
    ##   <chr>           <dbl>        <dbl>          <dbl>     <dbl>
    ## 1 B                12.1         17.9           78.1      463.
    ## 2 M                17.5         21.6          115.       978.

``` r
#I'll also see some of the worst features based on the diagnosis.
cancer_sample %>%
  group_by(diagnosis)%>%
  summarise(
    mean_w_radius = mean(radius_worst),
    mean_w_texture = mean(texture_worst),
    mean_W_perimeter = mean(perimeter_worst),
    mean_w_area = mean(area_worst))
```

    ## # A tibble: 2 × 5
    ##   diagnosis mean_w_radius mean_w_texture mean_W_perimeter mean_w_area
    ##   <chr>             <dbl>          <dbl>            <dbl>       <dbl>
    ## 1 B                  13.4           23.5             87.0        559.
    ## 2 M                  21.1           29.3            141.        1422.

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

I’ll choose *steam_games* as the dataset of my mini data analysis for
following reasons:

1.  I personally enjoy steam games, so it would be joyful for me to do
    an analysis on that topic.

2.  The dataset contains 40,833 entries, which provides a sufficiently
    large sample size for my analysis.

3.  The dataset includes a balanced amount of categorical and numerical
    variables, unlike *cancer_sample* which contains mainly numerical
    ones, allowing me to practice a wider range of data analysis
    techniques.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

My research question is: What factors would affect the prices and review
ratings of Steam games?

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

``` r
#library the pack needed
library(ggplot2)
```

1.  Plot the distribution of a numeric variable.

Since I plan to explore the factors influencing the price of the games,
I’ll first plot the distribution of oringal_price and discount_price to
get a general idea.

``` r
#plot a box plot to see the distribution of the original price.
ggplot(steam_games, aes(x = id, y = original_price)) +
  geom_line(fill = "skyblue")
```

    ## Warning in geom_line(fill = "skyblue"): Ignoring unknown parameters: `fill`

![](mini-project-1_files/figure-gfm/unnamed-chunk-16-1.png)<!-- -->

``` r
#I notice there are two entries with extremely high original price. I think there might be some error about these two, so I decide to exclude them from my analysis.

steam_games_filtered <- steam_games %>%  #create a new dataset
  arrange(desc(original_price)) %>%   #arrange the entries in descending order.
  slice(-(1:2))  #exlude the two entries with extremely high orginal price

#plot the distribution plot again.
#line graph:
ggplot(steam_games_filtered, aes(x = id, y = original_price)) +
  geom_line(fill = "skyblue" )
```

    ## Warning in geom_line(fill = "skyblue"): Ignoring unknown parameters: `fill`

![](mini-project-1_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

``` r
#histogram:
ggplot(steam_games_filtered, aes(x = original_price)) +
  geom_histogram(fill = "skyblue" )
```

    ## `stat_bin()` using `bins = 30`. Pick better value `binwidth`.

    ## Warning: Removed 5353 rows containing non-finite outside the scale range
    ## (`stat_bin()`).

![](mini-project-1_files/figure-gfm/unnamed-chunk-17-2.png)<!-- -->

2.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?

``` r
# I have already investigated missing value of original price in task 1, I'll now plot into a bar chart.

#add a new variable to show the missing status
steam_games_filtered <- steam_games %>%
  mutate(missing_status = ifelse(is.na(original_price), "Missing", "Not Missing"))

#plot the missing data into bar chart.

ggplot(steam_games_filtered, aes(x = missing_status, fill = missing_status)) +
  geom_bar() +  
  labs(title = "Missing vs Non-Missing Original Price",
       x = "Missing Status",
       y = "Count") +
  scale_fill_manual(values = c("Missing" = "red", "Not Missing" = "skyblue")) 
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

3.  Explore the relationship between 2 variables in a plot.

I plan to explore what factors would influence the price of games. I’ll
fist investigate the relationship between types and original price.

``` r
#Clean the data to exclude the outliers.
steam_games_filtered <- steam_games %>%
  filter(!is.na(original_price) & is.finite(original_price)) %>%
  group_by(types) %>%
  filter(original_price <= quantile(original_price, 0.99)) %>%
  ungroup()


#Paint the boxplot to see the relationship between types and price.
ggplot(steam_games_filtered, aes(x = types, y = original_price, fill = types)) +
  geom_boxplot(outlier.shape = NA, width = 0.6, alpha =0.5) 
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->

``` r
  labs(title = "Original Price by Type",
       x = "Type",
       y = "Original Price") 
```

    ## <ggplot2::labels> List of 3
    ##  $ x    : chr "Type"
    ##  $ y    : chr "Original Price"
    ##  $ title: chr "Original Price by Type"

4.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

I’ll draw the density plot to explore the discount price and orginal
price.

``` r
ggplot(steam_games_filtered, aes(x = discount_price)) +
  geom_density(fill = "skyblue", alpha = 0.5) +  
  labs(title = "Density Plot of Discount Price",
       x = "Discount Price",
       y = "Density") 
```

    ## Warning: Removed 23275 rows containing non-finite outside the scale range
    ## (`stat_density()`).

![](mini-project-1_files/figure-gfm/unnamed-chunk-20-1.png)<!-- -->

``` r
ggplot(steam_games_filtered, aes(x = original_price)) +
  geom_density(fill = "red", alpha = 0.5) +  
  labs(title = "Density Plot of Original Price",
       x = "Original Price",
       y = "Density") 
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-20-2.png)<!-- -->

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

1.  What factors determine a game’s price?

My hypothesis: Game type, the year of release, or achievements would
influence the price.

2.  What factors affect the discount strategy of games?

My hypothesis: Games with better reviews tend to have lower discount
rate.

3.  Does the relationship between discount rate and review score differ
    by game type?

4.  Are high-priced games with large discounts more likely to receive
    positive reviews?

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
