# Ch. 4 Challenge 1: Rocket Speed

## Mission Briefing

Mission Control needs to know how fast the rocket is moving during an engine burn. The fully loaded rocket starts its burn at 100 meters per second (m/s) and doubles its speed every second. Your program asks for the length of the burn, shows a chart of the rocket's speed for every second, and reports a final speed. The chart lets the crew see every second of the burn, in case the first estimate of the burn length was too high.

## What You'll Practice

- Input validation with a priming read and a `while` loop (Day 1 notes, E7-1 and E7-2)
- A `while` loop that counts from 1 up to a number (Day 1 notes, E4)
- Changing more than one variable on every iteration (Day 1 notes, E5)
- `++` to move a counter forward by 1 (Day 1 notes, E1)
- `Scanner` keyboard input and the `\t` tab escape sequence (Chapter 2)

## Starter Code

Edit `src/RocketSpeed.java`. The class is `RocketSpeed`. Do not rename the file or the class.

The comments in the starter list the steps of the program in order. Write the code for each step under its comment.

## Inputs

| Order | What it is | Java type |
|---|---|---|
| 1 | Burn length in seconds (asked again until it is valid) | `int` |

## Rules

### 1. Valid burn length

The burn length must be a whole number of **at least** 1. Zero, negative numbers, and anything that is not a number (such as `abc`) are invalid. When the input is invalid, print the error message, print the prompt again, and read a new value. Keep asking until the value is valid. The chart prints only after a valid value is entered.

| Typed | Valid? |
|---|---|
| `abc` | No |
| `-3` | No |
| `0` | No (**below** 1) |
| `1` | Yes (**at least** 1) |
| `2` | Yes |

### 2. Speed each second

These are classroom numbers, not real rocket physics. The speed in second 1 is 100 m/s, and the speed doubles every second after that. The chart shows each speed in kilometers per second (km/s).

```
speed in second 1 = 100 m/s
speed in the next second = speed * 2
speed in km/s = speed in m/s / 1000
```

| Seconds | Speed (m/s) | Speed (km/s) |
|---|---|---|
| 1 | 100 | 0.1 |
| 2 | 200 | 0.2 |
| 3 | 400 | 0.4 |
| 4 | 800 | 0.8 |
| 5 | 1600 | 1.6 |

Do the math in m/s. Convert to km/s only when you display a value.

### 3. Final speed

The final speed is the **sum of every speed shown in the chart**, not just the speed of the last second. For a 5 second burn:

```
0.1 + 0.2 + 0.4 + 0.8 + 1.6 = 3.1km/s
```

Add the speeds in m/s, then convert the total to km/s. Adding the km/s values as decimals can print extra digits, such as `0.30000000000000004`.

## What to Use

These are suggestions. Any approach that produces the correct output earns full credit, as long as it reads input with a `Scanner` and uses a loop (see How It's Checked).

- A priming read, then a `while` loop that repeats while the burn length is invalid (E7-2 pattern).
- `keyboard.hasNextInt()` to check that the next input is a whole number before reading it with `nextInt()`. If it returns `false`, throw away the bad input with `keyboard.next()` so it is not read again.
- A `while` loop with a counter that runs once for every second of the burn.
- An `int` speed in m/s that doubles each iteration, and an `int` total that adds each speed, like `altitude` in E5.

## Exact Output

Spelling, capitalization, and punctuation must match exactly. `[tab]` means one tab character, written `\t` in Java. There is no space before `km/s`. Speeds print the way Java prints a `double`, for example `0.1`, `1.6`, or `12.7`.

Prompt, printed on its own line (the user types on the next line):

```
How many seconds is the burn?
```

Only when the input is invalid: the error message, then the prompt again:

```
The number of seconds must be at least 1.
How many seconds is the burn?
```

Chart header:

```
Seconds[tab]Total Speed
```

One line per second of the burn, starting at 1:

```
[seconds][tab][tab][speed]km/s
```

After the chart:

```
Final speed:[tab][final speed]km/s
```

## Sample Runs

Burn length `5`:

```text
How many seconds is the burn?
5
Seconds	Total Speed
1		0.1km/s
2		0.2km/s
3		0.4km/s
4		0.8km/s
5		1.6km/s
Final speed:	3.1km/s
```

Invalid input `-3`, then `3`:

```text
How many seconds is the burn?
-3
The number of seconds must be at least 1.
How many seconds is the burn?
3
Seconds	Total Speed
1		0.1km/s
2		0.2km/s
3		0.4km/s
Final speed:	0.7km/s
```

Boundary: `0`, then `1`:

```text
How many seconds is the burn?
0
The number of seconds must be at least 1.
How many seconds is the burn?
1
Seconds	Total Speed
1		0.1km/s
Final speed:	0.1km/s
```

## Test Your Program

Run each test before you submit. The autograder uses these and other values.

| Typed | What should happen | Last line printed |
|---|---|---|
| `0`, then `2` | Error message and prompt again, then a 2-row chart | `Final speed:	0.3km/s` |
| `-3`, then `3` | Error message and prompt again, then a 3-row chart | `Final speed:	0.7km/s` |
| `abc`, then `2` | Error message and prompt again (no crash), then a 2-row chart | `Final speed:	0.3km/s` |
| `1` | A 1-row chart | `Final speed:	0.1km/s` |
| `2` | A 2-row chart | `Final speed:	0.3km/s` |
| `5` | A 5-row chart | `Final speed:	3.1km/s` |
| `7` | A 7-row chart; the last row is `7		6.4km/s` | `Final speed:	12.7km/s` |

## How It's Checked

| Check | What it looks for | Points |
|---|---|---|
| Valid burn lengths | Exact output for 1, 5, and 7 second burns (4 points each) | 12 |
| Invalid input | Exact output when a negative number or non-number input comes first (4 points each) | 8 |
| Uses a `Scanner` | The source code uses `Scanner` | 2 |
| Uses a loop | The source code has a `while` or `for` loop | 2 |
| No hardcoded answer | The source code does not contain the sample answer `3.1km/s` | 1 |
| **Total** | | **25** |

Any approach that produces the correct output earns full credit, as long as it uses a `Scanner` and a loop. Results must come from the user's input; printing a fixed answer fails the tests that use other burn lengths.

## Where to Look

- Day 1 notes, E7-2 (The validation loop): a priming read, then a loop that repeats while the input is invalid.
- Day 1 notes, E4 (Anatomy of a while loop): a counter that starts at 1 and stops after the last value.
- Day 1 notes, E5 and its trace table: two variables that change on every iteration.
- Rules 2 above: the speed table for the first five seconds.
