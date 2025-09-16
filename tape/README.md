# Tape


I transcripted the tape, about 60 lines for the blue and 102 lines for the yellow.

Decoding it into ASCII, the blue tape is very likely some compiled binary, since the output is garbage. \
HOWEVER, the yellow tape is a different story.

This is the output when you decode it into ASCII:
```
bsJ*B[EOT] M [FF][FF][FF]
1PL[FF][CR]
M[EOT][EOT] C[CR]
=[FF] 1PL[FF][CR]
,[EOT][EOT][EOT] cs K[EOT]
[ESC]="M[EOT]+s[EOT]" L1PL[FF][CR]
[GS][EOT][EOT][EOT] K#[STX]"[EOT] E[CR]
5[ESC]]B$ 1PL[FF][CR]
M[CR]
[EOT][EOT][EOT] C[CR]
= C[CR]
T[CR]
1PL[FF][CR]
M-[EOT][EOT][EOT] s$[RS] C[CR]
UZ[RS]\t
```

## From Gemini:
**TL;DR** - While we don't know the exact machine or system it was for, the logic is clear. It is an automated set of instructions for a device—likely a terminal or printer—to generate a formatted document.

This is very similar to early printer control languages or terminal escape codes (like ANSI or VT100).

`1PL[FF][CR]`
This is clearly a macro or subroutine that is called multiple times. It could mean "1st Printer Line, Form Feed, Carriage Return" – essentially, go to the top of a new page on line 1.

`[ESC]="M[EOT]+s[EOT]"`
This is an escape sequence. It's likely setting a variable. For example, "Set parameter = to the string value M+s". The `[EOT]` codes might be delimiters or pauses.

`[ESC]]B$`
This is a classic cursor positioning command. `[ESC]` initiates the command. `]` and `B` could specify the row and column (e.g., "move to row 29, column 2"), and the `$` is the character to be printed at that location.

`UZ[RS]\t`
This looks like data entry. `U` and `Z` might be field labels, `[RS]` acts as a separator, and `\t` (Tab) moves to the next field.

The presence of the `[ESC]` (Escape) character is a major clue. In the 1970s, the Escape key was the standard way to begin a "command sequence" to control a smart terminal, printer, or other peripheral. This was the precursor to the ANSI escape codes still used in terminals today. The sequence `[ESC]=` likely means "set a variable or parameter."

## After-thoughts
I would love to build a little punch tape reader like https://www.e-basteln.de/computing/papertape/overview/. \
I may do that in the future. Still pretty cool to know what a punch tape from the 70's was made to do.
