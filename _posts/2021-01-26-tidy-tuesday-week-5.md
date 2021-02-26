# Tidy Tuesday January 26, 2021: Plastic Pollution

Today I looked at a dataset at [RLadies](https://github.com/RLadies-Amherst/RLadies-Amherst) about [plastic pollution](https://github.com/rfordatascience/tidytuesday/tree/master/data/2021/2021-01-26). This dataset is actually from almost a month ago, but it seemed interesting, so we decided to focus on it today at our meeting.

The dataset has columns for different types of plastic in different countries produced by different companies. The most recognizable company was the Coca-Cola Corporation, so I decided to focus my visualization on that along with the total plastic found, instead of specific types of plastic, in the countries listed in the dataset.

When I ran the `unique()` function to see which countries were in the dataset, I ended up with 69 countries. My first though was, oh, maybe a map colored by amount of plastic would look nice. I didn't realize how bad all that missing data would actually make it look...

<img src = "https://github.com/aboskovic21/tidy_tuesday/blob/main/2021/map_fail.jpg" width="600" height="500">

I know that looks pretty bad, but trust me, it looked even worse before I took the log for the color scaling. I couldn't leave on that note, though, so I hurriedly made a bar graph of the same information. Ordering the countries by total plastic worked pretty well - at least better than the map! 

<img src = "https://github.com/aboskovic21/tidy_tuesday/blob/main/2021/plastic.jpg" width="600" height="500">

Thanks for reading! If you're interested, check out my code [here](https://github.com/aboskovic21/tidy_tuesday/blob/main/2021/week5.Rmd).
