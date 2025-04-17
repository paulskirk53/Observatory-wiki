the ASTAP software website is [here](https://www.hnsky.org/astap.htm#conditions) it can be daunting at first, but it's integrated well with [[Sequence Generator Pro]] . Note the key criteria for successful plate solving on the web page, one of which is the field of view. For the Celestron C14 (I would provide a link but it's all Celestron hype), with the Starlight Express h814C camera and 0.8x reducer, the following applies:

System focal length  3128  mm  (this takes into account the 0.8x reduction)
Camera CD size 12mm x 10 mm (approx) for SX H814C
Field of view is 0.2 degrees x 0.20 degrees approximately, which is great for capturing small objects like galaxies M81, M82, NGC4565 ....

## some config points
**in ASTAP settings:**
- set FOV as 0.2 degrees
- set downsample to 2
- set use triples - if ASTAP can it will use quads anyway
- Set the smallest object to be recognised as a star - usually 3 or 4 pixels
- use hash code tolerance as default 0.007
- radius search area can be 30, but if blind solve is required try 180 - i haven' found that to work.
- For our very small FOV, use the D80 star database.

Also if solve doesn't work, jog the scope using the handset or software equivalent controls in SGP or ASCOM Device Hub

With the small FOV, a 30 second 1x1 binned image is required for the solve to see enough stars.

I would say so far ASTAP has been 95% reliable and Han at HNSKY is contactable and responds very quickly


return to [[Observatory Home]] home page
