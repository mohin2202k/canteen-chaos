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

**Reproduced:** Searched om and the first suggestion was not visible. happened everytime when searching anything. 

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

## CC-03 — "Had to scroll sideways just to see the full menu in mobile phones"

**Reproduced:** When viewed in phone width in dev mode in browser, i had to scroll sideways to view the whole menu when the width was less than ~680px . First when i was trying to reproduce the bug, i faced a problem where the browser automatically zoomed out to fit the whole page in the specified width which caused me to not had to scroll sideways. I was stuck there. Then after some tinkering, i found that my auto adjust zoom was on under the zoom menu in dev mode. Disabling that fixed the issue and i got the specified bug. 

**Cause:** the width of the .dish-card img was set to auto which sometimes made the img larger than the parent thus causing overflow and the width of .name-btn(the name of the dish inside the card) was set to max-content which made the name to take extra unwanted space int the dish-card and prevented it to shrink down. These two combined made the card to not shrink and take more space than the screen thus causing the scroll sideways problem. 

**Fix:** set the width of .dish-card img and .name-btn to be 100% so it will always take the full space of the card and so that the card can shrink without any issues when the width of screen is less than 760px. when the width of the screen shrinks to 480px or less, the number of dish-cards drop down to 1 to prevent over shrinking of the card. 

**Checked:** now when the screen width is between 760px(phone width) and 480px(small phones) the cards starts to shrink to fit two card and prevent the card to overflow to more than screen width. And when they reach 480px, only one card is shown to prevebt overshrinking of card.

**Time:** about 15 minutes to mess around with the width settings of the card and its children to see what fits the best. 

## CC-04 — "The add to cart and star button was not working in tablets"

**Reproduced:** set the screen size to tablet in dev mode and tried clicking the add to cart and the star button. I wasnt able to click them.

**Cause:** there were after psuedo classes on dish-card and img-wrap classes under a media query of min-width: 761px and max-width:900 px with no content in it with made an invisible overlay on the add to cart and star buttons which made them impossible to click through.

**Fix:** removed those psuedo classes because I couldnt really think of any reason to include them and the site was responsive without them.

**Checked:** now in tab width, i was able to click the add to cart and star button.

**Time:** 30 mins. approx 10 to find what was causing the issue and another 20 to think of a case where it can be useful and test bunch of different cases to check if everything worked fine.

## CC-0X — "<the complaint, in short>"

**Reproduced:** 

**Cause:**

**Fix:**

**Checked:**

**Time:**

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
