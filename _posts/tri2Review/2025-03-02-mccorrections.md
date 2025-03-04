---
layout: post
title: MC Corrections 
type: issues
comments: True
permakink: /mccorrections
---

# Key concepts I got wrong 

<img src="{{site.baseurl}}/images/question6.png" alt="question6">


## Why My Answer (B) is Wrong
You chose B: containsArt("start", "article", "Bart").

The method concatenates all three strings into a single string (all = s1 + s2 + s3) and then checks if "art" appears in the combined string.

"start" contains "art" as a substring.
"article" contains "art" as a substring.
"Bart" does not contain "art" as a substring, but that doesn't matter.
Since at least one of these words already contains "art", the method correctly returns true.
Your choice was incorrect because the method behaved as expected in this case.

### Why the Correct Answer is Right
The correct answer is A: containsArt("rattrap", "similar", "today").

"rattrap" contains "rat", but not "art" explicitly.
"similar" contains "ilar", but not "art".
"today" contains "day", but not "art".
However, when these words are concatenated, "rattrap" + "similar" + "today" creates "rattrapsimilartoday", which contains "art" as a substring.

This exposes a bug in the method: instead of checking whether "art" appears in an individual string, it checks the concatenated version of all three. The method should be checking each word separately, but it's mistakenly allowing "art" to appear across word boundaries.

### Concepts to Study to Get Better
String Searching:

Learn how indexOf() works and how it detects substrings.
Understand why checking in a concatenated string can lead to false positives.
Boolean Logic in Methods:

Instead of concatenating the strings and checking indexOf(), a better approach is to check each string individually and return true if at least one contains "art".

### Debugging Logical Errors:

Try to think about edge cases where the method may not work as intended.
In this case, the edge case is "art" appearing across two words rather than inside a single word.
Fixing the Method:

Instead of:
java
Copy
Edit
String all = s1 + s2 + s3;
return (all.indexOf("art") != -1);
The method should be written as:
java
Copy
Edit
return (s1.indexOf("art") != -1 || s2.indexOf("art") != -1 || s3.indexOf("art") != -1);
This ensures "art" must be fully contained within a single string, fixing the bug.

### How to Improve
I can try writing a few test cases for different methods and predicting their output.
I can pay extra attention to how conditions are checked when working with string manipulation.
When debugging, I can consider how edge cases (like word boundaries) might affect the expected outcome.

<img src="{{site.baseurl}}/images/question9.png" alt="question9">


# **Correction & Explanation**

## **Why My  Answer (D) is Wrong**
You chose:
(int) (Math.random() * 13)
This generates a number 0 to 12 with equal probability, but dice sums range from 2 to 12 and follow a bell curve distribution (7 is most common). Your method does not simulate rolling two independent dice correctly.

### Why the Correct Answer is C
java
(int) (Math.random() * 6) + (int) (Math.random() * 6)
This correctly models rolling two six-sided dice, but should be adjusted to:
java
(int) (Math.random() * 6) + 1 + (int) (Math.random() * 6) + 1;
This ensures each die rolls between 1 and 6, giving sums 2 to 12 with realistic probabilities.

### Key Takeaways
    •    Use (int) (Math.random() * 6) + 1 to get values 1 to 6.
    •    Rolling two dice is not uniform—7 is most common, 2 & 12 least common.
    •    Avoid shortcuts that treat dice rolls as a single random value.

### How to Improve
✔ Practice Math.random() usage for number ranges.
✔ Study probability distributions for real-world simulations.
✔ Test outputs to ensure correct behavior.


<img src="{{site.baseurl}}/images/question38.png" alt="question38">

# **Correction & Explanation**

## **Why My Answer (E) is Wrong**
You chose:
Returns the maximum number of adjacent elements that are not equal to val.
However, the method never compares adjacent elements. Instead, it checks each element individually to see if it is equal to val. Your choice is incorrect because:
    •    The method recursively counts occurrences of val, not sequences of adjacent elements.
    •    There is no logic that tracks consecutive non-val elements.

### Why the Correct Answer is D
The correct answer is:
Returns the number of elements in numbers that are equal to val.
How the Method Works
    1    The method initializes k = 0.
    2    If the last checked element (nums[numVals - 1]) is v, k = 1.
    3    If numVals == 1, it returns k (base case).
    4    Otherwise, it recursively sums k with the count from the rest of the array.
Example
int[] nums = {3, 5, 3, 3, 2};
mystery(nums, 3, 5); // Checking occurrences of 3
    •    nums[4] == 3 → k = 1
    •    nums[3] == 3 → k = 1
    •    nums[2] == 3 → k = 1
    •    nums[1] == 5 → k = 0
    •    nums[0] == 3 → k = 1
    •    Final sum: 1 + 0 + 1 + 1 + 1 = 4 (4 occurrences of 3)
Thus, the method returns the count of elements equal to val, making D the correct answer.

### Key Takeaways
    •    Recursion tracks occurrences, not adjacency.
    •    Base case stops recursion when numVals == 1.
    •    Counting occurrences of a value is a common recursive pattern.

### How to Improve
✔ Practice recursion with array counting problems.
✔ Analyze how base cases and recursive calls modify return values.
✔ Think about what the method is accumulating (sums, counts, or positions).
Let me know if you need more clarification! 🚀