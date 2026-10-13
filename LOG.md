# Debug log

Your notes. One entry per bug you fixed, using the template below.

This file is read as carefully as your code. A correct fix you cannot
explain counts for little; a bug you could not fix but investigated
honestly still counts for something.

Delete the example before you submit.



## Example — delete this

### CC-99 — "The cart total is wrong"

**Reproduced:** Added 2 dosas at Rs. 60 each. The cart showed
Rs. 119.99999 instead of Rs. 130. Happened every time, on any dish with
a price ending in .50.

**Cause:** The total was being added up with plain floating point and
never rounded, so 0.1 + 0.2 style errors showed up on screen. The
rounding helper existed but this one place was not using it.

**Fix:** Ran the total through the existing rounding helper instead of
adding a new one, so every price on screen goes through the same path.

**Checked:** Cart, checkout and the order screen all show Rs. 130 now.
Prices without decimals still show without a trailing .00.

**Time:** about 40 minutes, most of it working out that the cart and the
order screen round in different places.



## CC-0X — "<the complaint, in short>"

**Reproduced:** 

**Cause:**

**Fix:**

**Checked:**

**Time:**

## CC-01 — "The search suggestions menu stuck behind category tab"

**Reproduced:** 	Searched om and the first suggestion was not visible. happened everytime when searching anything. 

**Cause:** The z-index of cat-tabs class was 40 which caused it to be on top of everything else.

**Fix:** Changed the z-index of .cat-tabs to 0 inside style.css

**Checked:** When searching something, the whole suggestion box is visible over the category tab.

**Time:** about 5 minutes, found the class name through browser inspect, tried changing the z-index through there, then changed the styles.css to set z-index to 0.

## CC-02 — "Can't read the prices and dish name in dark mode"

**Reproduced:** When in dark mode, the  dish name and prices were not visible, they were in some gray color which wasnt visible with with the dark background in dark mode.

**Cause:** in the parent of name-btn, the class of the name and prices, parent name: .dish-body, the color was set to hex code and not to the variable "ink" and the color of name-btn was set to inherit.

**Fix:** set the color of name-btn to inherit. 

**Checked:** now when in dark mode, the both the prices and name were visible

**Time:** about 15 minutes mostly to find the parent of btn-name.

## Could not fix

For anything you investigated but did not solve. Say what you tried and
where you got to. This is worth marks — leaving it blank when you got
stuck is not.

### CC-0X — "<the complaint>"

**What I tried:**

**Where I got to:**

**What I would try next:**



## Extra credit

Anything not on the bug log: a problem you found yourself, a test you
wrote, or a fix you are unsure about. Same format, plus one line on how
you noticed it.
