# General Testing Guide for Web Site

Index
* [Scenario](#scenario)
* [User](#user)
* [Device](#device)
* [EcoSystem](#ecosystem)

---

## Scenario

### Fundation Features

### Functional Testing
* Spec-based Functional Testing
 * RAT: release acceptance test
 * FAST: functioan acceptance test
 * FET: force error test
* Requirement-based Feature Testing
* Risk-based Testing
 * FMEA (Failure Mode & Effect Analysis)
   * Risk Priority Number (RPN)
     * Severity
     * Probability
     * Detection

### Non-Functional Testing

#### Security Testing
* content security
 * each out-going hyperlink should be evaluated by backend service in advance
* safety net or canary monitor
* anti-abuse
* reverse-engineering prevention
* data integrity
* secure data transfering/storing

#### Usability Testing
* best practice
* patterns for mobile navigation
* mobile friendly test
* tolerance of user error

#### Battery Uage Testing
* Battery Consumption

#### Stress Testing
tba

#### Performance Testing (cpu / memory / latency)
* baseline
* scenario-based

#### Stress Testing
tba

#### Maintenance / Sustainability Testing
* log file rotation
* user feedback channel

---

## User

### Personal Characterics
* gender/age (i.e. 18+)
* economy ability (i.e. how much spend on membership/products)
* education/language/culture/geographical background
* inertia of user experience (i.e. face-to-face, agent, etc.)
* preferrence/bendwidth of networking (i.e. 4G/3G/WiFi)
* browswer perference

---

## Device

### High-End
* PC / Web Browswer
* Java / JavaScript / Flash
* Ram >= 2 GB
* Display 1920*1080

### Middle
* Pad
* no Flash
* Ram <= 1 GB
* Display 1280 * 720

### Low-End
* device > 1 year
* CPU 1 core
* Ram <= 512 MB
* Storage <= 8 GB

### Browswer / OS Variation

* economy: cost per each test run, SLA
* variation: OS, screen-size and browswer types
* monitoring mechanism
* integration: CI/CD
* networking: region, VPN

---

## EcoSystem

* Windows/Linux/Mac/Android/iOS
* Browswer
* Payment System
* I18N
* L10N

---
