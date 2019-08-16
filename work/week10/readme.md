## # Week-10 Summary

- The implementation of CoLic integration was solely based on the `Scancode CLI` analyzer, we now have support for other analyzers categories i.e scancode and nomos. NOMOS provides only license-related information whereas the ScanCode analyzers can retrieve both license & copyright related information in more verbose.
- The major highlight of last week was regression testing of the grimoirelab-elk integration of Graal's Backend. [@valcos](https://github.com/valeriocos) & I conducted various tests on the integration task, we used all the repositories (31, to be precise) in consideration and evaluated the time required for the execution of the tasks. 

- **CoCom Evaluations**:

| Organization   | Repositories | Raw Phase | Enrichment Phase | Study Phase | Results Verified | 
| :-------------: | :---------: |:-------------: | :-----:| :-----:| :-----:|
| [chaoss](https://github.com/chaoss/) | 31 | 11:53:59 hr | 00:40:35 hr | 00:36:38 hr | Yes |

- **CoLic Evaluations**:

| Organization   | Analyzer | Repositories | All Phases | Results Verified | 
| :-------------: | :---------: |:-------------: | :-----:| :-----:|
| [chaoss](https://github.com/chaoss/) | Scancode-CLI | 4 | 04:54:22 hr | Yes |
| [chaoss](https://github.com/chaoss/) | NOMOS | 4 | 00:17:01 hr  | Yes |

> More details(logs and repositories in consideration) can be found in [this thread](https://github.com/inishchith/gsoc/issues/17).

- As we're only a week away from the final evaluation, our main focus, for now, is to get ready with the project as a whole, with implementation integrated to the grimoirelab-toolset and tested on entirety. There are corresponding Pull-requests open at (elk, mordred & sigils) in order to review and test the integration.

- **Note:**
  - We're currently working on some issues such as the slow execution speed of CoLic analyzer and other minor which we encountered during the testing phase.
  - **The incremental iteration of the [CoCom](http://tiny.cc/jx098y) & [CoLic](http://tiny.cc/52098y) Dashboard can be viewed from the remote instance**


- <u>Pull request created</u>
  - [chaoss/grimoirelab-sirmordred#320](https://github.com/chaoss/grimoirelab-sirmordred/pull/320): [graal] Add configuration for Graal integration in ELK <br>
  - [chaoss/grimoirelab-sigils#380](https://github.com/chaoss/grimoirelab-sigils/pull/380): [graal] Add Code Complexity(CoCom) & Code License(CoLic) panels <br>
