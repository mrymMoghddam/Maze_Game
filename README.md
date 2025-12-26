# Maze_Game
maze = [
    ['#','#','#','#','#'],
    ['#','#',' ',' ','#'],
    ['#',' ','#',' ','#'],
    ['#','#',' ',' ','#'],
    ['#','#','#','#','#']
]

x, y = 1, 1
target_x, target_y = 3, 3

print("Simple Maze Game")
print("Move with: u=up, d=down, l=left, r=right")
print("target:point (3,3)")

while True:
    # نمایش Maze
    for i in range(5):
        for j in range(5):
            if i == y and j == x:
                print("P", end=" ")
            else:
                print(maze[i][j], end=" ")
        print()
    
    # بررسی برنده شدن
    if x == target_x and y == target_y:
        print("You won!")
        break
    
    # دریافت حرکت
    move = input("Next move: ").lower()
    
    # محاسبه موقعیت جدید
    new_x, new_y = x, y
    
    if move == 'u':
        new_y = y - 1

    elif move == 'd':
        new_y = y + 1

    elif move == 'l':
        new_x = x - 1

    elif move == 'r':
        new_x = x + 1
        
    else:
        print("error!")
        continue
    
    # بررسی معتبر بودن حرکت
    if (0 <= new_x < 5 and 0 <= new_y < 5 and 
        maze[new_y][new_x] != '#'):
        x, y = new_x, new_y
    else:
        print("error!")

