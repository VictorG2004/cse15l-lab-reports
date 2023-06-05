# Lab Report 5
## Debugging Scenario
1).
# List Test not compiling properly
**Which syllabus section, announcement, or other course material has the policy that has to do with your question? Say "can't find it" if you can't find it.**

can't find it

**Put your question here:**

I fixed what we needed to for lab7 code but I keep getting error I think it might be my while loop.

![Image](http://url/a.png)

2.)

Victor Gomez

Hi, it seems you have two bugs in your code, line 41 has the while loop continue while index2 is less then index 2 which means that the while loop will never work. You also forgot to add `*.java` when compiling your code. So to compile your code use this instead `javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java`

3.)
![Image](http://url/a.png)

So I tried what you told me and I fixed the while loop, now instead of it only executing if index2 is less then index 2 it will run while it is less then list2.size(). I also tried `javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java` and it was finally able to compile with no error, it seems I was just missing "*". 

4.)
File and directory:
The file that had the bug was ListExamples.java, to be able to acces the file I needed to be in the directory: ` C:\Users\capti\OneDrive\Documents\GitHub\lab7`

Contents of the file before fixing the bug: 
```
# import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }

  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < index2) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    
    return result;
  }


}

```
Command line to trigger bug: 
`javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" .java`

How to fix the bug:
To fix the bug we will have to fix last while loop to 
```
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
```
We also have to fix the command line we used to trigger bug by instead using `javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java`


