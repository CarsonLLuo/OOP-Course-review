# Coursework

Bug1:输入数据类型为char

Bug2:竖列为3时无法判断胜利

顺序：

1. startGame
2. displayBoard
3. takeMove
4. checkGameState

# startGame

```java
    static void startGame(String[] board) {
        String[] players = {"x", "o"};
        System.out.print("Please select the player that will play first (x/o): ");
        String firstPlayer = scanner.nextLine().trim().toLowerCase();
        while (!firstPlayer.equals("x") && !firstPlayer.equals("o")) {
            System.out.println("Invalid choice! Please enter 'x' or 'o'.");
            System.out.print("Please select the player that will play first (x/o): ");
            firstPlayer = scanner.nextLine().trim().toLowerCase();
        }
        int currentPlayerIndex = firstPlayer.equals("o") ? 0:1;
        String gameState = null;
        while (gameState == null) {
            displayBoard(board);
            currentPlayerIndex = (currentPlayerIndex + 1) % 2;
            System.out.println("Player " + players[currentPlayerIndex] + " playing");
            takeMove(board, players[currentPlayerIndex]);
            gameState = checkGameState(board);
        }
        displayBoard(board);
        displayResult(gameState);
    }
```

‍
