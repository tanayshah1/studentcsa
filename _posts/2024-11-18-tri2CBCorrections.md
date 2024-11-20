---
layout: post
title: 2014 Practice MC Corrections
type: post
comments: true
---

I got a 33/44 which puts me in a 4 range. I am pretty happy with this score but do see room to improve. I hope over this trimester to improve my grade up to the 5 standard. 

<img src="{{site.baseurl}}/images/cbquizscore.png" width = 500px height = auto alt="Image 15">

I got a total of 7 questions wrong: 

### Question 8: 

<img src="{{site.baseurl}}/images/cbquestion8.png" width = 500px height = auto alt="Image 1">


I chose D (I and III only), but that answer is incorrect because the third declaration, Student c = new Student("Juan", "15");, does not match any of the constructors defined in the Student class. The class only includes a no-argument constructor (Student()) and a parameterized constructor that takes a String and an int (Student(String name, int age)). However, Student("Juan", "15") passes two String arguments, and there is no constructor in the class that accepts this combination, which causes a compilation error. 

The correct answer is C (I and II only) because both Student a = new Student(); and Student b = new Student("Juan", 15); match the defined constructors and compile successfully. This mistake happened because I didn’t carefully check that the argument types in the third declaration matched the constructor signatures. Going forward, I’ll pay closer attention to the number, type, and order of arguments when evaluating constructor calls.

- I could refer back to team teach 5 
- I could look at my old team teach
- Team teach from period 3 
- Look at code from my stocks simulator (literally all the files have sorting and searching)

### Question 15 

<img src="{{site.baseurl}}/images/cbquestion15.png"  width = 500px height = auto alt="Image 2">

I chose E (I and III only), but the correct answer is A (I only). The first code segment correctly checks if the array is sorted by iterating through the array starting at index 1, comparing each element with the previous one (data[k - 1] > data[k]). If it finds any element out of order, it immediately returns false; otherwise, it returns true after completing the loop.

The third code segment is incorrect because it includes an unnecessary else block that causes the method to return true as soon as it finds the first pair of elements in order, which prematurely ends the loop and results in incorrect behavior. The second code segment is also incorrect because it doesn’t properly handle the loop bounds and may result in an ArrayIndexOutOfBoundsException when it accesses data[k + 1] for the last element. My mistake was not carefully analyzing how each segment iterates through the array and ensures the method works as intended.

- I could review team teach unit 7 
- I could review team teach unit 7 of the other period 
- The home page of my stocks simulator uses a sorting/searching algorithm

### Question 18 

<img src="{{site.baseurl}}/images/cbquestion18.png" width = 500px height = auto alt="Image 3">

I chose D, but the correct answer is B. The expression in option D, (int) (Math.random() * (myList.size() + 1)), generates random integers in the range [0, myList.size()], which includes myList.size(). However, valid indices for an ArrayList are only within the range [0, myList.size() - 1]. If the generated index equals myList.size(), attempting to access that index would throw an IndexOutOfBoundsException, as there is no valid element at that position.

Option B, (int) (Math.random() * myList.size()), is correct because it ensures the generated random indices are within the range [0, myList.size() - 1], which are all valid positions in the list. My mistake was failing to recognize that adding 1 to myList.size() in the calculation allows for an invalid index to be generated. Understanding the bounds of Math.random() and how it relates to valid indices is essential for correctly solving problems like this.

- I could review team teach unit 7 
- I could review team teach unit 6 
- I could review team teach unit 7 and 6 of period 3 
- review this [link](https://www.baeldung.com/java-common-array-operations)

### Question 19 

<img src="{{site.baseurl}}/images/cbquestion19.png" width = 500px height = auto alt="Image 4">

I chose A, but the correct answer is B. The original expression !( !(a != b) && (b > 7) ) simplifies using logical rules. First, the double negation !( !(a != b) ) simplifies to (a != b), so the expression becomes !( (a != b) && (b > 7) ). Next, using De Morgan's laws to distribute the negation, the expression simplifies to (a != b) (b <= 7). This matches the condition in option B, which reads (a != b) (b <= 7).

I selected A because I misunderstood how the negations interact with the logical operators. Option A incorrectly uses (b < 7) instead of (b <= 7), which makes it invalid. The key to solving this problem is carefully applying De Morgan’s laws and correctly simplifying each part of the expression step by step. This mistake shows that I need to pay closer attention to how logical transformations work when dealing with complex boolean expressions.

- I could review team teach unit 3
- review this [link](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)

### Question 22 

<img src="{{site.baseurl}}/images/cbquestion22.png" width = 500px height = auto alt="Image 5">

I chose C, but this is incorrect because the method toString is indeed declared and implemented in the Book class, which is the superclass of AudioBook. In Java, all objects inherit the toString method from Object, and any custom implementation in a class will override it. Since AudioBook extends Book, it automatically inherits the toString implementation from Book. Therefore, there is no issue with calling toString on an AudioBook object, and the code at line 5 will compile without any errors.

The correct answer is B because the variable books[0] is declared as type Book, and in Java, variables of a superclass type can only call methods that are defined in the superclass, even if the object they reference is an instance of a subclass. The method pagesPerMinute is declared in AudioBook but not in Book. As a result, the compiler will prevent the call to pagesPerMinute at line 4, as the type Book does not include this method in its definition. This restriction ensures type safety, which is why the code fails to compile at this line.

- lowk really stupid of me, review my own team teach 
- review literally any of my own code like literally anythning 

### Question 28 

<img src="{{site.baseurl}}/images/cbquestion28.png" width = 500px height = auto alt="Image 6">

I chose E, but this is incorrect. The correct answer is D. At Point B (which is right after x = x + y), n will still be greater than 2 because the only change to n happens later in the loop (at line 15, where n-- is executed). Therefore, at Point B, n will still have the same value it had at the beginning of the loop, which is greater than 2. However, the question asks about Point C, which occurs after the loop ends, and by that time, n will have been decremented in each iteration of the loop. So, at Point C, n may no longer be greater than 2, as it could have been reduced to 2 or below during the loop's execution.

The correct answer is D because, by Point C, n will sometimes still be greater than 2, but other times, it will be reduced to 2 or lower, depending on how many times the loop has run. Since the loop continues to execute as long as n > 2, Point C might occur after n has been decremented to 2 or less. This means n will sometimes be greater than 2 at Point C, but it can also sometimes be 2 or less, depending on how many iterations have taken place. Thus, n will not always be greater than 2 at Point C, making D the correct choice.

- review this [link](https://testbook.com/interview/java-logical-interview-questions)
- review this [link](https://www.javatpoint.com/reasoning)

### Question 37 

<img src="{{site.baseurl}}/images/cbquestion37.png" width = 500px height = auto alt="Image 7">

I chose B, but this is incorrect. The correct answer is D. Let's break down why:

For the code segment to print only the values 1 3 5, the loop condition must allow the values of x to be 1, 3, and 5, but exclude any other values. The condition x < 6 (option I) allows the loop to run while x is less than 6, which means the loop will print the values 1, 3, and 5 as expected. This is because the value of x starts at 1 and is incremented by 2 each time (x = x + 2), and the loop will stop when x reaches 6, which is excluded from the condition. The condition x < 7 (option III) will also work because the loop will still print 1, 3, and 5 before x reaches 7, and the condition x != 6 (option II) ensures that the loop stops at 6, excluding it from the printout as well.

Thus, both x < 6 (option I) and x < 7 (option III) correctly generate the desired output of 1 3 5, making D the correct answer. My mistake was in thinking that only x != 6 would work, but in fact, both x < 6 and x < 7 also achieve the same result, which is why the correct answer is D.

- I could review team teach unit 3
- review this [link](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)

### CB Analytics

<img src="{{site.baseurl}}/images/2014cbanalytics.png" width = 500px height = auto alt="Analytics">

- I need to study unit 9
- there was one question and i got that one question wrong
- Next i need to study unit 2 and 7, as i got a 75% accuracy rate 
- I am happy that I aced my own team teach and units 5, 8, 10