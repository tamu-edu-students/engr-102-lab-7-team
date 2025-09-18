# ENGR 102 Lab Topic 7 (team)
There are two deliverables for this team assignment. Please submit the following files to **Canvas**. Please include the team header information at the top of each file with the names of all contributing team members. This is a team assignment, but **everyone** must submit the file for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Go Moves](#go-moves)

## Go Moves
The purpose of this activity is to get you used to using **lists of lists**, in a 2-D matrix-like format. Your team will create a program that sets up a small [Go board](https://en.wikipedia.org/wiki/Go_(game)) and lets users place stones.

### Part 1
First, **BEFORE YOU CODE**, you must **think** about how to structure your program. Create a document named `go_moves_planning.pdf` that contains an algorithm (in English or pseudocode, **NOT** python) of how you want your program to work. You may want to split up your algorithm into several smaller chunks that do one task each instead of one large algorithm.

Here are the details:
- The board is a 9 x 9 board. **Use a list of lists** to store your current board.
- Display the current state of the board before every move. Each empty point should just be a period. Each point with a stone should have that stone’s identifier.
- For identifiers, you may use lower-case for the white stones and upper-case for the black stones.
  - Use `O`/`o` or distinct round symbols (`*`, `@`, `●`, etc).
  - For a fun alternative, see the note below.
- When a stone is placed, it must be placed on an empty point.
- Continue to let users place stones until they enter “stop”.
- **Important**: You do **NOT** need to enforce any rules of Go or verify moves, with two exceptions: 
  - If a user tries to place a stone where one already exists, print a message to the screen and try again.
  - Alternate turns with black placing the first stone.
  - Other than that, you don’t need to worry about placing stones on forbidden points, removing stones, determining a winner, etc.
- This is an open-ended assignment. Feel free to get creative with your output!

You need to specify the system you want to use to identify the locations on the board. 
- In your pdf document, include instructions for user input.
- This problem will be graded manually so *your instructions must be clear*.
- In Go a simple coordinate system similar to chess is used to identify points on the board. You do **not** have to use this system, but you can if you wish.

*Your pdf must include an algorithm and instructions for running your program.*

### Part 2
Now that your team has planned everything, write a program named `go_moves.py` that sets up a Go board and lets users place stones. **Remember to write test cases and use the “pyramid” approach to programming!**

As an example, here is what the board might look like in the middle of a game:
```
.........
..o......
.oOo.....
.oOOo....
..oOOo...
...oO....
....o....
.........
.........
```
Remember to discuss this as a team and *think* through exactly what you will do *before* developing it!

### Note
You can display empty and filled circles using Unicode characters like the example below.

```
print(chr(9675))    # displays empty circle: ○
print(chr(9679))    # displays filled circle: ●
```
You can also change the color of your output using the `colorama` package like the example below.

```
from colorama import Fore, Style
print(Fore.RED + Style.BRIGHT + "my text" + Fore.RESET + Style.NORMAL)
# displays "my text" in bright red, then resets future text back
# to default colors
```
If you do not have colorama installed, you can use the following strings to do the same thing.

```
begin = "\x1b[1m"
end = "\x1b[39m\x1b[22m"
red = "\x1b[31m"
blue = "\x1b[34m"
green = "\x1b[32m"
print(begin + red + "red text" + end + " back to normal")
print(begin + blue + "blue text" + end + " back to normal")
print(begin + green + "green text" + end + " back to normal")
```

## Frequently Asked Questions
1. **I'm struggling to figure out how to print the board correctly (without `[]` and `,` but also without extra new lines). Any advice?** Try using a nested loop to print the board. Your outer loop can loop through the rows, and the inner loop can loop through the elements in each row (columns). You only need to print a new line at the end of each row, so you can suppress the new line in your inner loop, and add an empty `print()` statement at the end of your outer loop.

3. **This lab is so much fun! Since it's manually graded, can I add some rules in my code?** Programming the rules isn't easy. As long as your code runs and you fulfill the requirements for the lab, it's ok to add in some extra things. If you try something that doesn't work out, comment it out for submission. Also, make sure to include in your instructions which rules are implemented so we can run your code correctly.

Have a question you don't see here? Email your instructor!

Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
