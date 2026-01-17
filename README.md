# K-Drama-Recommendation-Application

# ShinyApp:

# Introduction
Finding a drama similar to those you enjoy is difficult. Many different implementations of recommendation systems, and in this visualization, I plan to implement a simple version of this by assigning a similarity score to the dramas selected and then ordering the dramas by ranking. Some other visualization details will also be implemented, for the user to understand more about similar dramas.

# Dataset
The dataset “top100_kdrama.csv” was obtained from Kaggle, and it contains metadata such as genres and tags, which is useful for finding connections between K-dramas. In total, the data from the top 100 dramas in 2023, based on the rankings from MyDramaList, was collected.

# Methodology
The recommendation engine calculates a similarity score to find connections between titles using the following weighted formula:
- Vectorization: The app creates unique vectors for genres and tags based on three user-selected dramas.
- Weighted Scoring: For every drama in the dataset, points are awarded for shared attributes:
  - +100 points for each shared genre.
  - +10 points for each shared tag.
- Ranking Penalty: To resolve ties and prioritize quality, the final score is subtracted by the drama’s original rank. This ensures that highly-ranked dramas are prioritized in the final recommendations.

# Interactive Features
- User Input: Three selectInput widgets allow users to choose dramas from a searchable sidebar.
- Dynamic Bar Graph: A horizontal bar graph (built with Plotly) displays the top ten most similar dramas.
- Hover Interactivity: Hovering over a bar reveals metadata such as titles and specific genres.
- Click-to-View Synopsis: Registered \plotly_click\ events allow users to click a bar to display a string-wrapped synopsis of the drama below the graph.
