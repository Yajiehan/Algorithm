# Algorithm
Project: Maze Solver using Depth-First Search (DFS)
Algorithm
The provided code implements a maze solver using the Depth-First Search (DFS) algorithm. DFS is a popular graph traversal algorithm that explores as far as possible along each branch before backtracking.

Function Description: hasPath
The hasPath function takes a maze, start position, and destination position as inputs and returns a boolean value indicating whether there exists a path from the start to the destination in the maze.

Algorithm Steps:
Define the dfs function: This nested function performs the depth-first search to check if there exists a path from the current position to the destination.

Check if the current position is the destination: If the current position [x, y] is equal to the destination position, we have found a path, so we return True.

Check if the current position is already visited: If the current position [x, y] has already been visited, we return False as we don't want to revisit previously explored paths.

Mark the current position as visited: We mark the current position as visited by setting visited[x][y] to True.

Explore all possible directions: For each direction in the list directions, we perform a while loop to move in that direction until we encounter a wall (maze[nx + dx][ny + dy] == 1) or reach the maze boundaries. This step simulates moving in a straight line until we hit an obstacle or reach the end of the maze.

Recursively call dfs for the new position: After reaching the end of the straight path in a particular direction, we recursively call the dfs function for the new position (nx, ny).

If dfs(nx, ny) returns True, it means there exists a path from the current position to the destination, so we return True.

If none of the directions lead to a valid path, we return False.

Initialize directions, visited, and start the DFS with the dfs function using the start position.

Return the result of the DFS traversal.

Test Cases:

Test Case 1:
Maze: (5x5 grid)
[0, 0, 1, 0, 0],
[0, 0, 0, 0, 0],
[0, 0, 0, 1, 0],
[1, 1, 0, 1, 1],
[0, 0, 0, 0, 0]
Start: [0, 4]
Destination: [4, 4]
Expected Output: True (There is a path from [0, 4] to [4, 4])

Test Case 2:
Maze: (5x5 grid)
[0, 0, 1, 0, 0],
[0, 0, 0, 0, 0],
[0, 0, 0, 1, 0],
[1, 1, 0, 1, 1],
[0, 0, 0, 0, 0]
Start: [0, 4]
Destination: [3, 2]
Expected Output: False (There is no path from [0, 4] to [3, 2])

Test Case 3:
Maze: (5x5 grid)
[0, 0, 0, 0, 0],
[1, 1, 0, 0, 1],
[0, 0, 0, 0, 0],
[0, 1, 0, 0, 1],
[0, 1, 0, 0, 0]
Start: [4, 3]
Destination: [0, 1]
Expected Output: False (There is no path from [4, 3] to [0, 1])
