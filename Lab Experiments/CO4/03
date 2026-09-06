# K-Nearest Neighbors Classification

import math
from collections import Counter

# Training data
data = [
    ([1, 2], 'A'),
    ([2, 3], 'A'),
    ([3, 3], 'A'),
    ([6, 5], 'B'),
    ([7, 7], 'B'),
    ([8, 6], 'B')
]

# New data point
new_point = [5, 5]

# Value of K
k = 3

# Calculate Euclidean distance
distances = []

for point, label in data:
    distance = math.sqrt(
        (point[0] - new_point[0]) ** 2 +
        (point[1] - new_point[1]) ** 2
    )

    distances.append((distance, label))

# Sort based on distance
distances.sort()

# Select K nearest neighbors
neighbors = distances[:k]

print("Nearest Neighbors:")
for distance, label in neighbors:
    print("Distance =", round(distance, 2),
          "Class =", label)

# Get labels
labels = [label for distance, label in neighbors]

# Majority voting
prediction = Counter(labels).most_common(1)[0][0]

print("\nPredicted Class:", prediction)
