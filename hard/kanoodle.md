# Title

Kanoodle

# Difficulty

Hard

# Description

The game of Kanoodle provides 12 distinctly shaped pieces (triminoes, tetraminoes and pentaminoes) and asks the player to assemble them into a 5 by 11 rectangular grid. 

The pieces are (and they're given here made up with different letters to help you see them in place). Pieces may be rotated, flipped, etc to make them fit but you may not overlap them or leave any blank squares in the 5x11 grid. 

     A
     A
    AA

     B
    BB
    BB

     C
     C
     C
    CC

     D
     D
    DD
     D
 
     E
     E
    EE
    E

    F
    FF

      G
      G
    GGG

      H
     HH
    HH

    I I
    III

    J
    J
    J
    J

    KK
    KK

     L
    LLL
     L
 
A solution is found when: 

- Every piece is used exactly once.
- Every square in the grid is covered exactly once.

## Note

This is an instance of the exact cover problem. There's "Algorithm X" by Knuth for finding solutions to the exact cover problem. It's not particularly sophisticated; indeed Knuth refers to it as "a statement of the obvious trial-and-error approach."

# Challenge Output

Your program should be able to omit a solution to this challenge. Bonus points if you can discover all of them. 