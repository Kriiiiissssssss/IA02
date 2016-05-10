# IA02
Projet
afficher([],_).
afficher([X|L],6):- write(X), write(' '),nl, N2 is 1, afficher(L,N2).
afficher([X|L], N):- write(X), write(' '), N1 is N + 1, afficher(L, N1).


element(X,[X|_]):-!.
element(X,[_|Q]):- element(X,Q).

choixBoard(Board, 0):- write('Quel cote souhaitez-vous ?  '), read(X), choixBoard(Board,X).
choixBoard(Board, 1):- Board=[2,3,1,2,2,3,2,1,3,1,3,1,1,3,2,3,1,2,3,1,2,1,3,2,2,3,1,3,1,3,2,1,3,2,2,1], afficher(Board,1),!.
choixBoard(Board, 2):- Board=[2,2,3,1,2,2,1,3,1,3,1,3,3,1,2,2,3,1,2,3,1,3,1,2,2,1,3,1,3,2,1,3,2,2,1,3], afficher(Board,1),!.
choixBoard(Board, 3):- Board=[1,2,2,3,1,2,3,1,3,1,3,2,2,3,1,2,1,3,2,1,3,2,3,1,1,3,1,3,1,2,3,2,2,1,3,2], afficher(Board,1),!.
choixBoard(Board, 4):- Board=[3,1,2,2,3,1,2,3,1,3,1,2,2,1,3,1,3,2,1,3,2,2,1,3,3,1,3,1,3,1,2,2,1,3,2,2], afficher(Board,1).

sbire(_,6):-!.
sbire([T|Q],I):- write('Sbire '), write(I), write(' : '), read(T), I1 is I + 1, sbire(Q,I1).
placerR([T|Q]):-nl,nl, write('Kalista : '), read(T),sbire(Q,1).
placerO([T|Q]):-nl,nl, write('Kalista : '), read(T),sbire(Q,1).

partie(11):- write('le joueur 1 place ses pions'),placerR(L),nl, write('le joueur 2 place ses pions'), placerO(P).
partie(21):- write('L IA a fait son choix'),nl, write('le joueur 2 place ses pions'), placerO(P).
partie(12):- write('le joueur 1 place ses pions'),placerR(L),nl, write('L IA a fait son choix.').
partie(22):- write('hgqzvfluqzhvfluhr').
partie(_):- write('joueur Humain (1) ou IA(2)? '), read(M),nl, partie(M).


initBoard(Board):- afficherBoard(1), choixBoard(Board,0), partie(0).

