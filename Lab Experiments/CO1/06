from collections import deque

def vacuum_cleaner_problem():
    # State: (Vacuum_Position, Room_A, Room_B)
    # Vacuum_Position: 0 = A, 1 = B
    # Room status: 0 = Dirty, 1 = Clean

    start = (0, 0, 0)
    goal = (0, 1, 1)

    queue = deque([(start, [])])
    visited = set()

    while queue:
        state, path = queue.popleft()

        if state in visited:
            continue

        visited.add(state)
        path = path + [state]

        if state[1] == 1 and state[2] == 1:
            print("Solution Steps:")

            for step in path:
                print(step)

            return

        position, room_a, room_b = state

        next_states = []

        # If vacuum is in Room A
        if position == 0:
            if room_a == 0:
                next_states.append((0, 1, room_b))  # Clean Room A

            next_states.append((1, room_a, room_b))  # Move to Room B

        # If vacuum is in Room B
        else:
            if room_b == 0:
                next_states.append((1, room_a, 1))  # Clean Room B

            next_states.append((0, room_a, room_b))  # Move to Room A

        for next_state in next_states:
            if next_state not in visited:
                queue.append((next_state, path))


vacuum_cleaner_problem()
