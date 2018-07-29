# RAMPCODE

Is a PD patch for livecoding with math and logical expressions, inspired in bytebeat but with a few more tools to play synthesis and rythm.

## How does it work?
It has **just one time ramp (phasor~) and all sounds are a function of that**. It is basically waveshaping with math and logic (even bitwise so you can do bytebeat :wink:) plus a rythmical aspect and envelopes. 

## First steps
1. Open the **rampcode.pd** patch in PD.

2. Open your favorite **text editor** and create a file with the code, for instance:

`ramp 1; code sin($v1) 1 1, end;`

3. Click the **open button** in the patch and select the file you are working.

4. Click the **read button** to update the code (remember to save the file before hehe).

If the DSP is on, you should hear an annoying sinewave. Try dividing the sine to change the pitch like `sin($v1/16)` and play with different subdivissions and envelope curves as `sin($v1/16) 8 2`, `sin($v1/16) 8 10`, `sin($v1/16) 4 1`, etc. There is an optional fourth argument for paning: `sin($v1/8) 8 1 0`. Paning goes from -1 (full left) to 1 (full right). All **code** arguments but envelope curve can be expressions as in `sin($v1/16) 8*($v1%t<8000) 1 sin($v1/t)`.

**$v1** is the actual value of the ramp, an icreasing counter (16000 per cycle). **t** is a very useful constant = 16000. Then you have all math (`+ - * / % ...`), bitwise (`& | >> << ...`) and non-bitwise (`&& || > < ...`) logic operators.

## Messages
There are two kinds of messages that rampcode receives: *ramp* and *code*. **Each type of msg is separated by a ; and each msg is separated by ,**. So you can do something like this:

**ramp** sets the general speed and pitch in cycles per second (hz), *think of a cycle as a pattern*.

**code** create multiple signals from the main ramp.

## Examples are your best friend
I think the best way to understand it is taking a look at the examples and mess with them. There are a lot of topics and they are fully commented. **Good luck!** Don't hesitate to contact me to ask anything and show me your rampcodes :heart:


