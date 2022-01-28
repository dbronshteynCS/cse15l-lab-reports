# Week 4 Lab Report 
**Daniel Bronshteyn**
**PID: A16882179**

## *Three code changes made to fix a bug*


## First Code Change

**First Code Change Diff:**
![First Code Change Diff](Week4ImagesFolder/Fixbugfile1.png)

**Link to test file for *failure-inducing input*:** [https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile1.md](https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile1.md)

>*The reason that bugfile1.md was being created and deleted multiple times in the Github history was because I forgot to include in the commit's description the unexpected output from the failure-inducing input. The most recent created, and used, version of bugfile1.md contains the unexpected output in the commit's description. I did not have this problem when committing bugfile2.md and bugfile3.md. 

**Symptom of failure-inducing input:**
![Symptom1](Week4ImagesFolder/Symptombugfile1.png)

The bug in `MarkdownParse.java` was that `MarkdownParse.java` was always searching for parentheses "()" so that it could add the data inside the paratheses to the `toReturn` array. If there were no parentheses present, as in `bugfile1.md`, then the program would produce an error. This bug caused the following symptom when using the failure-inducing input of `bugfile1.md`:
```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 0, end -1, length 24
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:3751)
        at java.base/java.lang.String.substring(String.java:1907)
        at MarkdownParse.getLinks(MarkdownParse.java:18)
        at MarkdownParse.main(MarkdownParse.java:26)
```
As seen in this relationship, the failure-inducing input caused the sympton shown above due to the bug in `MarkdownParse.java`. I fixed the bug by making `MarkdownParse.java` able to continue when there are no parentheses that contain links in the input.

---

## Second Code Change

**Second Code Change Diff:**
![Second Code Change Diff](Week4ImagesFolder/Fixbugfile2.png)

**Link to test file for *failure-inducing input*:** [https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile2.md](https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile2.md)

**Symptom of failure-inducing input:**
![Symptom2](Week4ImagesFolder/Symptombugfile2.png)

The bug in `MarkdownParse.java` was that it was first searching for brackets "[]" before going to the parentheses, copying the string inside the parentheses, and adding the string to the `toReturn` array. This bug caused the following symptom when using the failure-inducing input of `bugfile2.md`:
```
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
        at java.base/java.lang.StringLatin1.newString(StringLatin1.java:769)
        at java.base/java.lang.String.substring(String.java:1912)
        at MarkdownParse.getLinks(MarkdownParse.java:19)
        at MarkdownParse.main(MarkdownParse.java:31)
```
In this relationship, the failure-inducing input of `bugfile2.md` caused the symptom shown above due to the bug in `MarkdownParse.java`. I fixed the bug by making it so that `MarkdownParse.java` can read a file when parentheses holding the links are provided before the brackets. 

---

## Third Code Change

**Third Code Change Diff:**
![Third Code Change Diff](Week4ImagesFolder/Fixbugfile3.png)

**Link to test file for *failure-inducing input*:** [https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile3.md](https://github.com/dbronshteynCS/markdown-parse/blob/main/bugfile3.md)

**Symptom of failure-inducing input:**
![Symptom3](Week4ImagesFolder/Symptombugfile3.png)

The bug in `MarkdownParse.java` was that it was adding anything that came before a closing parenthese ")", when there was no opening parenthese before, to the `toReturn` array. This bug caused the follwing symptom when using the failure-inducing input of `bugfile3.md`:
```
[[ ]
```
In this relationship, the failure-inducing input of `bugfile3.md` caused the symptom shown above due to the bug in `MarkdownParse.java`. I fixed the bug by making it so that `MarkdownParse.java` made sure that when an input had a closing bracket, there was an opening bracket as well. Additionally, when an input had an opening parenthese, there would also have to be a closing parenthese. This ensured that a link had to be between two parentheses to be added to the `toReturn` array. 

