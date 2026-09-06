% Forward Chaining

fact(sunny).
fact(warm).

rule(sunny, outdoor).
rule(warm, comfortable).
rule(outdoor, play).
rule(comfortable, happy).

% Forward chaining rules

derive(X) :-
    fact(X).

derive(X) :-
    rule(Y, X),
    derive(Y).
