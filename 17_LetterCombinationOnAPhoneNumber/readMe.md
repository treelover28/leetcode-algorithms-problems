## Problem Statement
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent.

A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.
![200px-Telephone-keypad2 svg](https://user-images.githubusercontent.com/50902696/60766215-5a03e080-a042-11e9-8c51-c068fae9711d.png)

__Example:__
```
Input: "23"
Output: ["ad", "ae", "af", "bd", "be", "bf", "cd", "ce", "cf"].
```

## Result
My solution uses recursion/backtracking to find all possible combinations.

Given a String of digits ( call it __d__), I start with the first number. I have a for-loop that traverse each digit's list of character. After a character is added to a StringBuilder __temp__, the function calls itself recursively but this time with the index leading to the next digit's in the __d__ , and the for-loop runs its first iteration again. As recursion finished traversing __d__, __temp__ is added to the __result__ list. The last character is in the __temp__ is then removed. As recursion unwind back to the previous recursive frame, the for-loop runs its next iteration, appending the next character of that frame's current digit to __temp__. 

The process described above keeps running recursively and unwinding until it gets back to the top, __res__ should now be filled with all the possible combinations. 

### Example Run
__d__ = "23"

__________________________________________

__Recursive Frame 1:__

Current digit = 2 [a,b,c]

For-loop index j = 0 ==> 'a'.

__temp__ = "a"

__res__ = []

Function call itself to next digit

_________________________________________

__Recursive Frame 2:__

Current digit = 3 [d,e,f]

For-loop index j = 0 ==> 'd'.

__temp__ = "ad"

Function call itself to next digit

__________________________________________

__Recursive Frame 3:__

Since temp contains first combination, we add __temp__ to __res__

__res__ = ["ad"]

pop recursive frame 3 and return to Recursive Frame 2 since no more recursive call is made.

___________________________________________

__Recursive Frame 2:__

// continues running left-off code
delete last character in __temp__

__temp__ = "ad" ==> "a"

Current digit = 3 [d,e,f]

For-loop index j = 1 ==> 'e'.

__temp__ = "ae"

__res__ = ["ad"]

Function call itself to next digit

___________________________________________

__Recursive Frame 3:__

Since temp contains a combination, we add __temp__ to __res__

__res__ = ["ad", "ae"]

pop recursive frame 3 and return to Recursive Frame 2 since no more recursive call is made.

______________________________________

__Recursive Frame 2:__

// continues running left-off code
delete last character in __temp__

__temp__ = "ae" ==> "a"

Current digit = 3 [d,e,f]

For-loop index j = 2 ==> 'f'.

__temp__ = "af"

__res__ = ["ad", "ae"]

Function call itself to next digit

___________________________________________

__Recursive Frame 3:__

Since temp contains a combination, we add __temp__ to __res__

__res__ = ["ad", "ae", "af]

pop recursive frame 3 and return to Recursive Frame 2 since no more recursive call is made.

______________________________________

__Recursive Frame 2:__

// continues running left-off code

delete last character in __temp__

__temp__ = "af" ==> "a"

Current digit = 3 [d,e,f]

For-loop index j = 3 ==> exceeds so loop terminates.

Pop Recursive Frame 2 and return to Recursive Frame 1

_______________________________________

__Recursive Frame 1:__

// continues running left-off code
delete last character in __temp__

__temp__ = "a" ==> ""

Current digit = 2 [a,b,c]

For-loop index j = 1 ==> 'b'.

__temp__ = "b"

__res__ = ["ad", "ae", "af"]

Function call itself to next digit

________________________________________

__Recursive Frame 2:__

Current digit = 3 [d,e,f]

For-loop index j = 0 ==> 'd'.

__temp__ = "bd"

Function call itself to next digit
________________________________________

__Recursive Frame 3:__

Since temp contains first combination, we add __temp__ to __res__

__res__ = ["ad", "ae", "af", "bd]

pop recursive frame 3 and return to Recursive Frame 2 since no more recursive call is made.

........ keep continueing in this fashion until the for-loop finishes iterating for every digit!!

This way, we can find every possible combination.
###

My solution beats:
* 66.50% all Java submissions running-time wise.
* 99.13% all Java submissions memory-usage wise.
* Worst case: __O(4<sup>n</sup>)__ where 4 is the numbers of characters for 7 and 9 
* Expected: __O(3<sup>n</sup>)__ where 3 is the number of characters per digit.
* n is the number of digits inputed.

