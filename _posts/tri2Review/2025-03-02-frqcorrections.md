---
layout: post
title: FRQ Corrections
type: issues
comments: True
permakink: /frqcorrections
---

# 2014a. FRQ
```java
public class WordScrambler {
    private String[] scrambledWords;

    /**
     * Constructor initializes scrambledWords with mixed words from the given array.
     * @param wordArr an array of String objects (even length assumed)
     */
    public WordScrambler(String[] wordArr) {
        scrambledWords = mixedWords(wordArr);
    }

    /**
     * Takes two words and combines them by taking the first half of the first word
     * and the second half of the second word.
     * @param word1 The first word
     * @param word2 The second word
     * @return A new string formed by taking the first half of word1 and the second half of word2
     */
    private String recombine(String word1, String word2) {
        // Find the halfway point of each word
        int mid1 = word1.length() / 2;
        int mid2 = word2.length() / 2;
        
        // Concatenate the first half of word1 with the second half of word2
        return word1.substring(0, mid1) + word2.substring(mid2);
    }

    /**
     * Takes an array of words and forms a new array where each pair of words is recombined.
     * @param words An array of String objects (assumed to be of even length)
     * @return A new array with the same length where every pair of words is recombined
     */
    private String[] mixedWords(String[] words) {
        // Create a new array to store the recombined words
        String[] mixed = new String[words.length];
        
        // Process words in pairs
        for (int i = 0; i < words.length; i += 2) {
            // Apply recombine function to the pair of words
            mixed[i] = recombine(words[i], words[i + 1]);
            mixed[i + 1] = recombine(words[i + 1], words[i]); // Swap order for second recombination
        }
        
        return mixed;
    }
}
```

# 2014b. FRQ 
```java 
public class Mountain {

    /** 
     * @param array an array of positive integer values
     * Precondition: array.length > 0
     * @return the index of the first peak (local maximum) in the array, if it exists;
     *         -1 otherwise
     */
    public static int getPeakIndex(int[] array) {
        for (int i = 1; i < array.length - 1; i++) {
            if (array[i] > array[i - 1] && array[i] > array[i + 1]) {
                return i; // Found the first peak
            }
        }
        return -1; // No peak found
    }

    /** 
     * @param array an array of positive integer values
     * Precondition: array.length > 0
     * @return true if array contains values ordered as a mountain;
     *         false otherwise
     */
    public static boolean isMountain(int[] array) {
        int peakIndex = getPeakIndex(array);
        
        // A valid mountain must have a peak that is not at the beginning or the end
        if (peakIndex <= 0 || peakIndex >= array.length - 1) {
            return false;
        }

        // Check increasing sequence before peak
        for (int i = 0; i < peakIndex; i++) {
            if (array[i] >= array[i + 1]) {
                return false; // Must be strictly increasing
            }
        }

        // Check decreasing sequence after peak
        for (int i = peakIndex; i < array.length - 1; i++) {
            if (array[i] <= array[i + 1]) {
                return false; // Must be strictly decreasing
            }
        }

        return true; // It follows mountain property
    }

    // Main method for testing
    public static void main(String[] args) {
        int[][] testCases = {
            {1, 2, 3, 2, 1},
            {1, 2, 2, 1},
            {1, 2, 3, 4},
            {99, 33, 55, 77, 55},
            {3, 2, 1},
            {1, 2, 3, 2, 2}
        };

        for (int[] testCase : testCases) {
            System.out.println("Array: " + java.util.Arrays.toString(testCase));
            System.out.println("Peak Index: " + getPeakIndex(testCase));
            System.out.println("Is Mountain: " + isMountain(testCase));
            System.out.println();
        }
    }
}
```

# 2014c. FRQ 
```java 
public class TemperatureGrid {

    // A two-dimensional array of temperature values, initialized in the constructor (not shown)
    // Guaranteed not to be null
    private double[][] temps;

    /** 
     * Computes and returns a new temperature value for the given location.
     * @param row a valid row index in temps
     * @param col a valid column index in temps
     * @return the new temperature for temps[row][col]
     * - The new temperature for any element in the border of the array is the same as the old temperature.
     * - Otherwise, the new temperature is the average of the four adjacent entries.
     * Postcondition: temps is unchanged.
     */
    private double computeTemp(int row, int col) {
        int numRows = temps.length;
        int numCols = temps[0].length;

        // If the element is on the border, return the same value
        if (row == 0 || row == numRows - 1 || col == 0 || col == numCols - 1) {
            return temps[row][col];
        }

        // Compute the average of the four adjacent elements
        return (temps[row - 1][col] + temps[row + 1][col] + temps[row][col - 1] + temps[row][col + 1]) / 4.0;
    }

    /** 
     * Updates all values in temps and returns a boolean that indicates whether or not all the
     * new values were within tolerance of the original values.
     * @param tolerance a double value >= 0
     * @return true if all updated temperatures are within tolerance of the original values;
     *         false otherwise.
     * Postcondition: Each value in temps has been updated with a new value based on the 
     * corresponding call to computeTemp.
     */
    public boolean updateAllTemps(double tolerance) {
        int numRows = temps.length;
        int numCols = temps[0].length;
        boolean withinTolerance = true;

        // Create a new array to store updated temperatures
        double[][] newTemps = new double[numRows][numCols];

        // Compute new temperatures
        for (int row = 0; row < numRows; row++) {
            for (int col = 0; col < numCols; col++) {
                newTemps[row][col] = computeTemp(row, col);

                // Check if the difference is within tolerance
                if (Math.abs(newTemps[row][col] - temps[row][col]) > tolerance) {
                    withinTolerance = false;
                }
            }
        }

        // Update temps with the new computed values
        for (int row = 0; row < numRows; row++) {
            for (int col = 0; col < numCols; col++) {
                temps[row][col] = newTemps[row][col];
            }
        }

        return withinTolerance;
    }
}
```

# 2014d. FRQ 
 
```java
import java.util.*;

public class Stats {
    private ArrayList<ScoreInfo> scoreList; // Maintained in increasing score order

    /**
     * Records a score in the database, keeping the database in increasing score order.
     * If no other ScoreInfo object represents score, a new ScoreInfo object representing 
     * score is added to the database; otherwise, the frequency in the ScoreInfo object 
     * representing score is incremented.
     * 
     * @param score a score to be recorded in the list
     * @return true if a new ScoreInfo object representing score was added to the list;
     *         false otherwise
     */
    public boolean record(int score) {
        // Iterate through the list to find the correct position
        for (int i = 0; i < scoreList.size(); i++) {
            ScoreInfo info = scoreList.get(i);

            if (info.getScore() == score) {
                // Score already exists, increment frequency
                info.increment();
                return false;
            } else if (info.getScore() > score) {
                // Insert new ScoreInfo at the correct position
                scoreList.add(i, new ScoreInfo(score));
                return true;
            }
        }

        // If score is larger than all existing scores, add it at the end
        scoreList.add(new ScoreInfo(score));
        return true;
    }

    /**
     * Records all scores in stuScores in the database, keeping the database in increasing score order.
     * 
     * @param stuScores an array of student test scores
     */
    public void recordScores(int[] stuScores) {
        for (int score : stuScores) {
            record(score);
        }
    }

    // Constructor (not shown in prompt but necessary for testing)
    public Stats() {
        scoreList = new ArrayList<>();
    }

    // Method for testing
    public void printScores() {
        for (ScoreInfo info : scoreList) {
            System.out.println("Score: " + info.getScore() + ", Frequency: " + info.getFrequency());
        }
    }

    public static void main(String[] args) {
        Stats stats = new Stats();
        int[] scores = {85, 90, 75, 85, 100, 90, 95, 85, 100, 75};

        stats.recordScores(scores);
        stats.printScores();
    }
}

class ScoreInfo {
    private int score;
    private int numStudents;

    public ScoreInfo(int aScore) {
        score = aScore;
        numStudents = 1;
    }

    public void increment() {
        numStudents++;
    }

    public int getScore() {
        return score;
    }

    public int getFrequency() {
        return numStudents;
    }
}
```

# 2014 Takeaways 
- **Key Takeaways from This FRQ (Stats & ScoreInfo Classes)**:
  1. **Understanding Data Storage in Sorted Order**:
     - The `scoreList` (an `ArrayList<ScoreInfo>`) must maintain scores in increasing order.
     - No duplicate `ScoreInfo` objects should exist for the same score; instead, their frequency is incremented.
  
  2. **Proper Handling of the `record` Method**:
     - If the score already exists in the list, increment its frequency.
     - If the score does not exist, insert a new `ScoreInfo` object at the correct position to maintain sorted order.
     - The method should return true if a new score is added, false if an existing score is updated.

  3. **Efficiently Inserting a Score into a Sorted List**:
     - Use a loop to find the correct insertion point.
     - If the list is traversed and no larger value is found, append the score at the end.

  4. **Iterating Over an Array in `recordScores`**:
     - The `recordScores` method should call `record` for each score in the array to ensure all scores are properly inserted or updated in the database.

  5. **Encapsulation in Object-Oriented Programming**:
     - `ScoreInfo` encapsulates a score and its frequency with `getScore()`, `getFrequency()`, and `increment()`.
     - The `Stats` class is responsible for managing a collection of `ScoreInfo` objects.

  6. **Edge Cases to Consider**:
     - If `scoreList` is empty, the first score should be added directly.
     - If the new score is less than all existing scores, it should be inserted at index 0.
     - If the new score is greater than all existing scores, it should be appended at the end.
     - Ensure no duplicate `ScoreInfo` objects exist; only the frequency should be updated.

- **AP Exam Tips Based on This FRQ**:
  - ✅ Follow the method contract – Return the correct boolean values in `record`.
  - ✅ Think about efficiency – Finding the correct insertion point should ideally take O(n) time.
  - ✅ Test edge cases – Try inserting at the beginning, middle, and end of `scoreList`.
  - ✅ Use helper methods when needed – `recordScores` relies on `record`, reducing redundant code.
  - ✅ Maintain proper encapsulation – Avoid modifying `ScoreInfo` directly outside its class.

- **Skills Tested**:
  - Working with `ArrayLists`, maintaining order, and properly updating data are important skills for the AP CS A exam! 🚀

# 2015 FRQ
```java
public class DiverseArray {
    
    /**
     * Computes the sum of the elements in a one-dimensional array.
     * @param arr The input array.
     * @return The sum of the values in arr.
     */
    public static int arraySum(int[] arr) {
        int sum = 0;
        // Iterate through the array and sum up the elements
        for (int num : arr) {
            sum += num;
        }
        return sum;
    }

    /**
     * Computes the row sums of a two-dimensional array.
     * @param arr2D The input 2D array.
     * @return A 1D array where each element is the sum of a row in arr2D.
     */
    public static int[] rowSums(int[][] arr2D) {
        int[] rowSums = new int[arr2D.length];
        // Iterate over each row and compute its sum
        for (int i = 0; i < arr2D.length; i++) {
            rowSums[i] = arraySum(arr2D[i]); // Utilize arraySum for row sum computation
        }
        return rowSums;
    }

    /**
     * Determines if a 2D array is diverse, meaning no two rows have the same sum.
     * @param arr2D The input 2D array.
     * @return true if all row sums are unique, false otherwise.
     */
    public static boolean isDiverse(int[][] arr2D) {
        int[] sums = rowSums(arr2D); // Compute the row sums
        
        // Compare each sum with every other sum in the array
        for (int i = 0; i < sums.length; i++) {
            for (int j = i + 1; j < sums.length; j++) {
                if (sums[i] == sums[j]) {
                    return false; // Duplicate row sums found
                }
            }
        }
        return true; // All row sums are unique
    }
}
```

# 2015b. FRQ 

```java 
public class HiddenWord {
    private String hiddenWord;

    /**
     * Constructor that initializes the hidden word.
     * @param word the hidden word for the game.
     */
    public HiddenWord(String word) {
        hiddenWord = word;
    }

    /**
     * Generates a hint based on the player's guess.
     * @param guess the guessed word, same length as hiddenWord.
     * @return a hint string where:
     * - Matching letters in the correct position remain unchanged.
     * - Letters in the word but wrong position are replaced with "+".
     * - Letters not in the word are replaced with "*".
     */
    public String getHint(String guess) {
        StringBuilder hint = new StringBuilder();
        
        for (int i = 0; i < hiddenWord.length(); i++) {
            char guessChar = guess.charAt(i);
            char hiddenChar = hiddenWord.charAt(i);

            if (guessChar == hiddenChar) {
                hint.append(guessChar);  // Correct letter & position
            } else if (hiddenWord.indexOf(guessChar) != -1) {
                hint.append("+");  // Letter exists but wrong position
            } else {
                hint.append("*");  // Letter does not exist in hiddenWord
            }
        }

        return hint.toString();
    }

    // Main method for testing
    public static void main(String[] args) {
        HiddenWord puzzle = new HiddenWord("HARPS");

        System.out.println(puzzle.getHint("AAAAA")); // "*****"
        System.out.println(puzzle.getHint("HELLO")); // "H****"
        System.out.println(puzzle.getHint("HEART")); // "H+AR+"
        System.out.println(puzzle.getHint("HARMS")); // "HARP*"
        System.out.println(puzzle.getHint("HARPS")); // "HARPS"
    }
}
```

# 2015c. FRQ 

```java 
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class SparseArray {
    private int numRows;
    private int numCols;
    private List<SparseArrayEntry> entries;

    /** 
     * Removes the column col from the sparse array.
     * Precondition: 0 <= col < getNumCols()
     */
    public void removeColumn(int col) {
        // Use an iterator to remove entries with column index equal to col
        Iterator<SparseArrayEntry> iter = entries.iterator();
        while (iter.hasNext()) {
            SparseArrayEntry entry = iter.next();
            if (entry.getCol() == col) {
                iter.remove();
            }
        }

        // Adjust column indexes for entries with column index greater than col
        for (SparseArrayEntry entry : entries) {
            if (entry.getCol() > col) {
                entries.set(entries.indexOf(entry), 
                    new SparseArrayEntry(entry.getRow(), entry.getCol() - 1, entry.getValue()));
            }
        }

        // Reduce the number of columns by 1
        numCols--;
    }
}

// Supporting class for SparseArrayEntry
class SparseArrayEntry {
    private int row;
    private int col;
    private int value;

    public SparseArrayEntry(int r, int c, int v) {
        row = r;
        col = c;
        value = v;
    }

    public int getRow() {
        return row;
    }

    public int getCol() {
        return col;
    }

    public int getValue() {
        return value;
    }
}
```

# 2015 Takeaways: 
  - Emphasized core object-oriented programming concepts such as interfaces, encapsulation, list manipulation, and efficient data storage.

- **First Question (Diverse Array)**:
  - Involved iterating through 2D arrays and using helper methods to check for unique row sums.

- **Second Question (HiddenWord)**:
  - Focused on string processing, evaluating characters based on exact matches, partial matches, or absence in the hidden word.
  - Required looping through characters and using conditionals to construct a formatted hint efficiently.

- **Skills Reinforced**:
  - Methodical iteration and condition handling, critical skills for writing structured programs.

- **Third and Fourth FRQs**:
  - **SparseArray**: Focused on efficient storage of nonzero elements, utilizing a list of objects instead of a full 2D array.
  - **removeColumn**: Introduced safe list modification using iterators and index shifting.
  - **NumberGroup & MultipleGroups**: Tested interfaces and polymorphism, showcasing how an interface can unify different implementations while ensuring flexibility.
  - Used lists in MultipleGroups to manage various ranges, highlighting dynamic collections in Java.

- **Key Takeaways**:
  - Reinforced the importance of modular design, encapsulation, and efficient data manipulation.
  - These concepts are critical for success in the AP exam and real-world programming. :rocket:


