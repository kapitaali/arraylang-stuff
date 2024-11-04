
# challenge.dyalog.com

There are four rounds of the APL Challenge each year. You don’t need to participate in an earlier round to participate in the current one. Each round has ten problems and runs for three months, after which Dyalog Ltd awards three USD 100 prizes. You don’t have to answer every question, but your chance of winning increases as you answer more questions. A list of winners of previous rounds is available on the Dyalog website.

This listing features challenges in 2024. 1.1 means the first problem in challenge round 2024.1.

## 1.1: Reshaping Your World

APL's ⍴ is called Reshape. The symbol is a Greek Rho which is like r for reshape. Reshape takes a list of dimension lengths on its left and some data on its right, then reshapes the data into the specified shape.

For example, to get a table with 4 rows and 2 columns, filled with 1s, you'd write `4 2 ⍴ 1`.

When APL deals with text data, it uses single quotation marks before and after the text. For example `'abc'` will give a result that looks like abc.

Write an expression using ⍴ that reshapes 'Dyalog' into

    Dya
    log


## 1.2: Maxing Out

APL performs mathematical operations on entire collections of numbers, rather than just on a single number at a time. For example, `10 20 30 + 4 5 6` gives `14 25 36` and `10 × 1 2 3 is 10 20 30`.

The ⌈ symbol computes the maximum. When given numbers on both its left and its right, the maximum is the larger of corresponding numbers. Therefore, `10 4 ⌈ 2 6` gives `10 6`. Think of ⌈ as vertical line with a horizontal indicator tick at the maximum.

Write an expression that adjusts the values `1 6 1 8 0 3` so all the numbers are equal to or greater than 5, that is, gives the result `5 6 5 8 5 5`.


## 1.3: A Slice of

When the Circle symbol ○ is on the left of one or more numbers, it multiplies these numbers by pi (π). The symbol is hinting at pi being the ratio between a circle's circumference and its diameter.

Write a single expression that computes the circumference of circles with diameters of 2, 7, 1 and 8 units, giving the result `6.283185307 21.99114858 3.141592654 25.13274123`.


## 1.4: Which of Me is in You?

The Element Of function ∊ returns a 0 or 1 for every element in the array on its left; 1 indicates that the corresponding element was found as an element of the array on the right, while 0 indicates that it wasn't. For example, `1 16 12 ∊ 4 25 1 12 15 7` gives `1 0 1`. For this reason, the Element Of symbol is derived from the Greek letter Epsilon, which is like e for element.

The Indices function ⍸ takes an array of 1s and 0s on its right, and returns a list of the indices of all 1s, ignoring any 0s. For example, `⍸ 1 0 1` returns `1 3`. The function uses the underscored Greek Iota symbol, similar to an underscored letter i for indicators into indices.

An APL function takes the result of all code to its right (until the end of the expression) as its right argument. For example, `2×3+4` gives `14` (rather than the 10 you might expect) because the × takes the result of 3+4 as its right argument. Similarly, -2+4 gives ¯6 because - negates 2+4.

Write an expression that identifies the characters of `'BEAUTIFUL'` that also appear in `'SQUIGGLES'` by listing their positions in `'BEAUTIFUL'`, that is, `2 4 6 8 9` (corresponding to `E U I U L`).


## 1.5: In Summation

In APL, we can have entire lists be elements of other lists. Consider `1 ((2 3 4) (10 20)) (4 2)`. This is a 3-element list. The first element is the number 1 and the last element is the list `4 2`. The middle element is itself a 2-element list consisting of the lists `2 3 4` and `10 20`.

You've already met the ∊ symbol in the previous problem, but that was with an array on each side. If there's only an array on its right, then it means Enlist: It flattens whatever intricate array of arrays it is given into a simple list. Thus, ∊ is also like e for enlist. An example of its usage is with the above list: `∊ 1 ((2 3 4) (10 20)) (4 2)` gives the simple list `1 2 3 4 10 20 4 2`.

Reduce is denoted / which inserts the function on its left between the elements of the array on its right. For example, ×/ 1 2 3 4 5 computes the factorial of 5 (that is, 1×2×3×4×5).

Write an expression that computes the sum of all the numbers in `(1 6 1) ((3 1 4 1 5) (2 7 1 8)) 2`, namely 42.


## 1.6: Go Forth and Multiply

The Index Generator function ⍳ takes a number on its right and generates the indices from 1 until that number. For example, ⍳3 gives 1 2 3. The symbol ⍳ is a Greek Iota symbol, which is similar to the letter i for index or indices.

If you put ∘. ("jot dot") to the immediate left of a function, then it produces a table of that function applied between all the combinations of elements from the arguments. Its left argument forms the row headings (down the left side) and its right argument forms the column headings (across the top). Remember from problem 2 that ⌈ is Maximum? Here's a maximum-table in APL form – and as you might see it in a book:

        3 1 4 ∘.⌈ 2 7 1 8
      
    3 7 3 8
    2 7 1 8
    4 7 4 8

    ⌈	2	7	1	8
    3	3	7	3	8
    1	2	7	1	8
    4	4	7	4	8

Note that you can use parentheses to govern the order of operations, limiting any right argument so it only goes as far as the nearest closing parenthesis on its right. As we explained in problem 4, the code 2×3+4 gives 14 but if you write (2×3)+4 then you get 10 as the right argument of × is limited to be just 3.

The challenge here is to produce a multiplication table for the numbers up to 12:

     1  2  3  4  5  6  7  8   9  10  11  12
     2  4  6  8 10 12 14 16  18  20  22  24
     3  6  9 12 15 18 21 24  27  30  33  36
     4  8 12 16 20 24 28 32  36  40  44  48
     5 10 15 20 25 30 35 40  45  50  55  60
     6 12 18 24 30 36 42 48  54  60  66  72
     7 14 21 28 35 42 49 56  63  70  77  84
     8 16 24 32 40 48 56 64  72  80  88  96
     9 18 27 36 45 54 63 72  81  90  99 108
    10 20 30 40 50 60 70 80  90 100 110 120
    11 22 33 44 55 66 77 88  99 110 121 132
    12 24 36 48 60 72 84 96 108 120 132 144


## 1.7: The Sum Total

You can create your own function by putting an expression in curly braces. Inside this expression, ⍵ denotes the right argument (it being the right-most letter of the Greek alphabet). For example, a function to subtract one from the square of its argument could be written {(⍵×⍵)-1}.

In a function that takes two arguments, ⍺ denotes the left argument (it being the left-most letter of the Greek alphabet). For example, a function that computes twice the sum of its arguments could be written {2×⍺+⍵}.

Consider using Reduce / from problem 5.

Write a function that takes a list of prices for some goods as left argument and a list of corresponding quantities for these goods as right argument, then computes the total price for the purchase:

        4 5 2 {solution} 3 6 0
    42

The above should compute (4×3) + (5×6) + (2×0) to arrive at the answer 42.

        18.65 19.26 19.71 20.19 {solution} 6 0 2 2
    191.7


## 1.8: Jump into Your Racecar

The Reverse function ⌽ reverses lists; `⌽ 1 2 3` gives `3 2 1`. The symbol evokes reflection in a vertical mirror.

In APL, comparisons are normal functions, and apply to elements (just like arithmetic), returning 1s when true and 0s when false. For example, `2 7 1 8 2 8 = 2` gives `1 0 0 0 1 0`.

Did you know that you can use multiplication to check if two conditions are both true? `0 1 0 1 × 0 0 1 1` gives `0 0 0 1` indicating that only in the last position did we have true (1) in both arguments.

Write a function which takes a lowercase word and answers whether it is a palindrome, that is, it remains unchanged when reversed:

        {solution} 'racecar'
    1

        {solution} 'kayak'
    1

        {solution} 'dragster'
    0

        {solution} 'canoe'
    0


## 1.9: What are the Odds?

The Remainder function | computes the remainder when the integers on the right are divided by the integers on the left. For example, 4|14 gives 2 because 4 goes into 14 a total of 3 times with 2 remaining.

The Compress function ⌿ takes a list of 1s and 0s on its left. It filters the array on the right so that only those elements that match up to a 1 on the left array remain.

Write a function that takes a list of positive integers on its right, and removes all the even numbers, leaving only the odd numbers. For example:

        {solution} 10 9 8 7 6 5 4 3 2 1
    9 7 5 3 1

        {solution} 3 5 7 11
    3 5 7 11

No odd numbers here so it looks like there's no result:

      {solution} 42 48



## 1.10: Frequent Fliers

The Unique function ∪ removes any duplicates from its argument, leaving only unique items. For example, ∪ 'abracadabra' gives 'abrcd'. The symbol is of course a stylised letter u for unique.

Note that when +/ is applied to a table, it sums each row and returns a list of the sums. Remember the ∘. construct from problem 6? You might want to use that.

Write a function which takes a list on its right, and computes, for each unique element, how many times it appears in the whole list:

        {solution} 4 4 4 4 4
    5

        {solution} 'BAABCCACDA'
    2 4 3 1

        {solution} 2 7 1 8 2 8 1 8
    2 1 2 3

----

## 2.1: Drop Dead

APL's ↓ is used to drop elements. (The symbol hints at the direction things fall when dropped.) It takes a number on its left and a list on its right. The number specifies how many elements to drop from the left of the list.

For example, `1 ↓ 3 1 4 1 5` gives `1 4 1 5`.

Text is denoted in APL by including single quotation marks before and after the text. For example 'abc' will give a result that looks like abc.
Write a single expression using ↓ that turns the text 'allocation' into 'location'. 


## 2.2: Meet Me at the Intersection

The symbol ∩ is called Intersection. It keeps items from the list on its left that are also found in the list on its right. Note that the symbol is the same as used in set theory, and its shape is like the letter n as in intersection. For example, `3 1 4 1 5 ∩ 1 2 3` gives `3 1 1` and `'Drake Mallard' ∩ 'dark'` gives `rakaard`.

Write a single expression that uses ∩ to find the intersection of 'piece of cake' and 'aeiou'. The result should be ieeoae.


## 2.3: Minimalism

APL can perform mathematical operations on entire collections of numbers, rather than just on a single number at a time. For example, `10 20 30 + 4 5 6` gives `14 25 36` and `10 × 1 2 3` is `10 20 30`.

The ⌊ symbol implements a mathemetical operation that computes the minimum of two values. Think of ⌊ as a vertical line with a horizontal indicator tick at the minimum. You could also view it as a styled letter L, since it gives the Lowest of its arguments. When given numbers on both its left and its right, the minimum is the lowest of each pair of numbers. For example, `10 4 ⌊ 2 6` gives `2 4`.

Use ⌊ to write a single expression, without using parentheses, to limit the elements of `1 2 3 4 5 6 7 8 9 10` so they are no greater than 7, that is, elements greater than 7 become 7. The result will be `1 2 3 4 5 6 7 7 7 7`. 


## 2.4: Staying In Bounds

The Maximum function ⌈ is just like Minimum (which you met in problem 3), except that it returns the larger of corresponding elements. In this case, the symbol ⌈ provides a reminder because the tick is at the top of the vertical bar. For example, `3 1 4 1 5 9 ⌈ 2 7 1 8 2 8` returns `3 7 4 8 5 9`.

An APL function takes the result of all the code to its right (until the end of the expression) as its right argument. For example, 2×3+4 gives 14 (rather than the 10 as you might expect from traditional mathematics) because the × takes the result of 3+4 as its right argument. Similarly, -2+4 gives ¯6 (APL uses a high minus ¯ to indicate negative numbers) because - negates 2+4.

Use ⌊ and ⌈ to write a single expression, without using parentheses, that clamps the elements of `1 2 3 4 5 6 7 8 9 10` between 3 and 7, that is, elements less than 3 become 3 and elements greater than 7 become 7. The result will be `3 3 3 4 5 6 7 7 7 7`. 


## 2.5: Self Replication

The Replicate function ⌿ takes a list of numbers on its left and a list of equal length on its right. For each number in the list on the left, Replicate puts that many copies of the corresponding element of the right argument into the result. For example, `2 0 3 1 2 3 ⌿ 'DYALOG'` returns `DDAAALOOGGG`.

The Index Generator function ⍳ takes a number on its right and generates the indices from 1 until that number. For example, ⍳3 gives 1 2 3. The symbol ⍳ is a Greek Iota symbol, which is similar to the letter i for index or indices.

Note that you can use parentheses to govern the order of operations, limiting any right argument so it only goes as far as the nearest closing parenthesis on its right. As explained in problem 4, the code 2×3+4 gives 14 but if you write (2×3)+4 then you get 10 as the right argument of × is limited to be just 3.

Using ⍳, ⌿, parentheses, and the number 5, write a single expression that returns `1 2 2 3 3 3 4 4 4 4 5 5 5 5 5`.


## 2.6: Double Vision

Comparison functions like = and < return 1 when the indicated relation is true and 0 when it is false. For example, `'dyalog' = 'analog'` returns `0 0 1 1 1 1` and `3 ≥ 1 2 3 4 5` returns `1 1 1 0 0`.

Reduce is denoted / and inserts the function on its left between the elements of the array on its right. For example, `×/ 1 2 3 4 5` computes the factorial of 5 (that is, 1×2×3×4×5).

Drop (see problem 1) can take a negative number on its left to remove from the right. For example, `¯1 ↓ 3 1 4 1 5` gives `3 1 4 1`. (Remember from problem 4 that we write negative numbers with a high minus).

Write a single expression that uses ↓, =, parentheses, + and / to count the number of times a letter appears immediately after an identical letter in 'bookkeeper'. The result should be 3.

Hint: You can use ↓ for analysis of the relationship between adjacent elements in an array. For example, given the array `3 1 4 1 5 9` and the goal of finding out which elements are greater than their predecessor, start by dropping the first and last elements (separately), that is, `1 ↓ 3 1 4 1 5 9` and `¯1 ↓ 3 1 4 1 5 9` giving `1 4 1 5 9` and `3 1 4 1 5` respectively. Now compare their results with `1 4 1 5 9 > 3 1 4 1 5`, which returns `0 1 0 1 1`. Putting all the pieces together gives the APL expression `(1 ↓ 3 1 4 1 5 9) > (¯1 ↓ 3 1 4 1 5 9)`. Placing the result beneath the original array as shown below illustrates that the goal has been achieved; 1 in the result indicates the pairs of adjacent elements in which the right element is greater than the left one:

    3 1 4 1 5 9
     0 1 0 1 1


## 2.7: Things are Looking Up

You can create your own function by putting an expression in curly braces. Inside this expression, ⍵ refers to the right argument (it being the right-most letter of the Greek alphabet). For example, a function to subtract one from the square of its argument could be written {(⍵×⍵)-1}.

Time series data is a sequence of data points collected over regular time periods. Examples of time series data include daily or hourly temperature readings or stock prices. Any given data point might be greater than, less than, or equal to the previous data point. APL has a long history of being used for time series data analysis.

Write a function that takes a vector of numbers on its right (representing time series data) and computes how many of the vector's numbers are greater than their predecessor. For example:

        {solution} 10 9 8 7 6 5 4 3 2 1
    0

        {solution} 1 2 3 4 5 6 7 8 9 10
    9

        {solution} ¯2 ¯2 0 1 4 ¯2 ¯1 ¯1 2 ¯1
    5

        {solution} 5 10
    1

Hint: See Problem 6.


## 2.8: Unique Characters in APL

The Unique Mask function ≠ takes an array as its right argument and returns a 1 marking the first occurrence of an element, 0 for subsequent occurrences. For example, `≠ 3 1 4 1 5` returns `1 1 1 0 1` and `≠ 'DYALOG'` returns `1 1 1 1 1 1`.

The Boolean/mathematical And function ∧ (symbol taken from formal logic) returns 1 if both left and right arguments are 1, but 0 if either is 0. For example, `1 1 0 0 ∧ 0 1 0 1` returns `0 1 0 0`.

Write a function that takes a vector as its argument and returns 1 if the elements are all unique, 0 otherwise.

        {solution} 'DYALOG APL'
    0

        {solution} 1 2 3 4 5 6
    1

        {solution} 3 1 4 1 5 9 2 6
    0

        {solution} 3.1415926 'DYALOG' 42 'APL'
    1

Hint: ≠ and ∧ combined with / (see problem 6) can be useful here.


## 2.9: Caseless Sorting

Brackets […] select elements from the vector immediately to the left of [ using indices between [ and ]. For example: `'SYIM'[4 3 1 1 2]` returns `MISSY` and `4 25 1 12 15 7[3 1 6 4 5 2]` returns `1 4 7 12 15 25`.

The Grade function ⍋ is useful for sorting arrays. For a given array, it returns the indices you need when you want to sort that array. For example, `⍋ 4 25 1 12 15 7` returns `3 1 6 4 5 2`. Putting the result of Grade inside brackets `4 25 1 12 15 7[⍋ 4 25 1 12 15 7]` returns the sorted array `1 4 7 12 15 25`.

The system function ⎕C converts uppercase letters into their lowercase equivalents. This is useful for comparing texts. For example, `⎕C 'Hello World!'` gives `hello world!`.

Write a function that uses ⎕C, ⍋, and brackets to sort the given vector of character vectors, without considering letter case.

        {solution} 'Morten' 'brian' 'Adám' 'Bjørn' 'michael'
    Adám  Bjørn  brian  michael  Morten 

        {solution} 'ANN' 'ida' 'RAY' 'aMY' 'aMY'
    aMY  aMY  ANN  ida  RAY 

        {solution} 'eVA' 'FAY' 'Ray' 'Eve'
    eVA  Eve  FAY  Ray 


## 2.10: X Marks the Spot

The Reverse function ⌽ reverses a given array. For example, `⌽ 1 2 3` returns `3 2 1`. The symbol evokes reflection in a vertical mirror.

Complementing the And function from problem 8, the Or function ∨ (symbol also taken from formal logic) returns 1 if its left or right argument is 1 (or both are 1), but 0 if both are 0. For example, `1 1 0 0 ∨ 0 1 0 1` gives `1 1 0 1`.

If you put ∘. ("jot dot") to the immediate left of a function, then it produces a Table of that function applied between all the combinations of elements from the arguments. Its left argument forms the row headings (down the left side) and its right argument forms the column headings (across the top). Here's a multiplication-table in APL form – and as you might see it in a book:

        1 2 3 ∘.× 1 2 3 4
    1 2 3  4
    2 4 6  8
    3 6 9 12

    ×	1	2	3	4
    1	1	2	3	4
    2	2	4	6	8
    3	3	6	9	12

Write a function that takes a positive integer, n, as its argument and returns an n×n Boolean table (matrix) that uses 1s to depict an "X" along its diagonals (everything else is 0).

        {solution} 5
    1 0 0 0 1
    0 1 0 1 0
    0 0 1 0 0
    0 1 0 1 0
    1 0 0 0 1

        {solution} 4
    1 0 0 1
    0 1 1 0
    0 1 1 0
    1 0 0 1

        {solution} 1
    1

Hint: ⍳ (see problem 5), ⌽, ∨, and = combined with ∘. can be useful here.


----

## 3.1: Existentialism

In APL text data must appear between single quotes. For example 'ABC' will give a result that looks like ABC.

In APL, yes/no questions are answered with 1 for "yes" and 0 for "no".

The symbol ∊ is Exists In (and it looks like E too) because it reports whether letters of the text on its left exist in the text on its right. For example, `'APL' ∊ 'DYALOG'` gives `1 0 1` because:

    1: yes, 'A' exists in 'DYALOG'
    0: no, 'P' does not exist in 'DYALOG'
    1: yes, 'L' exists in 'DYALOG'

Note that what we’re looking for goes on the left of the ∊, and where we’re looking goes on its right.

Write a single line of APL that uses ∊ to show that each of the letters in the English alphabet `'ABCDEFGHIJKLMNOPQRSTUVWXYZ'` (← click to copy) is found in the text `'THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG'` (← click to copy). The result should be `1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1`, that is, 26 1s.


## 3.2: Comparing This to That

APL has six symbols that compare the data on their left the data on their on the right. Just like ∊ from Problem 1, they give 1 for "yes" and 0 for "no" when answering whether the statement is true.

The six comparisons are Smaller Than (<), Smaller Than Or Equal To (≤), Equal To (=), Bigger Than Or Equal To (≥), Bigger Than (>), and Not Equal To (≠).

You can check what each symbol will give in a line like 2 < 3 by using its name instead of its symbol. For example, we could say "Is 2 Smaller Than 3?" — yes, that's a true statement, so 2 < 3 will give 1 for "yes".

APL can compare entire lists of numbers, rather than just single numbers. For example, `1 2 3 = 5 4 3` gives `0 0 1` because:

    0: no, 1 is not equal to 5
    0: no, 2 is not equal to 4
    1: yes, 3 is equal to 3

Which comparison symbol will give 0 1 0 1 0 with 3 5 4 8 6 on its left and 3 4 5 3 9 on its right?

In other words, which symbol would you place in the box ( ⎕ ) of the APL code `3 5 4 8 6 ⎕ 3 4 5 3 9` (← click to copy) so that the answer will be `0 1 0 1 0`?


## 3.3: Picky Picky

The symbol ⊃ is called Pick because, when given a number (let’s call it n) on its left and a list on its right, it picks item number n from the list. For example, `2 ⊃ 'DYALOG'` gives `Y` and `2 ⊃ 'DYALOG' 'APL'` gives `APL`.

So far, we’ve only used text (in single quotes) and lists of numbers like `'DYALOG APL'` and `3 1 4 1 5 9`. Both of these are simple lists; one is a list of letters (we count space as a letter), the other is a list of numbers (the spaces between numbers don’t count). APL can also handle lists of lists, and so on. For example, `'DYALOG' 'APL'` is a list of two texts, that is, a list of two lists of letters.

If we want additional levels of lists inside lists, we use round brackets to mark each list. For example, `(1 2 3)(2 7 1 8)` is a list of two lists of numbers, and `('KEN' 'IVERSON')('DYALOG' 'APL')` is a list of lists of texts (with each text itself being a list of letters).

If we give Pick a list of numbers (rather than a single number) on the left (we’ll still call it n), then:

* the first number from n picks the appropriate item from the list on the right of Pick
* the second number from n picks the appropriate item from that list
* and so on

For example, `2 1 ⊃ 'DYALOG' 'APL'` will pick:

    item 2 from 'DYALOG' 'APL', which is 'APL'
    item 1 from 'APL', which is 'A'

Write a line of APL using ⊃ that will pick the 'G' from `('KEN' 'IVERSON')('DYALOG' 'APL')` (← click to copy).


## 3.4: Partition Condition

Partition ⊆ is a function (symbol) that cuts up text into parts: It takes a text as its right argument and a list of numbers as its left argument. The list of numbers has only 1s and 0s, and specifies how to cut the text into parts. Characters (letters and spaces) in the text corresponding to 0s are discarded; a new part is then started. For example, `0 0 1 1 0 1 1 1 1 0 0 1 1 1 ⊆ 'THIS PARTITION'` gives:

    ┌──┬────┬───┐
    │IS│PART│ION│
    └──┴────┴───┘

If your APL system shows this as  is  part  ion , without the boxes, then enter `]Box on`.

We can show what’s going on like this:

    0 0 1 1 0 1 1 1 1 0 0 1 1 1
    t h i s   p a r t i t i o n

Remember the comparison functions from Problem 2? We used them with single numbers on both sides and with lists of numbers on both sides. However, they can also take a single number on the left and a list on the right. For example, `4 < 3 5 7` gives `0 1 1`, because:

    0: no, 4 is not less than 3
    1: yes, 4 is less than 5
    1: yes, 4 is less than 7

Furthermore, we only used the comparison functions with numbers, but two of them, = and ≠, work on characters too. For example, `'APL' = 'ABC'` gives 1 0 0, because:

    1: yes, A is equal to A
    0: no, P is not equal to B
    0: no, L is not equal to C

An APL function takes the answer of all the code to its right as its right argument. For example, 2×3+4 gives 14, rather than the 10 that you might expect. This is because the × takes the answer of 3+4 as its right argument. However, you can use round brackets to change the order in which things are calculated, limiting any right argument so it only goes as far as the nearest closing bracket "…)" on its right: (2×3)+4 gives 10.

Using ⊆, one of the comparison functions, and round brackets, write an expression that will cut the text `'THE QUICK BROWN FOX'` into words at the space characters (' '). The answer should be

    ┌───┬─────┬─────┬───┐
    │THE│QUICK│BROWN│FOX│
    └───┴─────┴─────┴───┘

(Hint: You will need to use the text 'THE QUICK BROWN FOX' twice, so don’t forget that you can click on it to copy it.)


## 3.5: You Can Scan!

The APL symbols you’ve met so far take one data argument on each side. These symbols are called functions. APL also has operators which take a data argument on the right (just like functions), but on the left take a function instead of data. Each operator uses the given function with the given data in a specific way. Scan \ is such an operator. It takes a list on its right, and a function on its left. The function could be Plus (+) or Times (×), or any of the comparison functions you met in Problem 2.

Scan gives an answer of the same length as the given list:

* The first item of the answer is the same as the first item in the list
* The second item of the answer is calculated by putting the function between the first and second items of the list
* The third item of the answer is calculated by putting the function between the first three items of the list
* and so on

The first item of the answer is the same as the first item in the list. The second item of the answer is calculated by putting the function between the first and second items of the list. The third item of the answer is calculated by putting the function between the first three items of the list. And so on.

For example, `+\ 1 9 2 0 1 2 1 7` gives `1 10 12 12 13 15 16 23`, as follows:

    1                              →   1
    1 + 9                          →  10
    1 + 9 + 2                      →  12
    1 + 9 + 2 + 0                  →  12
    1 + 9 + 2 + 0 + 1              →  13
    1 + 9 + 2 + 0 + 1 + 2          →  15
    1 + 9 + 2 + 0 + 1 + 2 + 1      →  16
    1 + 9 + 2 + 0 + 1 + 2 + 1 + 7  →  23

and `<\ 0 0 1 0 1 0 1` gives `0 0 1 0 0 0 0`, as follows:

    0                          →  0
    0 < 0                      →  0
    0 < 0 < 1                  →  1
    0 < 0 < 1 < 0              →  0
    0 < 0 < 1 < 0 < 1          →  0
    0 < 0 < 1 < 0 < 1 < 0      →  0
    0 < 0 < 1 < 0 < 1 < 0 < 1  →  0

Remember from the previous problem that, when an APL expression contains multiple functions, they are applied from right to left. So, `0 < 0 < 1`, which is `0 < (0 < 1)`, which is `0 < (1)`, and so on.

Which comparison function, when used with Scan and a right argument of `0 1 1 0 0 1 0 1 0 1 1 0`, will give `0 1 0 0 0 1 1 0 0 1 0 0`?

In other words, which symbol would you place in the box ( ⎕ ) of the APL code `⎕\ 0 1 1 0 0 1 0 1 0 1 1 0` (← click to copy) so the expression gives `0 1 0 0 0 1 1 0 0 1 0 0`?


## 3.6: Leading Question

Every APL function you’ve met to far, has taken two arguments, but some functions only take one argument. For those, the single argument goes on the right. The Not function ~ is an example of such a function. It swaps 1s and 0s, turning each 1 ("yes") in its right argument into a 0 ("no") and each 0 ("no") into a 1 ("yes"): `~ 1 1 0 1 0 0 1` gives `0 0 1 0 1 1 0`.

In the last problem you learned about the Scan operator. The related Reduce operator / returns the last item of what would have been Scan’s result. For example, `+/ 1 9 2 0 1 2 1 7` returns `23` (that is, 1+9+2+0+1+2+1+7).

You can use the And function ∧ to see whether both of two statements are true. This gives 1 ("yes") if both its left and right arguments are 1 ("yes"); if any of its arguments are 0 ("no"), it gives 0 ("no").

Using Plus (+), Reduce (/), And (∧), Scan (\), Not (~), and Exists In (∊), write an APL expression that counts how many consonants (non-vowels) are at the beginning of the word `'SCHNITZELS'` (← click to copy), before the first vowel (which is I).

(Use 'AEIOU' as your list of vowels.)


## 3.7: You Have My Word

You can create your own function by putting an expression in curly brackets. Within this expression, if needed, ⍺ (alpha) refers to the argument to the left of { and ⍵ (omega) refers to the argument to the right of }. (This is because alpha and omega are the left-most and right-most letters of the Greek alphabet, respectively.) For example, a function that adds its arguments and then multiplies by two could be written `{2×⍺+⍵}`.

Using Pick (⊃) and your answer for Problem 4, write a function that takes a number n as its left argument and a text that has words (with spaces between them) as its right argument, and gives word number n from the text. For example:

        1 {answer} 'THE QUICK BROWN FOX'
    THE

        3 {answer} 'THE QUICK BROWN FOX'
    BROWN

        5 {answer} '   EXTRA    SPACES DO NOT MATTER   '
    MATTER

(The text will have at least n words.)


## 3.8: Give Me a Break!

In Problem 4, you learnt how to cut text into parts based on the location of space characters. You will now take that a step further by cutting a text into parts based on the location of characters from a list. Remember from Problem 3 that a text is just a list of characters.

Using Not (~), Exists In (∊) and Partition (⊆), write a function that takes a text on its right and a list of characters on its left and cuts the text at those characters. For example:

        ':- ,()' {answer} 'THREE-CHARACTER ANIMALS: CAT,DOG,ELK,EEL (AND BAT)'
    ┌─────┬─────────┬───────┬───┬───┬───┬───┬───┬───┐
    │THREE│CHARACTER│ANIMALS│CAT│DOG│ELK│EEL│AND│BAT│
    └─────┴─────────┴───────┴───┴───┴───┴───┴───┴───┘

        ':/.?=' {answer} 'HTTPS://WWW.BLOOFO.COM:8080?NAME=VALUE'
    ┌─────┬───┬──────┬───┬────┬────┬─────┐
    │HTTPS│WWW│BLOOFO│COM│8080│NAME│VALUE│
    └─────┴───┴──────┴───┴────┴────┴─────┘


## 3.9: Turning up the Heat

Remember from Problem 7 that ⍺ refers to the left argument of your own function, but you also learnt in Problem 6 that not all functions need a left argument. Such functions do not need an ⍺. For example, a function to multiply its sole (right) argument by itself and then subtract one could be written `{(⍵×⍵)-1}`.

Write a function that describes a temperature given in degrees Fahrenheit: If the temperature is below 32 (you don’t need to handle negative temperatures) it is `'FREEZING'`, while if it is 32 or higher, but below 50, it is merely `'COLD'`. From 50 it becomes `'CHILLY'`, then from 70 it is `'PLEASANT'`, from 85 it is `'HOT'` and at or above 95 it is `'HELLISH'`. For example:

         {answer} 33
    COLD

        {answer} 14
    FREEZING

        {answer} 83
    PLEASANT


## 3.10: Pick a Vowel

Using the techniques you have learnt so far, write a function that takes a word as its right argument and gives the word’s first vowel as its answer. For example:

        {answer} 'SPHRAGISTIC'
    A

        {answer} 'SEAL'
    E

        {answer} 'ICONOGRAPH'
    I

(The given word will have at least one vowel. Use 'AEIOU' as your list of vowels.)


----

## 4.1: Easy as 1-2-3

It is easy to count in APL. Just write the symbol ⍳ (iota, a Greek letter), to the left of a number; this will give you all the whole numbers from 1 to the number you wrote. (Iota is like an i for integers, which means whole numbers.) For example. `⍳ 10` gives `1 2 3 4 5 6 7 8 9 10`

Write some APL code that uses ⍳ to get the numbers from 1 to 42. The result should be `1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40`


## 4.2: Rectangle Areas

In APL, multiplication uses the symbol × (times). It works as you’d expect. However, in APL all basic mathematical symbols can work on multiple numbers at once. For example, `5 2 3 × 2 4 3` gives `10 8 9` because:

    5 × 2 is 10
    2 × 4 is 8
    3 × 3 is 9

Write some APL code that uses a single × to calculate the area of three rectangles. The first has sides of length 3 and 2, the second has sides of length 1 and 7, and the third has sides of length 4 and 2. The result should be 6 7 8


## 4.3: Selection

In APL, text must appear between single quotes ('). For example, 'ABC' will give a result that looks like ABC.

You can select specific letters from a text by putting square brackets ( [] ) to the right of the text. Inside the square brackets, you put numbers that say which letters you want to get from the text. For example, `'ABCDE'[1]` gives you the letter `A` because that’s the 1st letter of 'ABCDE'. Similarly, `'ABCDE'[5 2 2]` gives you `EBB`, because:

    The 5th letter of 'ABCDE' is E
    The 2nd letter of 'ABCDE' is B
    The 2nd letter of 'ABCDE' is B

Write some APL code using square brackets that transforms `'DYALOG APL'` into `'GO POLLY'`


## 4.4: How the Tables have Turned

An APL symbol takes the answer of all the code to its right as its right argument. For example, 2×3+4 gives 14, rather than the 10 that you might expect. This is because the × takes the answer of 3+4 as its right argument.

⍴ (Rho, a Greek letter) is called Reshape (Rho is like an r for reshape). It can take a list of two numbers on the left and any data on the right. The two numbers state how many rows and columns the data on the right should be reshaped into.

For example, to get a table with 3 rows and 5 columns, filled with 7 9 4, you'd write `3 5 ⍴ 7 9 4`. It'd look like this:

    7 9 4 7 9
    4 7 9 4 7
    9 4 7 9 4

The numbers are reused as needed to fill the rows and columns, first filling the top row, then the next one, and so on.

Using Reshape (⍴) and Iota (⍳ from problem 1), create the following table of numbers:

     1  2  3  4
     5  6  7  8
     9 10 11 12
    13 14 15 16
    17 18 19 20
    21 22 23 24


## 4.5: All Backwards

So far, we’ve only used text (in single quotes, like 'DYALOG APL') and lists of numbers (with spaces between them, like 3 1 4 1 5 9). Both of these are simple lists; one is a list of letters (we count space as a letter), the other is a list of numbers (the spaces between numbers don’t count). APL can also handle lists in which every element is itself a list. For example, `'DYALOG' 'APL'` is a list of two texts, that is, a list of two lists of letters.

⌽ is called Reverse. `⌽ 3 1 4` gives `4 1 3`.

Now let’s look at a more complicated example: `⌽ 2 3 ⍴ 'SAWNET'`. Remember from the previous problem that ⌽ takes the answer of `2 3 ⍴ 'SAWNET'` as its right argument. Therefore, the result is:

    WAS
    TEN

The APL symbols that you’ve met so far take either one data argument (on the right) or two data arguments (one on each side). These symbols are called functions.

Some APL symbols take a data argument on the right (just like a function), but on the left take a function instead of data. These symbols are called operators. An operator uses the given function with the given data in a specific way. Each (¨) is such an operator. It takes a list on its right, and a function on its left, and applies the function to each element of the list. For example, ⍳¨ 3 1 4 gives:

    ┌─────┬─┬───────┐
    │1 2 3│1│1 2 3 4│
    └─────┴─┴───────┘

Using Reverse (⌽) and Each (¨), turn 'mood' 'net' 'pop' into:

    ┌───┬───┬────┐
    │pop│ten│doom│
    └───┴───┴────┘

Note that both the list of words, and each word, have been reversed.


## 4.6: Palindrome

In APL, yes/no questions are answered with 1 for "yes" and 0 for "no".

The symbol ≡ is Match. It reports whether whatever is on its left matches whatever is on its right. For example, `'You' ≡ 'You'` gives `1`. However, `'I' 'Like' 'You' ≡ 'I' 'Love' 'You'` gives `0`, because we don’t look at each word separately, only at the whole list of texts.

Remembering ¨ from problem 5, you can see that `'I' 'Like' 'You' ≡¨ 'I' 'Love' 'You'` gives `1 0 1`, because:

    1: yes, 'I' matches 'I'
    0: no, 'Like' does not match 'Love'
    1: yes, 'You' matches 'You'

Using Match (≡) and Reverse (⌽ from problem 5), check whether 'APL' is a palindrome (a word that stays the same when read backwards). Hint: It is not, so the answer should be 0.


## 4.7: More Palindromes

You can create your own function by putting an expression (for example, ⍳10) in curly brackets (for example, `{⍳10}`). Within the inner expression (in our example, ⍳10), ⍵ (the Greek letter omega) stands for the argument to the right of the closing curly bracket ( } ). (Omega is the right-most letter of the Greek alphabet.)

For example, a function that multiplies its argument by two could be written `{2×⍵}`, so `{2×⍵}5` gives `10`.

Remember from problem 4 that the right argument of each function is the result of all the code to its right. This means that a function that subtracts one from its argument and then multiplies it by two, could be written {2×⍵-1}.

Using what you learnt in problem 6, write a function that checks whether its argument is a palindrome (a word that stays the same when read backwards). For example:

        {answer} 'racecar'
    1

        {answer} 'medium'
    0

        {answer} 'civic'
    1


## 4.8: Turning up the Heat

In problem 7, you saw how to write a function that takes a right argument using ⍵. If you want to create a function that also takes a left argument, use ⍺ (alpha; the left-most letter of the Greek alphabet). For example, a function that sums its left and right arguments and then multiplies by two could be written `{2×⍺+⍵}`.

In problem 5, you saw how we can create lists simply by putting elements next to each other. This also works for argument names that are separated by spaces:

        {⍵ ⍵ ⍵} 4
    4 4 4

        {⍵ ⍵ ⍵} 'd'
    ddd

We call this Stranding, like a strand of thread.

Another way to join things is by using , (Catenate but usually just said aloud as Comma). For example, `2 , 3` gives `2 3`. This is a normal function, so it follows the rules you learnt in problem 4. Catenate and Stranding behave differently when at least one element is a list. In such a case, Catenate joins the two arguments into a single list:

        'Hot' , 'Dog'
    HotDog

In contrast, stranding of two things always creates a two-element list:

        'Hot' 'Dog'
    ┌───┬───┐
    │Hot│Dog│
    └───┴───┘

Write a function using Stranding, Reshape (⍴ from problem 4), and Catenate (,) that takes a letter as its left argument and a size as its right argument, then produces a square table of the given size. The table should be made entirely of plus symbols (+), replaced by the given letter marking the diagonal from the top left to the bottom right:

        'o' {answer} 3
    o++
    +o+
    ++o

        'Q' {answer} 4
    Q+++
    +Q++
    ++Q+
    +++Q


## 4.9: Babushka

In problem 7 and problem 8, you saw that you could write your own function using APL symbols. You can also write functions that contain other functions that you have written. For example, a function that, given a letter, reshapes it into 3 copies, and then reshapes each copy into a 2-by-4 table, could be written like this:

        { {2 4⍴⍵}¨ 3⍴⍵} 'a'
    ┌────┬────┬────┐
    │aaaa│aaaa│aaaa│
    │aaaa│aaaa│aaaa│
    └────┴────┴────┘

In problem 5, you saw how the Each (¨) operator can be used with functions that take a single argument (which is then on the right). It can also be used with a function that takes both a right argument and a left argument. In this case, it pairs up elements from the left with elements from the right:

        1 2 3 ⍴¨ 'abc'
    ┌─┬──┬───┐
    │a│bb│ccc│
    └─┴──┴───┘

Using the way of selection you learnt in problem 3, write a function that takes a list of numbers on the left and a list of words on the right. It must then use the first number on the left to select a letter from the first word on the right, use the second number to select a letter from the second word, and so on:

        3 2 1 {answer} 'here' 'be' 'dragons'
    red

        3 3 1 5 {answer} 'just' 'eat' 'apple' 'today'
    stay


## 4.10: X Marks the Spot

Using everything that you’ve learnt so far, write a function that takes a size as right argument and draws a large X of that size. Use backslash symbols (\) and slash symbols (/) for the diagonals:

        {answer} 4
    \  /
     \/ 
     /\ 
    /  \

When your function is given an odd number as argument, then the diagonals meet in a single letter. Put an X there:

        {answer} 5
    \   /
     \ / 
      X  
     / \ 
    /   \


