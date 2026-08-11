# 🏏 T20 Cricket Scorer

A simple **command-line T20 cricket scorer** written in Python. Score a match ball-by-ball and watch a live scoreboard update after every delivery.

Built as a learning project to practice the Python fundamentals: **functions, dictionaries, loops, f-strings, and undo with history tuples**.

---

## ✨ Features

- **Live scoreboard** after every ball — team score, overs, last ball, both batsmen (runs & balls faced), and the bowler's figures
- **Full T20 rules** — runs (0–6), wickets, wides, no-balls, leg byes, byes, and the end-of-over batsman swap
- **Undo (`u`)** — rewinds the last ball perfectly using a history log
- **Two innings** — team 2 chases team 1's total, and the winner is announced

## 🚀 Run it

```bash
python3 cricket.py
```

Or open `cricket.py` in PyCharm and click the green **Run** button.

> Requires Python 3 — no extra libraries.

## 🎮 How to score

You'll be asked for team names, two opening batsmen, and a bowler. Then type what happened on each ball:

| Input     | Meaning                                 |
|-----------|-----------------------------------------|
| `0` – `6` | Runs off the bat (dot ball, four, six…) |
| `w`       | Wicket                                  |
| `wd`      | Wide (+1 run, no ball against the over) |
| `nb`      | No ball (+1 run)                        |
| `lb`      | Leg bye (you'll enter how many)         |
| `bye`     | Bye (you'll enter how many)             |
| `u`       | Undo last ball                          |
| `q`       | Quit early                              |

### Sample session

```
============================================
 India  10/1
 Overs: 1.0  |  Last ball: 1
--------------------------------------------
 Rohit            (striker)  4 (3b)
 Virat                       1 (1b)
--------------------------------------------
 Bumrah            1.0-10-1
============================================
```

## 🧠 How it works

- **State** – plain variables and dictionaries hold the match (`runs`, `wickets`, `ball_number`, `batsman_scores`, `bowler_*`, …)
- **Display** – `print_scoreboard()` and `print_end_of_innings()`
- **Logic** – `record_ball()` decides what each input does; `swap_strike()`, `end_of_over()` and the undo system keep the scorebook correct
- **Flow** – `play_innings()` runs one team's innings; `main()` runs the whole match
- **Undo** – every ball is stored as a tuple (`("runs", 2, striker, ball_number)`), so `undo_last_ball()` can wind the game back exactly

## 📁 Project structure

```
CricketScorer/
├── cricket.py    # the whole app (one file)
├── README.md
└── LICENSE
```

## 🔮 Ideas to try next

- Add a **boundary counter** (number of 4s and 6s) per batsman
- Track **fall of wicket (FoW)** as an extra column
- Enforce the T20 **bowler over limit** (max 4 overs each)
- Save the scorecard to a **text file** at the end of the match

## 📄 License

[MIT](LICENSE) — free to use, learn from, and remix.

---