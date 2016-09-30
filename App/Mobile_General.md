# General Testing Guide for Mobile App

*History:
 *Vash Hsu, 2016/09/30

Index
* [App](#app)
* [User](#user)
* [Device](#device)
* [EcoSystem](#ecosystem)

---

## App
### Fundation Features
* Installation
* Uninstallation
* Update
 * Android update (i.e. adb install -r OO.apk)
 * Google App Store
 * App Internal Update process
* Upgrade / Migrate
* Storage (internal storage or external SD card)
* Restore to Factory Setting (optioanl)
* Date/Region/Networking Awareness

### Functional Testing
* Spec-based Functional Testing
 * RAT: release acceptance test
 * FAST: functioan acceptance test
 * FET: force error test
* Requirement-based Feature Testing
 *
* Risk-based Testing
 * FMEA (Failure Mode & Effect Analysis)
   * Risk Priority Number (RPN)
     * Severity
     * Probability
     * Detection


credit: http://www.slideshare.net/shettyuc/quality-risk-management-fmea
* FMEA Matrix (Simple Version) from 320 ~ 1, totally less than 64 degrees

| Severity | Probability | Detection |
|---|---|---|
| 10 (Extreme) |  |  |
| 9 |  |  |
| 8 | 8 (Regular failures) |  |
| 7 (High) |  |  |
| 6 |  |  |
| 5 |  |  |
| 4 | 4 (Repeated failures) | 4 (Normally not detected) |
| 3 (Moderate) |  | 3 (Likely not detected) |
| 2 | 2 (Occasional failures) | 2 (Regular detected) |
| 1 (Low) | 1 (unlikely failures) | 1 (Always detected) |




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
 * fresh Installation
 * app/activity launch time
 * standby
 * full operation (i.e. full scanning on whole device storage)
 * upgrade/migration
 * uninstallation
* scenario-based
  * single App
  * App, interaction with backend server
  * App, interaction with 3rd party cloud service vendors
  * App, interaction with other Apps


#### Interrupt Testing
* Pause / Resume
* Start / Stop
* foreground / background


#### Stress Testing
tba

#### Maintenance / Sustainability Testing
* log file rotation
* user feedback channel



---

## User

### Personal Characterics
* gender/age (i.e. 18+)
* economy ability (i.e. how much spend on in-app purchase)
* education/language/culture/geographical background
* inertia of user experience (i.e. MIUI, ZenUI, hTC Sense, etc.)
* frequency of standing by for Apps/Devices/Networkings
* preferrence/bendwidth of networking (i.e. 4G/3G/WiFi)
* preferrence of smart phone vendors/devices/screen-size

tba

---

## Device

### High-Ebd
* device < 6 monthes
* latest OS
* CPU >= 4 core
* Ram >= 2 GB
* Storage >= 32 GB

### Middle
* device < 1 year
* OS released one year ago
* CPU <= 2 core
* Ram = 1 ~ 2 GB
* Storage >= 16 GB

### Low-End
* device > 1 year
* OS released before more than one year
* CPU 1 core
* Ram <= 512 MB
* Storage <= 8 GB

### Hardware Sensor
* gps/agps
* camera/touchless
* touchscreen
* microphones

* ambient light
* proximity
* acceleration
* gyroscope
* magnetic
* pressure
* temperature
* humidity


### Real Device vs. Emulator

| Type of Testing  | Real Device  | Emulator  | Pros  | Cons  |
|---|---|---|---|---|
| Functional  | O  | O+ | emulator works more economically  |  . |
| Regression  | X | O+ | backup and restore on emulator is more efficiently  | .  |
| User Experience | O+ | O |   |  . |  
| System Level | O | X |   |   . |  

### Mobile Lab, local vs. cloud

* economy: cost per each test run, SLA
* variation: devices, screen-size and OS fragmentation
* interface: management conosle, web GUI, VNC, web/reporting service interface
* monitoring mechanism
* integration: CI/CD
* networking: region, VPN
* security: device/storage/networkinng is isolated/exclusive or shared, NDA

---

## EcoSystem

* Android Native App
 * Browswer
* Google Service: gapps
* Vendor Built-in App
* I18N
* L10N

---
