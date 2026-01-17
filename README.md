# K-Drama-Recommendation-Application

# ShinyApp:

# Introduction
Finding a drama similar to those you enjoy is difficult. Many different implementations of recommendation systems, and in this visualization, I plan to implement a simple version of this by assigning a similarity score to the dramas selected and then ordering the dramas by ranking. Some other visualization details will also be implemented, for the user to understand more about similar dramas.

# Dataset
The dataset “top100_kdrama.csv” was obtained from Kaggle, and it contains metadata such as genres and tags, which is useful for finding connections between K-dramas. In total, the data from the top 100 dramas in 2023, based on the rankings from MyDramaList, was collected.

# Methodology
The formula for creating the similarity score was simple. Given the three selected dramas, create a vector of unique genres and a vector of unique tags in the three dramas. Then, for each drama, for each shared genre, give 100 points, and for each shared tag, give 10 points. Then, subtract the score by the drama’s rank, which gets rid of ties and also recommends more highly ranked dramas. After obtaining the sorted data frame of similar dramas, I then plotted the top ten dramas in a horizontal bar graph with the plotly library, which shows information about the drama, such as the title and genres, when hovered over the specific bar. Then, if the bar is clicked, the synopsis of the drama is shown below.

# Interactive Features
- User Input: Three selectInput widgets allow users to choose dramas from a searchable sidebar.
- Dynamic Bar Graph: A horizontal bar graph (built with Plotly) displays the top ten most similar dramas.
- Hover Interactivity: Hovering over a bar reveals metadata such as titles and specific genres.
- Click-to-View Synopsis: Registered plotly_click events allow users to click a bar to display a string-wrapped synopsis of the drama below the graph.
