MachineLearning_MazeFlooder
===========================

Passing simple maze by flooding all possible solutions simultaneously. First one to reach the exit is marked as the shortest one.

## GRAPH
```python
# 7                (A)--(B)--(C)--(D)
#                   |              |
# 6                (E)--(F)       (G)--(H)
#                        |              |
# 5      (I)--(J)--(K)--(L)  (M)--(N)--(O)
#         |              |    |         |
# 4      (P)--(Q)       (R)  (S)       (T)
#              |              |         |
# 3           (U)--(V)       (W)--(X)  (Y)
#                   |              |    |
# 2                (Z)       (1)--(2)  (3)
#                   |                   |
# 1                (4)--(5)--(6)--(7)--(8)
#
#         1    2    3    4    5    6    7
```

## GRAPH VALUES
```python
nodes_cords = {
        "A" : [2,7],    "B" : [3,7],
        "C" : [4,7],    "D" : [5,7],
        "E" : [2,6],    "F" : [3,6],
        "G" : [5,6],    "H" : [6,6],
        "I" : [1,5],    "J" : [2,5],
        "K" : [3,5],    "L" : [4,5],
        "M" : [5,5],    "N" : [6,5],
        "O" : [7,5],    "P" : [1,4],
        "Q" : [2,4],    "R" : [4,4],
        "S" : [5,4],    "T" : [7,4],
        "U" : [2,3],    "V" : [3,3],
        "W" : [5,3],    "X" : [6,3],
        "Y" : [7,5],    "Z" : [3,2],
        "1" : [5,2],    "2" : [6,2],
        "3" : [7,2],    "4" : [3,1],
        "5" : [4,1],    "6" : [5,1],
        "7" : [6,1],    "8" : [7,1]
}
```

## OUTPUT:

```python
Searching path via [] --> C
        [ ] Node value: 6.0
        L[ ] Analyzing neighbour node: B
        L[ ] Analyzing neighbour node: D

Searching path via ['C'] --> D
        [ ] Node value: 6.083
        L[ ] Analyzing neighbour node: G

Searching path via ['C'] --> B
        [ ] Node value: 6.083
        L[ ] Analyzing neighbour node: A

Searching path via ['C', 'D'] --> G
        [ ] Node value: 6.099
        L[ ] Analyzing neighbour node: H

Searching path via ['C', 'B'] --> A
        [ ] Node value: 7.325
        L[ ] Analyzing neighbour node: E

Searching path via ['C', 'B', 'A'] --> E
        [ ] Node value: 7.385
        L[ ] Analyzing neighbour node: F

Searching path via ['C', 'D', 'G'] --> H
        [ ] Node value: 7.385
        L[ ] Analyzing neighbour node: N

Searching path via ['C', 'D', 'G', 'H'] --> N
        [ ] Node value: 7.472
        L[ ] Analyzing neighbour node: M
        L[ ] Analyzing neighbour node: O

Searching path via ['C', 'B', 'A', 'E'] --> F
        [ ] Node value: 8.099
        L[ ] Analyzing neighbour node: K

Searching path via ['C', 'B', 'A', 'E', 'F'] --> K
        [ ] Node value: 8.123
        L[ ] Analyzing neighbour node: J
        L[ ] Analyzing neighbour node: L

Searching path via ['C', 'D', 'G', 'H', 'N'] --> M
        [ ] Node value: 8.123
        L[ ] Analyzing neighbour node: S

Searching path via ['C', 'D', 'G', 'H', 'N', 'M'] --> S
        [ ] Node value: 8.162
        L[ ] Analyzing neighbour node: W

Searching path via ['C', 'D', 'G', 'H', 'N', 'M', 'S'] --> W
        [ ] Node value: 8.236
        L[ ] Analyzing neighbour node: X

Searching path via ['C', 'B', 'A', 'E', 'F', 'K'] --> L
        [ ] Node value: 9.0
        [@] Dead end discovered:  R

Searching path via ['C', 'D', 'G', 'H', 'N'] --> O
        [ ] Node value: 9.0
        L[ ] Analyzing neighbour node: T

Searching path via ['C', 'D', 'G', 'H', 'N', 'O'] --> T
        [ ] Node value: 9.243
        L[ ] Analyzing neighbour node: Y

Searching path via ['C', 'B', 'A', 'E', 'F', 'K'] --> J
        [ ] Node value: 9.472
        L[ ] Analyzing neighbour node: I

Searching path via ['C', 'D', 'G', 'H', 'N', 'M', 'S', 'W'] --> X
        [ ] Node value: 9.828
        L[ ] Analyzing neighbour node: 2

Searching path via ['C', 'D', 'G', 'H', 'N', 'M', 'S', 'W', 'X'] --> 2
        [ ] Node value: 10.236
        [@] Dead end discovered:  1

Searching path via ['C', 'D', 'G', 'H', 'N', 'O', 'T'] --> Y
        [ ] Node value: 11.0
        L[ ] Analyzing neighbour node: 3

Searching path via ['C', 'D', 'G', 'H', 'N', 'O', 'T', 'Y'] --> 3
        [ ] Node value: 10.162
        L[ ] Analyzing neighbour node: 8

Searching path via ['C', 'D', 'G', 'H', 'N', 'O', 'T', 'Y', '3'] --> 8
        [ ] Node value: 11.0
        L[ ] Analyzing neighbour node: 7

Searching path via ['C', 'D', 'G', 'H', 'N', 'O', 'T', 'Y', '3', '8'] --> 7
        [ ] Node value: 11.0
        L[ ] Analyzing neighbour node: 6

Searching path via ['C', 'B', 'A', 'E', 'F', 'K', 'J'] --> I
        [ ] Node value: 11.0
        L[ ] Analyzing neighbour node: P

Searching path via ['C', 'D', 'G', 'H', 'N', 'O', 'T', 'Y', '3', '8', '7'] --> 6
        [ ] Node value: 11.0
        L[ ] Analyzing neighbour node: 5

[+] Destination reached in 26 iterations.


SHORTEST PATH:
C [4, 7]
D [5, 7]
G [5, 6]
H [6, 6]
N [6, 5]
O [7, 5]
T [7, 4]
Y [7, 5]
3 [7, 2]
8 [7, 1]
7 [6, 1]
6 [5, 1]

```
