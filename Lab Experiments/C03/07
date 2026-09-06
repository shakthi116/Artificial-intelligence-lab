% Best First Search

edge(a, b).
edge(a, c).
edge(b, d).
edge(b, e).
edge(c, f).
edge(c, g).
edge(e, h).
edge(f, h).

% Heuristic values
heuristic(a, 6).
heuristic(b, 4).
heuristic(c, 3).
heuristic(d, 7).
heuristic(e, 2).
heuristic(f, 1).
heuristic(g, 5).
heuristic(h, 0).

% Find the node with the lowest heuristic value
best_node([Node|Nodes], Best) :-
    best_node(Nodes, Node, Best).

best_node([], Best, Best).

best_node([Node|Nodes], Current, Best) :-
    heuristic(Node, H1),
    heuristic(Current, H2),
    (H1 < H2 ->
        NewCurrent = Node
    ;
        NewCurrent = Current
    ),
    best_node(Nodes, NewCurrent, Best).

% Best First Search
best_first(Start, Goal, Path) :-
    search([Start], Goal, [], Path).

search([Goal|_], Goal, _, [Goal]).

search(Open, Goal, Visited, Path) :-
    best_node(Open, Best),
    delete(Open, Best, Remaining),
    findall(X,
            (edge(Best, X), \+ member(X, Visited),
             \+ member(X, Remaining)),
            Children),
    append(Remaining, Children, NewOpen),
    search(NewOpen, Goal, [Best|Visited], RestPath),
    Path = [Best|RestPath].
