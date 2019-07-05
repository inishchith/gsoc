## # Week-6 Summary

- We had planned to re-iterate over the CoCom Dashboard to add more visualizations related to the evolution of some of the attributes(CCN, LOC, and others), [@valcos](https://github.com/valeriocos) had suggested to work on a selector(which would work as a filter) for attributes such as `project`, `origin` and `file_path` with the help of which we could show results for selected project(s) and evolution of files.
- The good thing about the addition of `selector` was, it opened the door for other insightful visualizations such as results at [`module level`](https://github.com/chaoss/grimoirelab-elk/pull/651#issuecomment-507173657) and viewing files with a metric(say LOC) in range 100 and 500 lines, I made the necessary changes to the CoCom enricher and we could produce some good results (link to dashboard ahead)

> [@valcos](https://github.com/valeriocos) also helped me with some suggestions and improvements that could be done on the CoCom dashboard, the thread can be found [here](https://github.com/inishchith/gsoc-graal/issues/11#issuecomment-507033011) with a checklist ahead ;)<br>

<br>

- **The incremental iteration of the CoCom Dashboard can be viewed from the remote instance : [here](http://tiny.cc/jx098y)**
- **Note**: don't forget to select the time-range at top right corner :P
<br><br>

> As the CoCom enricher is on its way to becoming better over time, we had also discussed to start working on CoLic data to produce some visualizations. 

- With the experience of working with CoCom enricher, I could easily sketch a version of CoLic enricher with fields such as a list of `licenses` and `copyrights` defined under a given project just for initial exploration and quickly produce [some visualizations](https://github.com/inishchith/gsoc-graal/issues/14#issuecomment-508492516) such as:
  - **`Pie Chart:`**
     - All licenses definition across projects
     - All copyright definition across projects
  - **`Data Tables:`**
     - Files with no license definition
     - File-wise license definition
     - Files with no copyright definition
     - File-wise copyright Definition
  - **`Metric`**
     - Total number of Licensed and Non-Licensed files

> After some time of initial exploration of CoLic viz. during later this week, I could prepare the first version of [CoLic dashboard](http://tiny.cc/52098y). Though a lot of improvements to be made in coming days ;)

<br>

- Today's meeting would revolve around the improvements that could be made to the CoCom Dashboard, organization of widgets. Also as of now, we've just considered a few attributes from the CoLic backend data, we can add more fields to the enricher and produce more insightful visualizations, which need to be discussed with the mentors.

<br>

- <u>Pull request created</u>
  - [chaoss/grimoirelab-elk#650](https://github.com/chaoss/grimoirelab-elk/pull/650): [elk] Add option to fetch from selected branches<br>
  - [chaoss/grimoirelab-elk#651](https://github.com/chaoss/grimoirelab-elk/pull/651): [graal] Add support of Graal's CoCom Backend to ELK<br>
  - [chaoss/grimoirelab-elk#653](https://github.com/chaoss/grimoirelab-elk/pull/653): [graal] Add support of Graal's CoLic Backend to ELK<br>
  - [chaoss/grimoirelab-graal#40](https://github.com/chaoss/grimoirelab-graal/pull/40): [docs] Update documentation and links to requirements <br>
  - [chaoss/grimoirelab-graal#41](https://github.com/chaoss/grimoirelab-graal/pull/41): [analyzer] Fix scancode_cli results<br>

- <u>Issues opened</u>
  - [inishchith/gsoc-graal#14](https://github.com/inishchith/gsoc-graal/issues/14): [visualization] Dashboard for CoLic backend <br><br>