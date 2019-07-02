## Problem Statement

Given a string, sort it in __decreasing__ order based on the frequency of characters.

__Example 1:__
```
Input:
"tree"

Output:
"eert"

Explanation:
'e' appears twice while 'r' and 't' both appear once.
So 'e' must appear before both 'r' and 't'.
Therefore "eetr" is also a valid answer.
```

__Example 2:__
```
Input:
"cccaaa"

Output:
"cccaaa"

Explanation:
Both 'c' and 'a' appear three times, so "aaaccc" is also a valid answer.
Note that "cacaca" is incorrect, as the same characters must be together.
```

__Example 3:__
```
Input:
"Aabb"

Output:
"bbAa"

Explanation:
"bbaA" is also a valid answer, but "Aabb" is incorrect.
Note that 'A' and 'a' are treated as two different characters.
```

## Result
For this problem, I came up with two different approaches - a brute-force O(n<sup>2</sup>) solution and a more elegant O(n) solution.

### O(n<sup>2</sup>) HashMap solution
* I use a hashMap to store the frequency of each character:
* Use a for-loop that iterates over all the entries in the map finding the entry with maximum value (say, freq).
* Appends that character in the current maxEntry to a StringBuilder for freq times.
* Remove the current maxEntry from the map.
* Repeat the previous 3 steps while map is NOT empty. Since we remove the maxEntry from the map every iteration, the next iteration is guaranteed to find the lower max.
* Return the sorted string.

This solution beats:
* 66.27% all Java submissions running-time wise.
* 90.46% all Java submissions memory-usage wise.
* __O(n<sup>2</sup>)__

### O(n) HashMap solution
I still use a hashMap to store the frequency of each character but use a new way to find the characters with the highest frequencies.
* Use a hashMap to store the frequency of each character.
* Use a seperate __array__ called __list__ of character ArrayLists <pre>ArrayList<Character>[] list</pre> that has the size of the string + 1.
* For each character in the keySet of the original hashMap, I find its count and add the character to list[count]. So the frequency of the character determines the index of where it is in the array.
* Since mulitple characters can share the same frequency, list[count] ( which is an arrayList) can store multiple characters. 
* Use another for-loop that iterates from the list's highest index back down to index of 1 where each iteration appends each character at the list[i] to a stringBuilder __i__ times.
* Return the sorted string.

This solution beats:
* 90.49% all Java submissions running-time wise.
* 94.27% all Java submissions memory-usage wise.
* __O(n)__
