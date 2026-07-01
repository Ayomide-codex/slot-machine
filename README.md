# Slot Machine

A terminal-based slot machine game built in Go. Place your bet, spin the reels, and win based on symbol multipliers — or lose your balance trying.

## Demo

```
Welcome to Show's Casino...
Enter your name: Show Manny
Welcome Show Manny, let's play!
Enter your bet, or 0 to quit (balance = $200): 50

C | A | B
C | C | C   Won $250 (5x) on Line #2
D | A | B

Enter your bet, or 0 to quit (balance = $400): 0
You left with, $400.
```

## How It Works

1. You start with a balance of **$200**.
2. Each round you enter a bet amount.
3. Three reels spin and display a 3x3 grid of symbols.
4. If all three symbols on a row match, you win your bet multiplied by that symbol's multiplier.
5. The game ends when your balance hits **$0** or you choose to quit.

## Symbols and Multipliers

| Symbol | Multiplier | Rarity (weight) |
|--------|------------|-----------------|
| A      | 28x        | 4               |
| B      | 10x        | 7               |
| C      | 5x         | 12              |
| D      | 2x         | 20              |

Rarer symbols pay out more. Common symbols appear more frequently but pay less.

## Project Structure

```
slot-machine/
├── main.go      # Entry point, core game loop, and checkWin logic
├── spin.go      # GenerateSymbolArray, GetRandomNumber, GetSpin, PrintSpin
└── utils.go     # GetName, GetBet — handles all user input
```

All files share `package main` and compile together as one program.

## Concepts Demonstrated

- **Maps** — used as lookup tables for symbol weights and multipliers.
- **2D slices** — `[][]string` represents the slot machine grid.
- **Unsigned integers (`uint`)** — balance and bets are always non-negative.
- **Game loop** — `for balance > 0` keeps the game running until the player runs out of funds or quits.
- **Multi-file structure** — logic is split by responsibility across separate files.
- **Functions with return values** — `checkWin` evaluates each row and returns a slice of winnings.

## Running the Program

From inside the project folder:

```bash
go run .
```

> Use `go run .` (not `go run main.go`) since the project spans multiple files.

## Author

Ayomide Ajisegiri (Show Manny)