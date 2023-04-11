# Project 2 - Sudoku Solver
Personal Project that solves Sudoku puzzles in Python using recursion and backtracking.

## Skills
Python | Recursion | Backtracking

## Outline
### Print the puzzle: print_puzzle()

### Solver function: Solve()
1. Choose somewhere on the puzzle to make a guess (Helper function: find_next_empty)
    - If there is nowhere left, then the puzzle is solved because we only allowed valid inputs
2. If there is a place to put a number, then make a guess between 1 and 9
3. Check if this is a valid guess (Helper function: is_valid)
    - If the guess is valid, then place it on the puzzle (mutates puzzle)
4. Recursively call our function
5. If the guess is not valid OR if the guess does not solve the puzzle, then backtrack and try a new number
6. If none of the numbers that we have tried work, then this puzzle is unsolvable

### Choose somewhere on the puzzle to make a guess: find_next_empty()
- Finds the next (row, col) on the puzzle that is not filled yet (i.e. -1)
- Returns (row, col) tuple (or (None, None) if there is none)

### Check whether the guess is valid: is_valid()
- Checks whether the guess at the (row, col) of the puzzle is a valid guess
- Returns True if is valid, False otherwise
- For a guess to be valid, then we need to follow the sudoku rules
- That number must not be repeated in the row, column, or 3x3 square that it appears in

## Note
Pseudo codes for the Solver function

    Solve():

        Find somewhere empty on the puzzle to make a guess, say (row, col)
        if nowhere is empty:
            Solved

        Make a guess between 1 and 9 at (row, col) 
            if the guess is valid:
                Place that guess on the puzzle
                if Solve() is Solved:
                    Solved

            if the guess is not valid OR the guess does not solve the puzzle
                Backtrack (Reset) and Make a new guess at (row, col)

        if none of the guesses that we try work:
            Unsolvable
