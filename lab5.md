# Lab Report 5
## Debugging Scenario

# List Test not compiling properly
**Which syllabus section, announcement, or other course material has the policy that has to do with your question? Say "can't find it" if you can't find it.**

can't find it

**Put your question here:**

I fixed what we needed to for lab7 code but I keep getting error I think it might be my while loop.

![Image](http://url/a.png)

Victor Gomez

Hi, it seems you have two bugs in your code, line 41 has the while loop continue while index2 is less then index 2 which means that the while loop will never work. You also forgot to add `*.java` when compiling your code. So to compile your code use this instead `javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java`


