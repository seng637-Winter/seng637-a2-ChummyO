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
The test range of -50.0 to 60,0 will be used for most test cases. Depending on the test case, additional test ranges were created for more specific test case scenarios.

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


#### **Table 3.** Range.expandToInclude() Test Cases
| Test Case Name                   | Input Value Partitions                                | Expected Value                  | Actual Value            | Outcome |
|----------------------------------|-------------------------------------------------------|:-------------------------------:|:-----------------------:|:-------:|
| expandToIncludeBelowLowerBound() | Input range:(-50.00001,60.0); Input value: -50.00001  | (-50.00001, 60.0)               | (-50.0,-50.0)           | Fail    |
| expandToIncludeLowerBound()      | Input range:(-50.0,60.0); Input value: -50.0          | (-50.0,60.0)                    | IllegalArgumentException | Fail    |
| expandToIncludeAboveLowerBound() | Input range:(-50.0,60.0); Input value: -49.99999      | (-50.0,60.0)                    | (-50.0,60.0)            | Pass    |
| expandToIncludeNominalValue()    | Input Range:(-50.0,60.0); Input value: 20.0           | (-50.0,60.0)                    | (-50.0,60.0)            | Pass    |
| expandToIncludeBelowUpperBound() | Input Range:(-50.0,60.0); Input value: 59.99999       | (-50.0,60.0)                    | (-50.0,60.0)            | Pass    |
| expandToIncludeUpperBound()      | Input Range:(-50.0,60.0); Input value: 60.0           | (-50.0,60.0)                    | (-50.0,60.0)            | Pass    |
| expandToIncludeAboveUpperBound() | Input Range:(-50.0,60.0); Input value: 60.00001       | (-50.0,60.00001)                | (-50.0,60.00001)        | Pass    |
| expandToIncludeMaxValue()        | Input Range:(-50.0,60.0); Input value: Double.MAX_VALUE | (-50.0,Double.MAX_VALUE)      | (-50.0,Double.MAX_VALUE) | Pass    |
| expandToIncludeMinValue()        | Input Range:(-50.0,60.0); Input value: Double.MIN_VALUE | (-50.0,Double.MIN_VALUE)      | (-50.0,Double.MIN_VALUE) | Pass    |
| expandToIncludeNullRange()       | Input Range: (15.0,15.0); Input value: null           | (15.0,15.0)                     | (15.0,15.0)             | Pass    |


#### **Table 4.** Range.contains() Test Cases
| Test Case Name                                    | Input Value Partitions                                | Expected Value                  | Actual Value            | Outcome |
|---------------------------------------------------|-------------------------------------------------------|:-------------------------------:|:-----------------------:|:-------:|
| containsValueJustBelowLowerBound()                | exampleRange: (-50.0,60.0); Value: -50.00001          | False                           | False                   | Pass    |
| containsLowerBound()                              | exampleRange: (-50.0,60.0); Value: -50.0              | True                            | True                    | Pass    |
| containsValueJustAboveLowerBound()                | exampleRange: (-50.0,60.0); Value: -49.99999          | True                            | True                    | Pass    |
| containsNominalValue()                            | exampleRange: (-50.0,60.0); Value: 50                  | True                            | True                    | Pass    |
| containsValueJustBelowUpperBound()                | exampleRange: (-50.0,60.0); Value: 99.99999            | True                            | True                    | Pass    |
| containsUpperBound()                              | exampleRange: (-50.0,60.0); Value: 100                  | True                            | True                    | Pass    |
| containsValueJustAboveUpperBound()                | exampleRange: (-50.0,60.0); Value: 100.00001           | False                           | False                   | Pass    |
| containsNotANumber()                              | exampleRange: (-50.0,60.0); Value: NaN                 | False                           | False                   | Pass    |
| containsACharacter()                              | exampleRange: (-50.0,60.0); Value: ‘n’                 | False                           | False                   | Pass    |
| containsValueInRangeWithNegativeBoundaries()      | exampleRange: (-10, -5); Value: -7                    | True                            | True                    | Pass    |
| containsValueEqualToBothLowerAndUpperBoundaries() | exampleRange: (-5, 5); Value: 5                       | True                            | True                    | Pass    |


#### **Table 5.** Range.constrain() Test Cases
| Test Case Name                   | Input Value Partitions                                | Expected Value                  | Actual Value            | Outcome |
|----------------------------------|-------------------------------------------------------|:-------------------------------:|:-----------------------:|:-------:|
| constrain_Should_Be_Max()        |exampleRange: (-100, 100); Value: 11 | 100 | 100 | Pass |
| constrain_Should_Be_Input() | exampleRange: (-100, 100); Value: 1.4 | -1.4 | -1.4 | Pass |
| constrain_Should_Be_Min() | exampleRange: (-100, 100); Value: -100.00001 | -100 | 0 | Fail |
| constrain_Should_Be_Value() | exampleRange: (-100, 100); Value: ‘a’ | ‘a’ | ‘a’ | Pass |


#### **Table 6.** Range.intersects() Test Cases
| Test Case Name                   | Input Value Partitions                                | Expected Value                  | Actual Value            | Outcome |
|----------------------------------|-------------------------------------------------------|:-------------------------------:|:-----------------------:|:-------:|
| intersectsWithBLBAndLB() | exampleRange: (-100, 100); value:  -100.00001, -100.0 | True | True | Pass|
| intersectsWithBLBAndALB() | exampleRange: (-100, 100); value:  -100.00001, -99.99999 | True | True | Pass |
| intersectsWithBLBAndAUB() | exampleRange: (-100, 100); value:  -100.00001, 100.00001 | True | True | Pass |
| intersectsWithLBAndALB() | exampleRange: (-100, 100); value:  -100.0, -99.99999 | True | True | Pass |
| intersectsWithLBAndUB() | exampleRange: (-100, 100); value:  -100.0, 100.0 | True | True | Pass |
| intersectsWithNormalAndNormal() | exampleRange: (-100, 100); value:  -99, 99 | True | True | Pass |
| intersectsWithBUBAndUB() | exampleRange: (-100, 100); value:  99.99999, 100.0 | True | False | Fail |
| intersectsWithBUBAndAUB() | exampleRange: (-100, 100); value:  99.99999, 100.00001 | True | False | Fail |
| intersectsWithUBAndAUB() | exampleRange: (-100, 100); value:  100.0, 100.00001 | True | False | Fail |
| intersectsWithInputAUBAndMAX() | exampleRange: (-100, 100); value:  100.00001, Double.MAX_VALUE | False | False | Pass |
| intersectsWithInputBLBAndMIN() | exampleRange: (-100, 100); value:  -999.00, -100.00001 | False | True | Fail |
| intersectsWithInputNaNAnd1() | exampleRange: (-100, 100);value:  Double.NaN, 1 | False | False | Pass |


#### **Table 7.** Range.shift() Test Cases
| Test Case Name                   | Input Value Partitions                                | Expected Value                  | Actual Value            | Outcome |
|----------------------------------|-------------------------------------------------------|:-------------------------------:|:-----------------------:|:-------:|
| positiveShiftRangeRight() | exampleRange: (-100, 100); delta: 50.0 | (-50,150) | (-50,150) | Pass |
| negativeShiftRangeLeft() | exampleRange: (-100, 100); delta: -75.0 | (-175, 25) | (-175, 25) | Pass |
| zeroDeltaNoShiftRange() | exampleRange: (-100, 100); delta: 0.0 | (-100,100) | (-100,100) | Pass |
| positiveShiftLbZeroCrossing()| exampleRange: (-100, 100); delta: 100.00001 | (0.0, 200.00001) | (0.0,0.0) | Fail |
| positiveShiftLbAndUbZeroCrossing() | exampleRange: (-100, -50); delta: 100.00001 | (0.0, 0.0) | (1.0000000003174137E-5, 1.0000000003174137E-5) | Fail |
| negativeShiftUbZeroCrossing() | exampleRange: (100, 150); delta: -100.00001 | (0.0, 49.99999) | [-1.0000000003174137E-5, -1.0000000003174137E-5] | Fail |
| negativeShiftLbAndUbZeroCrossing() | exampleRange: (50, 100); delta: -100.00001 | (50, 100) | [-1.0000000003174137E-5, -1.0000000003174137E-5] | Fail |
| nullBaseInvalidParameterException() | exampleRange: (50, 100); delta: -100.00001 | InvalidParameterException | NullPointerException | Fail |

# 4 How the team work/effort was divided and managed

Text…

# 5 Difficulties encountered, challenges overcome, and lessons learned

Text…

# 6 Comments/feedback on the lab itself

Text…
