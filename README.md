# Minesweeper AI

An intelligent AI player for Minesweeper with a graphical user interface built using Pygame. The AI uses logical inference to make smart moves and identify safe cells, combined with random moves when necessary.

## Features

- **Interactive GUI**: User-friendly Minesweeper game interface built with Pygame
- **Intelligent AI**: Advanced AI agent that uses constraint satisfaction and logical deduction to play Minesweeper
- **Hybrid Strategy**: Combines known safe moves with intelligent random moves when no logical deductions are possible
- **Configurable Board**: Adjustable board height, width, and number of mines
- **Manual & AI Play**: Play manually by clicking cells or let the AI make moves
- **Flagging System**: Right-click to flag suspected mines
- **Real-time Feedback**: Console output showing AI decision-making process

## How It Works

### Game Components

1. **Minesweeper Class**: Represents the Minesweeper game board
   - Generates random mine placement
   - Calculates nearby mines for each cell
   - Tracks flagged mines and game state

2. **Sentence Class**: Represents logical statements about the board
   - Tracks cells and mine counts
   - Infers known mines and safe cells
   - Updates knowledge when mines/safes are marked

3. **MinesweeperAI Class**: Intelligent AI player
   - Maintains knowledge base of all logical deductions
   - Makes safe moves when possible
   - Uses inference to derive new knowledge from existing sentences
   - Falls back to random moves when no safe moves are known

### AI Strategy

The AI uses **constraint satisfaction and logical inference**:
- When a cell is revealed, it creates a logical sentence with neighboring cells and mine count
- It derives conclusions:
  - If a sentence has count = 0, all cells are safe
  - If a sentence has count = length(cells), all cells are mines
  - Uses subset logic to infer new constraints from existing sentences
- Before making random moves, it exhausts all logical deductions

## Installation

### Requirements
- Python 3.7+
- Pygame

### Setup

1. Clone the repository:
```bash
git clone https://github.com/harjot008/Minesweeper.git
cd Minesweeper
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

Run the game:
```bash
python runner.py
```

### Game Controls

- **Left Click**: Reveal a cell
- **Right Click**: Flag/unflag a cell as a suspected mine
- **AI Move Button**: Make the AI play the next move
- **Reset Button**: Start a new game

### Game Modes

- **Manual Play**: Click cells yourself to reveal them
- **AI Assisted**: Click the "AI Move" button to let the AI make strategic moves
- **AI Only**: Repeatedly click "AI Move" to watch the AI play the entire game

## Configuration

Edit the constants in `runner.py` to customize the game:

```python
HEIGHT = 8      # Board height
WIDTH = 8       # Board width
MINES = 8       # Number of mines
```

## Files

- `minesweeper.py`: Core game logic and AI implementation
- `runner.py`: GUI interface using Pygame
- `requirements.txt`: Python dependencies
- `LICENSE`: MIT License

## Game Rules

- Click on unopened cells to reveal them
- Numbers show how many mines are adjacent to that cell (0-8)
- Right-click to flag cells you believe contain mines
- Win by flagging all mines correctly
- Lose if you click on a mine

## Example Output

When the AI plays, you'll see console messages like:
```
AI making safe move.
No known safe moves, AI making random move.
No moves left to make.
```

This helps track the AI's decision-making process and reasoning.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

[harjot008](https://github.com/harjot008)

## Future Enhancements

Possible improvements could include:
- More sophisticated probability-based moves for uncertain situations
- Difficulty levels with different AI strategies
- Game statistics and performance tracking
- Multiplayer support
- Different visual themes

---

**Enjoy watching the AI master Minesweeper!** 🎮💣
