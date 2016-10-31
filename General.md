General Test Plan Guideline
---
index

* [Stackholder](#stackholder)
* [Deliverables](#deliverables)
* [Schedule](#schedule)
* [Matrics](#matrics)
* [Testing Type](#testing_type)
 * [Functional Tests](#functional_tests)
---

# Stackholder

| Who | What | When | Why | How |
|---|---|---|---|---|
| PM,<br /> JM,<br /> QM,<br /> test team,<br /> All | Test Plan <br /> Traceability Matrix <br /> Test Result <br /> Test Status Report <br />Metrics | project kickoff <br /> sprint planning <br /> sprint end <br /> up-to-date | - | wiki <br /> gantt chart |

---

# Deliverables

| What | When | Who | Why | How (Which Meterial) |
|---|---|---|---|---|
| Test Plan | project kickoff, <br /> sprint planning | PM, JM, Test Team| - | wiki page or document file |
| [Traceability Matrix](TraceabilityMatrix.md) | project kickoff, <br /> sprint planning | PM, JM, QM | - | table, tantt chart|
| Test Result | release | JM | - | - |
| Test Status Report | sprint end | QM, Test Team | - | - |
| [Metrics](#matrics) | up-to-date | All | - | - |

---

# Schedule

| task | sub-tasks | duration |
|---|---|---|
| Test Plan | to review requirement/spec <br /> initialize test estimation | - |
| Recruit/Train test resources | - | - |
| Prepare test environment | - | - |
| Deploy SUT to test environment | - | - |
| Functional Test | - | - |
| Non-Functional Test | - | - |
| Bug Fixing and Regression Test | - | - |
| User Acceptance Test | - | - |
| Final Defect Review Meeting and Candidate Build Preparation | - | - |
| Deploy SUT to staging environment | - | - |
| Performance Test | - | - |
| Super Lab, beta/livefeed traffic Test | - | - |
| Release to Production | - | - |

---

# Matrics

* credit to http://www.getzephyr.com/resources/whitepapers/qa-metrics-value-testing-metrics-within-software-development


## Project Level Matrics

| - | formula |
|---|---|
| Requirement Coverage | number of requirements covered <br /> ** / ** total number of requirements <br /> ** * ** 100 |
| Defect Distribution by Status and Phase (DD) | (total number of defects) <br /> ** / ** (function areas) <br /> ** * ** Status ** * ** Phase |
| Defect open and close rate (DOCR) | defect found before delivery <br /> ** / ** ( (defect found before delivery) + (defect found after delivery) ) <br /> ** * ** 100 |
| Execution Trends by Status and By User | ( Execution Status / Execution Rate ) <br /> ** * ** ( Functional Area / Iteration ) |  

## Department Level Matrics

| - | formula |
|---|---|
| Mean Time to Defect (MTTD) | (number of issues detected) / (total execution time) |
| Mean Time to Repair (MTR)  | (number of issues fixed) / (total coding time)|
| Defect Removal Efficiency (DRE) | (number of pre-release defects) <br />** / ** (number of total defects) <br /> ** * ** 100
| Overall Testing Trend | MTTD, MTR, DRE |
| Defect Trend | DD, DOCR, DRE |

## Company Level Metrics

| - | formula |
|---|---|
| Customer Reported Issue Percentage | total number of defects found by Customer <br /> ** / ** total number of product defects <br /> ** * ** 100  |
| Mean Time between Failure | total time of software system operation <br /> ** / ** number of critical software system failures |

---

# Assumption and Risk

## Assumption
| what | by whom | possibility to break | plan B |
|---|---|---|---|
| - | -| - | - |
| At beta stage, functionality correctness is much more important than performance | - | low | introduce more servers to share loading |
| - | -| - | - |


## Risk

| Risk | Impact/Severity | Consequence | Mitigation Plan |
|---|---|---|---|
| server down | High | service downtime might break SLA <br /> | HA practice before rescue |

## High Level FMEA

---

# Testing Type

### Functional Tests

#### Grouping by Types

* BVT
* RAT: release acceptance test
* FAST: functioan acceptance test
* FET: force error test
* TOFT: task-oriented functional test
* SMOKE Test:


#### common practice
* for a regular test run, as less test cases/steps as possible
 * i.e. 10 cases for 1 minutes is better than 100 cases for 10 minutes
* for a set of test cases, as much coverage as better
 * i.e. if test case A can cover test case B and C, then use A replace B+C.
* for a controlable input data, as smaller equivalent class as possible
 * i.e. for integer input, there are possible equivalent classes for input range  

| - | equivalent class | - |
|---|---|---|
| - | i < 0 | sometimes, negative number is used to indicate error |
| - | i == 0 | some logic use 0 as false and non-zero as true |
| - | i > 0 | the most common cases without touching integer overflow |
| - | i = MAX and then i++ | in case of overflow |
| - | i = MIN (negative) and then i-- | in case of overflow |

* clean and clear discription for test case
 * i.e. calculator for A + B = C

| IPO | Phase | Description | (optional) detail |  
|---|---|---|---|
| input | pre-condition | when both A and B are positive integer | a = 1 and b = 2 |  
| process | processing | we will get C returned after performing + | SUT return a+b |  
| output | post-condition | C should be equivalent to sum of &#124;A&#124; and &#124;B&#124; | c == 3, otherwise test failed |  

* for corner cases, FET (force-error) tests and other expensive test cases
 * (risk-based) use FMEA to force ranking test cases based on risk
 * (ROI-based) use defect density to evaluate when to stop testing
 * (coverage-based) use requirement/function/branch/condition coverage to evaluate completeness of testing


### Load Tests
* behavior of the system under a specific expected load

### Stress Tests
* upper limits of capacity within the system

### Soak Tests
* system can sustain the continuous expected load

### Spike Tests
* system can sustain a suddenly increasing load generated by a large number of traffic/transaction/users

### Isolation Tests
* previously detected system issue has been fixed by repeating a test execution that resulted in a system problem
* to verify the output of each one of those interfaces/subsystems precisely https://www.tutorialspoint.com/software_testing_dictionary/isolation_testing.htm



---

# Component of Test Case

## Product
* product name, project code, a.k.a. SUT (software under test)
* version (major, minor, build, revision)
* feature ID/topic, requirement mapping, function name
* platform: OS, browswer (the testing one and/or preferred one)

## Case
* test case ID, title, purpose, short description, type, scope of functions/requirements
* test steps, assumption (i.e. environment), expected result
* (tool assisting) creator/owner, timestamp of creation and updating

---


### Referece

##### Defect Density
* http://softwaretestingfundamentals.com/defect-density/

```
defect Density = [Number of Defects] / [Size, function points, lines of code]
```
##### Test Case
* http://www.360doc.com/content/10/0826/16/1698198_48958195.shtml
* https://dzone.com/articles/automated-performance-tests-in-jenkins-ci-environm
* https://strongqa.com/qa-portal/testing-docs-templates/test-plan
