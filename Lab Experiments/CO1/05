from collections import deque

# State: (Missionaries_left, Cannibals_left, Boat_position)
# Boat position: 0 = Left side, 1 = Right side

def is_valid(state):
    m_left, c_left, boat = state
    m_right = 3 - m_left
    c_right = 3 - c_left

    # Values must be within limits
    if not (0 <= m_left <= 3 and 0 <= c_left <= 3):
        return False

    # Left side condition
    if m_left > 0 and m_left < c_left:
        return False

    # Right side condition
    if m_right > 0 and m_right < c_right:
        return False

    return True


def get_next_states(state):
    m, c, boat = state

    # Possible combinations in the boat
    moves = [
        (1, 0),  # 1 Missionary
        (2, 0),  # 2 Missionaries
        (0, 1),  # 1 Cannibal
        (0, 2),  # 2 Cannibals
        (1, 1)   # 1 Missionary and 1 Cannibal
    ]

    next_states = []

    for dm, dc in moves:
        if boat == 0:  # Boat moves from left to right
            new_state = (m - dm, c - dc, 1)
        else:           # Boat moves from right to left
            new_state = (m + dm, c + dc, 0)

        if is_valid(new_state):
            next_states.append(new_state)

    return next_states


def solve():
    start = (3, 3, 0)
    goal = (0, 0, 1)

    queue = deque([(start, [start])])
    visited = set()

    while queue:
        state, path = queue.popleft()

        if state in visited:
            continue

        visited.add(state)

        if state == goal:
            print("Solution Path:")
            for step in path:
                print(step)
            return

        for next_state in get_next_states(state):
            if next_state not in visited:
                queue.append((next_state, path + [next_state]))

    print("No solution found.")


solve()
