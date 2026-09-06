% Planets Database

planet(mercury, 1).
planet(venus, 2).
planet(earth, 3).
planet(mars, 4).
planet(jupiter, 5).
planet(saturn, 6).
planet(uranus, 7).
planet(neptune, 8).

% Rule to find position of a planet
position(Planet, Number) :-
    planet(Planet, Number).

% Rule to check whether a planet is inner planet
inner_planet(Planet) :-
    planet(Planet, Number),
    Number =< 4.

% Rule to check whether a planet is outer planet
outer_planet(Planet) :-
    planet(Planet, Number),
    Number > 4.
