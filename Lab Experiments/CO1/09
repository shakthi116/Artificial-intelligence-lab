from itertools import permutations

# Distance matrix
distance = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0]
]

cities = [0, 1, 2, 3]

min_distance = float('inf')
best_route = None

# Generate all possible routes
for route in permutations(cities):
    total_distance = 0

    # Calculate distance between cities
    for i in range(len(route) - 1):
        total_distance += distance[route[i]][route[i + 1]]

    # Return to starting city
    total_distance += distance[route[-1]][route[0]]

    # Find minimum distance
    if total_distance < min_distance:
        min_distance = total_distance
        best_route = route

print("Best Route:", best_route)
print("Minimum Distance:", min_distance)
