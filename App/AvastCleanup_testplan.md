# Blackbox Testing for Mobile App

background knowhow:  
* [Mobile_General.md](Mobile_General.md)
* [AvastCleanup_walkthrough.md](AvastCleanup_walkthrough.md)

---

## 60+ Minutes Test Plan

### Requirement-based Feature Testing
* TOFT: task oriented feature testing

#### Terminology:
* FMEA (SxPxD) means Severity x Probability x Detection
 * reference: [Mobile_General.md FMEA](Mobile_General.md/#functional-testing)
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

| ID | Type | FMEA (S*P*D) | Description |
|---|---|---|---|
| RAT-001 | Auto | (3x1x1) | Each activity (window) should be accessable individually. Otherwise, hidden logic dependence migth bring troubles for troubleshotting and automation test. |
| RAT-002 | Auto | (3x1x1) | Strings shown on GUI should be managed by res:string.xml for L10N practice. |
| RAT-003 | Auto | (3x2x2) | Each out-going hyperlink should pass dead-link evaluation with networking. (static analysis) |
| RAT-004 | Auto | (3x2x1) | Each id/path belonging to advertisement or recommanded App should pass whitelisting/blacklist and revoke list checking. (backend ad server) |
| RAT-005 | Auto | (3x2x1) | Each permission option is able to turn ON/OFF at run time without breaking App (crash). (configuration and error handling test) |
| RAT-006 | Auto | (3x1x1) | Welcome page (i.e. hello to configuration) shows on first time and only once, even after update/migration. |


* FAST: functioan acceptance test

| ID | Type | FMEA (S*P*D) | Description |
|---|---|---|---|
| FAST-001 | Auto | (3x1x1) | [safe clean] After using dummy app to generate garbage data, safe clean can purge those files by one click.  |
| FAST-002 | Auto | (3x1x1) | [safe clean] After uninstallation dummy app, safe clean can purge residual files by one click.  |
| FAST-003 | Auto | (3x1x1) | [safe clean] After using Instagram / Camera360, safe clean can purge those preview thumbnail files by one click. |
| FAST-004 | Auto | (3x1x1) | [safe clean] After browsing top 10 web sites by default browswer, chrome, firefox and opera, safe clean can purge those cache files by one click. |
| FAST-005 | Auto | (3x1x1) | [safe clean] After downloading 3rd party APK files and installing complete, safe clean can purge the downloaded APK files by one click. |
| FAST-006 | Auto | (3x1x1) | [safe clean] Browsing the advertisement (google ad) shared by multiple APPs, safe clean can purge those shared cache by one click. |
| FAST-007 | Auto | (7x2x2) | [safe clean] After adding dummy app in ignore list, no matter what kinds of options configured or heuristic rule adopted, safe clean do not and will not purge files/folders belonging to dummy app. |
| FAST-008 | Auto | (3x1x1) | [memory boost] After lunching N dummy apps iteratively, memory boost will keep the latest active Apps and kill other idle ones by one click. |
| FAST-009 | Auto | (3x2x1) | [memory boost] System apps (i.e. Google Service) should be listed on whitelisting (for long-live) by default, memory boost should not purge them accidently. |
| FAST-010 | Auto | (3x2x1) | [memory boost] After ckecking the dummy apps, memory boost do purge those apps from memory by one click. |
| FAST-011 | Manual | (3x2x2) | [memory boost] After uncheckinng the famous apps, memory boost do NOT purge those apps from memory. Those pausing apps are able to resume without errors. |
| FAST-012 | Manual | (3x1x1) | [reporting] After safe clean and memory boost operations, statistic result is proposed with correct numbers and unit (B?/KB/MB/GB). |
| FAST-013 | Manual | (3x1x1) | [AD] Each uninstalled App's icon is grayed-out on "MORE-BY-AVAST". |
| FAST-014 | Manual | (3x1x1) | [AD] Clicking grayed-out App's icon on "MORE-BY-AVAST", Google Play Store will be invoked for installing target App. |
| FAST-015 | Manual | (3x2x1) | [AD] After installing recommanded App, its icon wiil be changed to highlighed on "MORE-BY-AVAST" without restarting. |
| FAST-016 | Auto | (3x1x1) | [AD] All Apps' icons will change from grayed-out to highlighted after those 6 target apps are installed by "adb install". |
| FAST-017 | Auto | (3x1x1) | [AD] All Apps' icons will change from highlighted to grayed-out after those 6 target apps are uninstalled by "adb uninstall". |
| FAST-018 | Manual | (1x1x1) | [AD] All Apps' icons will change from highlighted to grayed-out after those 6 target apps are uninstalled by "adb uninstall". |

* FET: force error test

| ID | Type | FMEA (S*P*D) | Description |
|---|---|---|---|
| FET-001 | Auto | (3x1x2) | While networking with WiFi only, AUT works smoothly without crash when WiFi is connected and broken iteratively. |
| FET-002 | Auto | (3x1x2) | While networking with Cellular only, AUT works smoothly without crash when Cellular is connected and broken iteratively. |
| FET-003 | Auto | (3x1x3) | AUT works smoothly without crash when networking change between WiFi and Cellular iteratively. |
| FET-004 | Manual | (3x1x3) | During AUT works on killing other Apps, Android OS keep stable when AUT is purged immediatly by demand. |
| FET-005 | Manual | (3x1x3) | During AUT works on purging garbage files, AUT is able to be paused/resumed/killed by demand. The Apps, which own those garbage file, can start and work smoothly without error. |


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
