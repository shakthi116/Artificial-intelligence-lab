# Recommendation System using Collaborative Filtering

import pandas as pd

# User-Movie rating data
ratings = {
    'Movie A': [5, 4, 0, 0],
    'Movie B': [4, 5, 0, 0],
    'Movie C': [0, 0, 5, 4],
    'Movie D': [0, 0, 4, 5]
}

users = ['User1', 'User2', 'User3', 'User4']

df = pd.DataFrame(ratings, index=users)

print("Ratings:")
print(df)

# Find movies liked by User1
user = 'User1'

print("\nRecommendations for", user, ":")

for movie in df.columns:
    if df.loc[user, movie] == 0:
        print(movie)
