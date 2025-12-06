<img src="/blog/images/Debugging.jpeg" alt="debug"> 

<h1>What is debugging?</h1>
<p>

Debugging is the process of finding and fixing the mistakes that prevent code from running the way it’s supposed to. No matter how experienced a programmer is, bugs are an unavoidable part of writing software—what matters is how effectively you track them down. When I debug code, I start by trying to reproduce the problem so I know exactly what the bug looks like. Then I read error messages, add print statements or use debugging tools to trace the program’s behavior, and isolate the exact line or logic that’s causing the issue. From there, I test possible solutions one step at a time until the code works reliably again. Debugging isn’t just about fixing errors—it’s about understanding how your program thinks so you can make it stronger and more efficient.</p>

<br>
<br>

<h1>First Code</h1>
<img src="/blog/images/codeone.jpeg" alt="first">
<p>
The purpose of the code was to take a temperature value and determine whether it should be labeled as hot, temperate, or cold. The intention was for temperatures above 100 to be hot, temperatures between 50 and 100 to be temperate, and anything below 50 to be classified as cold.

The problem I found was that the original code did not account for temperatures between 0 and 50. Because the last condition used an elif, the code only checked for temperatures below 0, leaving a gap where temperatures from 1 to 49 weren’t categorized at all. This meant the program could ignore valid inputs or produce incorrect output.

My debugging thought process started with examining each conditional statement to see which temperature ranges were covered. When I noticed the missing range, I looked at how the conditions were structured. Since the final elif was too specific, I realized that converting it into an else statement would automatically catch all remaining temperatures including those between 0 and 50.

The solution was to change the final elif to an else statement, ensuring that any temperature less than 50 is correctly determined to be cold, fixing the gap in the logic.
</p>

<br>
<br>

<h1>Second Code</h1>
<img src="/blog/images/codetwo.jpeg" alt="second">
<p>
The purpose of the code was to ask the user to enter the correct password, but only allow three attempts before the program stops. After the third incorrect attempt, the program should lock the user out.

The problem I found was that the program was actually stopping after four attempts instead of three. This meant the loop condition wasn’t aligned with the actual number of tries the user was supposed to get.

My debugging thought process started by checking how the attempt counter was being updated. I noticed that the code was adding 1 to the attempt count before the checking logic ran, which meant the program was counting from 1 instead of 0. Because of that, the original condition if attempts > 3 allowed one extra try.

To fix the bug, I changed the condition from checking whether the attempts were greater than 3 to greater than 2, because the counter had already increased before the password check. This ensured that the program stops the user after exactly three attempts, as intended.
</p>

<br>
<br>

<h1>
Third Code
</h1>
<img src="/blog/images/codethree.jpeg" alt="third">
<p>
The purpose of the code was to calculate the factorial of a number entered by the user. After performing the calculation, the program should print out both the original number and the final factorial result.

The problem I found was that the print statement was not working. Instead of displaying the output, the program produced an error. The issue was that it was trying to print numeric values directly while combining them with text in a way that Python interpreted incorrectly.

My debugging thought process started with checking the print line to see how the variables were being displayed. When I looked it, I noticed that the print statement was trying to combine strings and integers without converting them. Python cannot join them together unless everything is the same data type. That’s why the print failed.

To fix the bug, I converted both num and result to strings before printing. Once they were cast as strings, the print statement could correctly concatenate the text and the numbers, allowing the program to display the calculation without errors.</p>

<br>
<br>

<h1>Fourth Code</h1>
<img src="/blog/images/codefour.jpeg" alt="fourth">

<p>
The purpose of the code was to take the numbers from 1 to n and determine whether each number is even or odd. The program should loop through every integer in the range and correctly label it.

The problem I found was that the program was showing every number as odd, even when some of them should have been even. This meant the condition used to test evenness was incorrect.

My debugging thought process started with checking the expression that determines whether a number is even. In Python, a number is even if its remainder when divided by 2 is exactly 0. However, the original code used a condition that checked whether the remainder was less than 0, which will never be true, since a remainder from dividing by 2 can only be 0 or 1. Because the even check always failed, every number was being labeled as odd.

To fix the bug, I changed the condition so that the remainder is checked with == 0 instead of < 0. This correctly identifies even numbers, and the program now properly prints which numbers are even and which are odd.
</p>
<br>
<br>


<p>
Working through each of these debugging challenges helped me understand that fixing code isn’t just about spotting errors — it’s about learning how a program thinks. By examining the logic step-by-step, checking how conditions were written, and reviewing how variables changed throughout execution, I was able to identify exactly where things went wrong and how to correct them. Each issue, whether it involved missing ranges, incorrect comparisons, or data type mismatches, taught me to slow down and analyze the structure of the code more carefully. This experience has made me more confident in troubleshooting and has shown me the importance of testing my work as I go. Moving forward, these debugging skills will help me write cleaner, more reliable programs and approach future coding tasks with a clearer, more problem-solving mindset.
</p>