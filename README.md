# Crazy Balloon Game

A two-part number grid game in C++, written as an undergraduate programming assignment. Part 1 places balloons on an empty grid and merges neighbouring balloons of the same value. Part 2 picks cells on a filled grid, clears the matching values around them and adds up a score.

## Build and run

```bash
g++ -std=c++11 main.cpp -o balloon
./balloon input1.txt input2.txt output.txt
```

The arguments are the part 1 file, the part 2 file and the output file.

## Input

- **Part 1 file:** the grid size `N` on the first line, then one balloon per line as `value row column`. Rows and columns are counted from 0.
- **Part 2 file:** the grid size `N`, then `N` rows of `N` values separated by spaces, then one target cell per line as `row column`.

## Rules

- **Part 1:** when a placed balloon is connected, horizontally or vertically, to at least two more balloons of the same value, those cells are set to 0 and the placed balloon goes up by 1. The check is repeated with the new value.
- **Part 2:** every cell that holds the same value as the target cell and lies on its row, its column or one of its two diagonals is set to 0. Each cleared cell adds its value to the score.

## Output

The output file holds the final grid of each part under `PART 1:` and `PART 2:`, followed by the score as `Final Point`.
