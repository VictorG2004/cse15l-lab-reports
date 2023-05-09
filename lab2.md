# Lab Report 3
---
## **Part 1**

[Image](part1-pic1.png)

[Image](part1-pic2.png)
Method called: public String handleRequest(URI url)
Relevant arguments in method: The argument 
```
if(url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
```
These are important to the code because it checks if a new message is being added if not then nothing will be presented in site.
How the values change: I have a string value named str which at first is blank but then changes and adds the string that is inputted in search bar.

[Image](part1-pic3.png)

Method called: public String handleRequest(URI url)
Relevant arguments in method: The same if statement is important in this case:
```
 else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {

```
How the values change: the str now adds the new string that is inputted and in the if statement I have “\n” be added right after so that the new string can be seen in another line.
 ```
 str += parameters[1];
                    str +="\n";
                    return str;
```


## **Part 2:**

Failure inducing input:
 ```
 @Test
  public void testAverageWithoutLowest1() {
    double[] input1 = { 1.0, 1.0, 2.0, 3.0  };
    double ans = ArrayExamples.averageWithoutLowest(input1);
    assertEquals( 2.0 , ans , 0);
  }
```
Input doesn’t include failure:
```
 @Test
  public void testAverageWithoutLowest4() {
    double[] input1 = { 1, 2, 3, 4 };
    double ans = ArrayExamples.averageWithoutLowest(input1);
    assertEquals( 3.00 , ans , 0.01);
  }
```
Symptom 1st input:

[Image](part2-pic1.png)
Symptom 2nd Input:
The 2nd input worked so did not have any noticeable failures.

The bug(Before):
```
 static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
The bug(After/fixed):
```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
       sum += num;
    }
    sum -= lowest;
    return sum / (arr.length - 1);
  }

```
Part 3: 
I was able to learn how to start a new server and be able to search it up on a website. I was also able to learn new ways to test programs, especially the use of helper methods to be able to use less tester methods.

