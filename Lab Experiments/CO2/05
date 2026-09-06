# Decision Tree using ID3 Algorithm

import math

# Dataset
data = [
    ['Sunny', 'Hot', 'No'],
    ['Sunny', 'Hot', 'No'],
    ['Overcast', 'Hot', 'Yes'],
    ['Rain', 'Mild', 'Yes'],
    ['Rain', 'Cool', 'Yes'],
    ['Rain', 'Cool', 'No'],
    ['Overcast', 'Cool', 'Yes'],
    ['Sunny', 'Mild', 'No'],
    ['Sunny', 'Cool', 'Yes'],
    ['Rain', 'Mild', 'Yes']
]

features = ['Weather', 'Temperature']
target = 'Play'

# Calculate Entropy
def entropy(rows):
    total = len(rows)
    counts = {}

    for row in rows:
        result = row[-1]
        counts[result] = counts.get(result, 0) + 1

    ent = 0

    for count in counts.values():
        probability = count / total
        ent -= probability * math.log2(probability)

    return ent


# Calculate Information Gain
def information_gain(rows, feature_index):
    total_entropy = entropy(rows)

    values = set(row[feature_index] for row in rows)

    weighted_entropy = 0

    for value in values:
        subset = [
            row for row in rows
            if row[feature_index] == value
        ]

        weight = len(subset) / len(rows)
        weighted_entropy += weight * entropy(subset)

    return total_entropy - weighted_entropy


# Build Decision Tree
def build_tree(rows, feature_indices):

    # If all rows have the same class
    classes = [row[-1] for row in rows]

    if len(set(classes)) == 1:
        return classes[0]

    # If no features are left
    if not feature_indices:
        return max(set(classes), key=classes.count)

    # Find best feature
    best_feature = max(
        feature_indices,
        key=lambda i: information_gain(rows, i)
    )

    tree = {features[best_feature]: {}}

    values = set(row[best_feature] for row in rows)

    for value in values:
        subset = [
            row for row in rows
            if row[best_feature] == value
        ]

        remaining_features = [
            i for i in feature_indices
            if i != best_feature
        ]

        tree[features[best_feature]][value] = build_tree(
            subset,
            remaining_features
        )

    return tree


# Build the tree
tree = build_tree(data, [0, 1])

print("Decision Tree:")
print(tree)
