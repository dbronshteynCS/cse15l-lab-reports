# Week 10 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**


### The two tests that I chose from the 652 commonmark-spec tests were 58.md and 482.md

---

To find the tests that caused different results between my implementation and the implementation provided in lab, I ran a bash for loop first for my implementation and copied the results into a `results.txt` file that would be stored in the directory holding my implementation. Then I ran a bash for lopp on the implementation provided in lab and copied the results into a `results.txt` file that would be stored in the directory holding the implementatation provided in lab. Then I ran the command `diff your-markdown-parse/results.txt Markdown-Parse-Week9/results.txt` with `your-mardown-parse/` directory being my implementation and `Markdown-Parse-Week9/` directory being the implementation provided in lab. This command showed me which tests caused different results between the two implementations. 



