# Week 10 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**


### The two tests that I chose from the 652 commonmark-spec tests were 530.md and 578.md

---

To find the tests that caused different results between my implementation and the implementation provided in lab, I ran a bash for loop first for my implementation and copied the results into a `results.txt` file that would be stored in the directory holding my implementation. Then I ran a bash for loop on the implementation provided in lab and copied the results into a `results.txt` file that would be stored in the directory holding the implementatation provided in lab. Then I ran the command `diff your-markdown-parse/results.txt Markdown-Parse-Week9/results.txt` with `your-mardown-parse/` directory containing my implementation and `Markdown-Parse-Week9/` directory containing the implementation provided in lab. This command showed me which tests caused different results between the two implementations. 

## Test 530.md

While my implementation caused the wrong output, the implementation provided in the lab presented the expected output. The expected output is to provide the link `moon.jpg`:

![ExpectedOutputFor530](Week10Images/Expected530.png)

![Diff530](Week10Images/Diff530.png)

The bug in my implementation that causes the wrong output is that my code does not use the closing parenthese to advance the currentIndex variable. Instead my code using the closing bracket to advance the currentIndex variable; therefore causing the This is why the output shows multiple `![moon](moon.jpg,` after properly showing just `moon.jpg`. 

Image of the code that needs to be fixed:

![FixThis530](Week10Images/MyCodeProblem.png)


## Test 578.md

In testing 578.md, my implementation causes the wrong output while the implementation provided in lab 9 presents the expected output. The expected output is an empty list of links because there are no links in 578.md: 

![ExpectedOutputFor566](Week10Images/Expected578.png)

![Diff566](Week10Images/Diff578.png)

The bug in my implementation that causes the wrong output is that anything inside of parentheses will be copied and inserted into the ArrayList that will return the list of links. For 578.md, there is the text "title" inside of the parentheses. This text causes the link `/path/to/train.jpg` to not be considered a link by "Preview 578.md". Therefore, the implementation from lab disregards the link while my implementation believes it is a link and adds it to the list of links returned. 

The code that should be fixed:

![FixSecond578](Week10Images/FixSecond578.png)


