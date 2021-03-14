# Tidy Tuesday March 13, 2021: Avatar the Last Airbender

<img src = "https://www.pride.com/sites/default/files/avatar-the-last-airbender-live-action-netflix-lgbtq-characters-v2.jpg">

At [RLadies](https://github.com/RLadies-Amherst/RLadies-Amherst), we looked at the [Avatar dataset](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-08-11/readme.md) from an old [Tidy Tuesday](https://github.com/rfordatascience/tidytuesday). The dataset has information on all episodes in all three seasons of the (AMAZING) show. At first, I was pretty skeptical that we'd be able to make something cool with this dataset, but we ended up answering an interesting question.

We looked at the number of lines each character spoke per episode in Season 1 and found the character that spoke the most lines in each episode. Then, we plotted the number of lines they spoke against the rating of the episode on IMDB, which was included in the dataset.

The plot below shows this information for Season 1 of *Avatar: The Last Airbender*.

<img src = "https://raw.githubusercontent.com/aboskovic21/tidy_tuesday/main/2021/avatar_plot.jpg" width="600" height="500">

Based on the plot, it seems like the highest rated episodes are the ones where the character who speaks most often doesn't actually speak *that* much. I think that could indicate that high rated episodes are ones where the dialogue between characters is pretty balanced or that the high rated episodes have a lot of action and less dialogue. 

It took a while to try to get the character images on the plot, but it was a good introduction to `ggimage`, which I hadn't used before. Check out my [code](https://github.com/aboskovic21/tidy_tuesday/blob/main/2021/week10.Rmd) to see how I got it working. 

Thanks for reading!  
