It is now time to get familiar with some basic physics. The first thing we need you to do is a simple calculation for how long we need to do a burn in order to get to the correct speed.

Our fully loaded rocket doubles its speed every second starting at 100m/s. Write a program that calculates the speed the rocket is traveling at for every second of a burn, based on a number of seconds entered by the user. The output should be displayed in km/s. The output should also provide a chart showing the speed after every second of the burn, in case the initial estimate for the burn length was too high.

Complete your work in `src/RocketSpeed.java`.

## Speed Per Second

The rocket starts its burn at 100m/s and doubles its speed every second after that:

| Seconds   | Speed (m/s) | Speed (km/s) |
|---------  |-------------|--------------|
| 1 second  | 100 m/s     | 0.1km/s      |
| 2 seconds | 200 m/s     | 0.2km/s      |
| 3 seconds | 400 m/s     | 0.4km/s      |
| 4 seconds | 800 m/s     | 0.8km/s      |
| 5 seconds | 1600 m/s    | 1.6km/s      |

Hint: The starting speed given is measured in meters per second, but the outputs are measured in kilometers per second. Do the math in meters per second and only convert to kilometers per second when it is time to display a value.

## Final Speed

In addition to the chart, the program reports a "final speed" once the chart is finished. The final speed is the **sum of every speed shown in the chart**, not just the speed of the last second. For example, if the burn lasts 5 seconds, the final speed is:

```
0.1 + 0.2 + 0.4 + 0.8 + 1.6 = 3.1km/s
```

## Input Validation

Nobody should be able to enter a negative number, zero, or any non-number characters for the number of seconds. If the user enters an invalid value, tell them and ask them again until they give you a valid number of seconds (an integer of 1 or greater).

## Required Prompts and Output

Things you need to pass the tests:

- Prompt 1: `How many seconds is the burn?`
- Prompt 2 (for invalid input only): `The number of seconds must be at least 1.`
- Prompt 2 (continued on a new line): `How many seconds is the burn?`
- Output 1 (chart header): `Seconds` `[tab]` `Total Speed` `[new line]`
- Output 2 (one line per second): `[seconds elapsed]` `[tab]` `[tab]` `[current speed]` `km/s` `[new line]`
- Output 3 (after the chart): `Final speed:` `[tab]` `[final speed]` `km/s` `[new line]`

## Sample Run

Input: `5`

```
How many seconds is the burn?
Seconds	Total Speed
1		0.1km/s
2		0.2km/s
3		0.4km/s
4		0.8km/s
5		1.6km/s
Final speed:	3.1km/s
```

If the user first enters an invalid value (for example `-3` or `abc`), the burn length prompt repeats until a valid number of seconds is entered, and the chart is only printed once a valid value has been given:

```
How many seconds is the burn?
The number of seconds must be at least 1.
How many seconds is the burn?
Seconds	Total Speed
1		0.1km/s
2		0.2km/s
3		0.4km/s
Final speed:	0.7km/s
```

## What You'll Need to Use

- A `Scanner` to read the number of seconds from the user.
- A loop (or conditional) to validate the input until it is a valid number of seconds.
- A loop to build the chart and calculate the final speed one second at a time.
