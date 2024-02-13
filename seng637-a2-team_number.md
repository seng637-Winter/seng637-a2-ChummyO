**SENG 637 - Software Testing, Reliability, and Quality**

**Lab. Report \#2 – Requirements-Based Test Generation**

| Group \#:      |     |
| -------------- | --- |
| Chioma Ukaegbu |     |
| Taran Bains               |     |
| Balkarn Gill               |     |
| Hannah                |     |
| Satchy                |     |

# 1 Introduction

Text…

# 2 Detailed description of unit test strategy

// including the input partitions you have designed
## Range Class
The test range of -50 and 60 will be used for most test cases. Depending on the test case, additional test ranges can be created for more specific test case scenarios.

#### **Table 1.** Boundary Value Testing - Domain Table for Range Class
| Boundary Value (BVT) Notation      | Value      |
|:----------------------------------:|:----------:|
| BLB (value just below lower bound) | -50.00001 |
| LB (lower bound)                   | -50       |
| ALB (value just above lower bound) | -49.99999  |
| Nominal Value(s)                   | -49 to 59  |
| BUB (value just below upper bound) | 59.99999   |
| UB (upper bound)                   |    60     |
| AUB (value just above upper bound) | 60.00001  |

## DataUtilities Class
The test range for most DataUtilities test cases will be primarily based on the number of dimensions that the mocked Values2D matrix will have. Depending on the test case, additional test criteria can be created for more specific test case scenarios. It is important to note that it will not be possible to test a method for some boundary values (for example, a Values 2D matrix cannot have a dimension of 0 or -1).

#### **Table 2.** Boundary Value Testing - Domain Table for DataUtilities Class
| Boundary Value (BVT) Notation      | Value                                        |
|:----------------------------------:|:--------------------------------------------:|
| BLB (value just below lower bound) | -1                                           |
| LB (lower bound)                   | 0                                            |
| ALB (value just above lower bound) | 1                                            |
| Nominal Value(s)                   | Any value between(but not including) 0 And 2 |
| BUB (value just below upper bound) | 1                                            |
| UB (upper bound)                   | 2                                            |
| AUB (value just above upper bound) | 3                                            |


# 3 Test cases developed

Text…

// write down the name of the test methods and classes. Organize the based on
the source code method // they test. identify which tests cover which partitions
you have explained in the test strategy section //above

# 4 How the team work/effort was divided and managed

Text…

# 5 Difficulties encountered, challenges overcome, and lessons learned

Text…

# 6 Comments/feedback on the lab itself

Text…
