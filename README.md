⚠️ Important: This repository is frozen since it's only here for the purpose of preservation. If you want to use the code to do a Z-80 home computer version, I suggest you look at this effort here: https://github.com/pvmm/msx-tinybasic

Tiny BASIC
==========

This latest version of Li-Chen Wang's Palo Alto Tiny BASIC will run on either the 8080 or Z-80, and only uses 2K of core memory. It contains a number of nice features including command abbreviations and error messages. At the end of the listing is a cross reference table for symbols used in the program and also the object code for the program. For further information on Tiny BASICs, see Dr. Dobb's Journal Volume 1 for which there is a card at the back. Tapes of version 1 are available from Community Computer Center (seep. 105).

Notes
-----

The following errors were found in the source code:

```
F056 215DF0      1595        LXI  H,ST1+1      LITERAL 0
F79B 11CA00      3943 GETLN  LXI  B,BUFFER   ***** MODIFY THIS *****
```

should be, respectively:

```
F056 2A5DF0      1595        LHLD ST1+1        LITERAL 0
F79B 11CA00      3943 GETLN  LXI  D,BUFFER
```

Modifications
-------------

If you want to move the source code from 0xF000 to a lower memory address bellow 0x8000 you need to replace the line:

```F0FC E6FF        1802        ANI   0FFH      ***** ANI 07FH *****```

with this:

```F0FC E67F        1802        ANI   07FH      ***** ANI 0FFH *****```

(That's what the comment is about.)
