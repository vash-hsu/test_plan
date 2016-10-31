# Project-Level Metrics

* goal: all about efficiency and effectness

#### Based on and Referred to

* http://www.getzephyr.com/resources/whitepapers/qa-metrics-value-testing-metrics-within-software-development

---

### Requirement Coverage

#### purpose
* to see the bigger picture
* to identify the opportunities for improvement
* to decrease the number of missed test cases

#### formula

* Requirements Coverage = (number of requirements covered) / (total number of requirements) ** X ** 100

#### note

* configuration coverage is not equivalent to requirement coverage; it is more like sub-set of requirement coverage.

#### example

* tba

---

### Defect Distribution by Status and Phase

#### purpose
* to identify defect hotspots

#### formula
* Defect Distribution = (total number of defects) / (function areas) ** X ** Status ** X ** Phase

| defect distribution | = | total number of defects |
|---|---|---|
| | / | function areas |
| | * | Status |
| | * | Phase |

#### note
* Status: ?
* Phase: ?

#### example

---

### Defect Open and Close Rates

#### purpose

* to evaluate the ability of tester and developers to work together to identify, address and fix software defect

#### formula

* defect open and close rate =   
(defect found before delivery) / ** ( ** (defect found before delivery) + (defect found after delivery) ** ) **  
** X ** 100

| defect open and close rate | = | defect found before delivery |
|---|---|---|
| | / | ** ( ** (defect found before delivery) <br /> + (defect found after delivery) ** ) ** |
| | * | 100 |

#### note

#### example

---

### Execution Trends by Status and By User

#### goal

* to address the relationship among
 * tests executed
 * a given member of test team
 * status of found defects
* to quantify the effectiveness of idividual team members and

#### formula

* Execution Trend = ( Execution Status / Execution Rate )  
** X**  ** ( ** Functional Area / Iteration ** ) **

| execution trend | = | execution status / execution rate |
|---|---|---|
| | * | ** ( ** functional area / iteration ** ) ** |


#### note

* It might not a good method to assess the performance unless each tester works on the same area.
* It might help to use (team) execution trends to find possible buttonneck

#### example

* tba

---
