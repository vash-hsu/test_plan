# Blackbox Testing for Mobile App

---

## 10+ Minutes Test Plan

### Requirement-based Feature Testing
* TOFT: task oriented feature testing

#### Terminology:
* FMEA (SxPxD) means Severity x Probability x Detection
 * reference: [Mobile_General.md FMEA](Mobile_General.md/#functional testing)
* AUT: app under test

| ID | Type | FMEA (S*P*D) | Description |
|---|---|---|---|
| TOFT-001 | Auto | (7x1x1) | User can fresh install AUT on both high-end and middle devices successfully. |
| TOFT-002 | Auto | (7x1x1) | User can activate AUT successfully. |
| TOFT-003 | Manual | (1x1x1) | User can reject to activate AUT and get suggestion by instructive guidelines. |
| TOFT-004 | Auto | (1x1x1) | User can uninstall AUT successfully. |
| TOFT-005 | Auto | (2x2x2) | User can update AUT correctly and successfully. Otherwise, statistic and user setting (i.e. ignore list) will lose and user hates to do it over-and-over again. |
| TOFT-006 | Auto | (1x2x3) | User can allow/disallow all permissions required by AUT successfully. AUT have ability to perform/skip major functions without requested permissions. |
| TOFT-007 | Auto | (10x2x2) | On dirty device, user can run Safe clean by default options successfully. |
| TOFT-008 | Auto | (10x2x2) | On heavy-loaded device, user can run Memory boost by default options successfully. |
| TOFT-009 | Manual | (7x2x2) | User can install other Avast Apps through "MORE BY AVAST". |
| TOFT-010 | Manual | (3x2x3) | User can get baseline usability even without networking. For example, there should NOT be any dead loop for pop-up window telling "out-of-networking". |

### Functional Testing
Spec-based Functional Testing
* RAT: release acceptance test
* FAST: functioan acceptance test
* FET: force error test


### Non-Functional Testing
* Security Testing
 * content security
   * each out-going hyperlink should be evaluated by backend service in advance
* Usability Testing
* Battery Uage Testing
* Stress Testing
* Performance Testing (cpu / memory / latency)  
 * Interrupt Testing
 * Stress Testing
* Maintenance / Sustainability Testing  
 * log file rotation
 * user feedback channel
