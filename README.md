## Hi there 👋<h1 align="center">Hi, I'm [Tanmay Dahake] 👋</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=00C2FF&center=true&vCenter=true&width=480&lines=welcome;Computer+Engineering+Student;Frontend+Developer;Problem+Solver" />
</p>

<p align="center">
  I’m a student developer focused on building practical projects and learning modern web technologies.
</p>

### 🔧 Skills
- JavaScript
- Python
- React
- Node.js
- Java
- HTML / CSS
- Git & GitHub

### 🚀 Projects
- IPL score Predictor 
- Online shopping system 
- Water Management

### 📫 Contact
- LinkedIn: [Tanmay Dahake]
- Email: [tanmaydahake19@gmail.com]
- GitHub: [https://github.com/tanmaydahake19-byte]

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=[tanmaydahake19-byte]&show_icons=true&theme=radical" />
</p>

<!--
**tanmaydahake19-byte/tanmaydahake19-byte** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tic Tac Toe</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: #222;
            font-family: Arial, sans-serif;
        }
        
        .game-container {
            text-align: center;
        }
        
        h1 {
            color: #fff;
            margin-bottom: 30px;
        }
        
        .board {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            gap: 5px;
            margin: 0 auto 30px;
        }
        
        .cell {
            width: 100px;
            height: 100px;
            background: #444;
            border: none;
            color: #fff;
            font-size: 30px;
            cursor: pointer;
            border-radius: 5px;
            transition: 0.3s;
        }
        
        .cell:hover {
            background: #555;
        }
        
        .status {
            color: #fff;
            font-size: 20px;
            margin-bottom: 20px;
        }
        
        .reset-btn {
            background: #4CAF50;
            color: white;
            padding: 10px 30px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        
        .reset-btn:hover {
            background: #45a049;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>⭕ Tic Tac Toe</h1>
        <div class="status">Player: <span id="status">X</span></div>
        <div class="board" id="board">
            <button class="cell" onclick="makeMove(this, 0)"></button>
            <button class="cell" onclick="makeMove(this, 1)"></button>
            <button class="cell" onclick="makeMove(this, 2)"></button>
            <button class="cell" onclick="makeMove(this, 3)"></button>
            <button class="cell" onclick="makeMove(this, 4)"></button>
            <button class="cell" onclick="makeMove(this, 5)"></button>
            <button class="cell" onclick="makeMove(this, 6)"></button>
            <button class="cell" onclick="makeMove(this, 7)"></button>
            <button class="cell" onclick="makeMove(this, 8)"></button>
        </div>
        <button class="reset-btn" onclick="resetGame()">New Game</button>
    </div>

    <script>
        let gameBoard = ['', '', '', '', '', '', '', '', ''];
        let currentPlayer = 'X';
        let gameActive = true;

        const winConditions = [
            [0, 1, 2],
            [3, 4, 5],
            [6, 7, 8],
            [0, 3, 6],
            [1, 4, 7],
            [2, 5, 8],
            [0, 4, 8],
            [2, 4, 6]
        ];

        function makeMove(element, index) {
            if (gameBoard[index] === '' && gameActive) {
                gameBoard[index] = currentPlayer;
                element.textContent = currentPlayer;
                element.disabled = true;

                if (checkWin()) {
                    document.getElementById('status').textContent = currentPlayer + ' Wins! 🎉';
                    gameActive = false;
                } else if (gameBoard.every(cell => cell !== '')) {
                    document.getElementById('status').textContent = "It's a Draw!";
                    gameActive = false;
                } else {
                    currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
                    document.getElementById('status').textContent = currentPlayer;
                }
            }
        }

        function checkWin() {
            return winConditions.some(condition => {
                return condition.every(index => gameBoard[index] === currentPlayer);
            });
        }

        function resetGame() {
            gameBoard = ['', '', '', '', '', '', '', '', ''];
            currentPlayer = 'X';
            gameActive = true;
            document.getElementById('status').textContent = currentPlayer;
            document.querySelectorAll('.cell').forEach(cell => {
                cell.textContent = '';
                cell.disabled = false;
            });
        }
    </script>
</body>
</html>
