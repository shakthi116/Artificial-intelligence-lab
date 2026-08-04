from collections import deque

def water_jug_problem():
    capacity_a = 4
    capacity_b = 3
    target = 2

    start = (0, 0)
    queue = deque([(start, [])])
    visited = set()

    while queue:
        (a, b), path = queue.popleft()

        if (a, b) in visited:
            continue

        visited.add((a, b))
        path = path + [(a, b)]

        if a == target or b == target:
            print("Solution Steps:")
            for step in path:
                print(step)
            return

        next_states = [
            ((capacity_a, b), "Fill Jug A"),
            ((a, capacity_b), "Fill Jug B"),
            ((0, b), "Empty Jug A"),
            ((a, 0), "Empty Jug B"),

            # Pour A into B
            (
                (a - min(a, capacity_b - b),
                 b + min(a, capacity_b - b)),
                "Pour Jug A into Jug B"
            ),

            # Pour B into A
            (
                (a + min(b, capacity_a - a),
                 b - min(b, capacity_a - a)),
                "Pour Jug B into Jug A"
            )
        ]

        for state, action in next_states:
            if state not in visited:
                queue.append((state, path))

water_jug_problem()
