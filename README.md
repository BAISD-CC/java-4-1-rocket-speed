It is now time to get familiar with some basic physics. The first thing we need you to do is a simple calculation for how long we need to do a burn in order to get to the correct speed.

Our fully loaded rocket doubles its speed every second starting at 100m/s. We need you to write a program that calculates the speed that the rocket is traveling at based on how many seconds we input as a potential burn. The output should be displayed in km/s. The output should also provide us with a chart to show us the speed after different numbers of seconds in case we set our initial estimate too high.

Example:
| Seconds   | Speed    |
|---------  |----------|
| 1 second  | .1km/s   |
| 2 seconds | .2km/s   |
| 3 seconds | .4km/s   |
| 4 seconds | .8km/s   |
| 5 seconds | 1.6km/s  |

We also want to make sure that nobody tries to put in a negative value or any non-number characters. Please make sure that you include input validation to prevent them from doing that.

Things you need to pass the tests:
- Prompt 1: "How many seconds is the burn?"
- Prompt 2(for invalid input only): "The number of seconds must be at least 1."
- Prompt 2(continued on a new line): "How many seconds is the burn?"
- Output 1: "Seconds``[tab]``Total Speed``[new line]`"
- Output 2: "`[seconds elapsed]``[tab]``[tab]``[current speed]`km/s``[new line]`"
- Output 3: "Final speed:``[tab]``[final speed]`km/s``[new line]`"

Hint: The starting speed given is measured in meters per second, but the outputs are measured in kilometers per second.
