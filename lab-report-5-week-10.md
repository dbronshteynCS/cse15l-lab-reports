# Week 10 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**


### The two tests that I chose from the 652 commonmark-spec tests were 53.md and 565.md

---

To find the tests that caused different results between my implementation and the implementation provided in lab, I ran a bash for loop first for my implementation and copied the results into a `results.txt` file that would be stored in the directory holding my implementation. Then I ran a bash for lopp on the implementation provided in lab and copied the results into a `results.txt` file that would be stored in the directory holding the implementatation provided in lab. Then I ran the command `diff your-markdown-parse/results.txt Markdown-Parse-Week9/results.txt` with `your-mardown-parse/` directory being my implementation and `Markdown-Parse-Week9/` directory being the implementation provided in lab. This command showed me which tests caused different results between the two implementations. 

## Test 53.md


## Test 565.md

Both my implementation and the implementation provided in lab 9 do not present the expected output. The expected output should show the text "foo" with a link embedded: 

# Expected O

# Diff

The bug in my implementation that causes the wrong output is that the code will continue to get stuck in the while loop and keep adding anything between brackets and an opening parenthese to the ArrayList that will be returned until the condition to ensure the while loops breaks to prevent an infinite loop becomes true. 

The while loop that is causing this bug is shown below:

## Image of while loop



