# K-Drama-Recommendation-Application

# ShinyApp:

# Introduction
Finding a drama similar to those you enjoy is difficult. Many different implementations of recommendation systems, and in this visualization, I plan to implement a simple version of this by assigning a similarity score to the dramas selected and then ordering the dramas by ranking. Some other visualization details will also be implemented, for the user to understand more about similar dramas.
# Dataset
The dataset “top100_kdrama.csv” was obtained from Kaggle, and it contains metadata such as genres and tags, which is useful for finding connections between K-dramas. In total, the data from the top 100 dramas in 2023, based on the rankings from MyDramaList, was collected.
# Method
The formula for creating the similarity score was simple. Given the three selected dramas, create a vector of unique genres and a vector of unique tags in the three dramas. Then, for each drama, for each shared genre, give 100 points, and for each shared tag, give 10 points. Then, subtract the score by the drama’s rank, which gets rid of ties and also recommends more highly ranked dramas. After obtaining the sorted data frame of similar dramas, I then plotted the top ten dramas in a horizontal bar graph with the plotly library, which shows information about the drama, such as the title and genres, when hovered over the specific bar. Then, if the bar is clicked, the synopsis of the drama is shown below.
# Question
What are some interesting facts that you learned through the visualization. Provide at least one unexpected finding.
○ One interesting fact about this visualization is that there are many very similarly ranked dramas. There is usually a plateau from the first 1 to 5 dramas to the rest of the top ten similar dramas. This is unexpected because I expected a more linear graph. Expectedly, the dramas with second seasons tend to show up near the top when the first season is selected. However, it was unexpected that when inputting the second season of a drama, the first season was sometimes near the bottom or not in the top ten at all. This may be due to the low ranking of the drama, but It was interesting to see that there were dramas that were closer to the drama than one in the same series.
