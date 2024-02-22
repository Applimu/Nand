# Nand!
Nand is a fun little esolang / computational model that I have created. It's vaguely based on PROPs in category theory.

To run it, compile nand.rs with rustc,

### `+`/`-` 
Move cursor forwards / backwards <br>
### `N`
Take the bit and the bit infront of the cursor and Nand them together. <br>
### `C`
Copy the bit currently selected and put it to the front of the cursor.
### `S` 
Swap the bit and the bit in front of the cursor
### `I`
Insert a new bit at the position of the cursor.
Everything in front of the cursor will move in the direction faced to accomodate it. <br>
`I` must be followed by one of the following: <br>
    &emsp;`0`: a literal 0<br>
    &emsp;`1`: a literal 1 <br>
    &emsp;`U`: An input from the user <br>
    &emsp;`R`: A random bit (based on the time elapsed, which is not very random but idk how to do crates right now so it will do) <br>
### `D`
Delete the current bit and move forward.
### `B`
Skip the next instruciton if the bit under the cursor is a 1 right now.
### `[ ]`
When the program pointer reaches \], go back to the previous \[ that is not already matched. This allows for basic looping and turing completeness.
```
    [  [ ]  ]  These go to these spots
    |  +-+  |
    +-------+
```