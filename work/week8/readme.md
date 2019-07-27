## # Week-8 Summary

- We had discussed the optimization approaches in the last meeting in order to tackle performance issues related to memory and execution time. This week, we spent time implementing and evaluating them and making possible refinements to the dashboard.
- With the help of the new approach (i.e `query-chunk` via study), we could completely get rid of the extra memory(`cach_dict`) by trading some extra execution time for it. After [evaluating](https://github.com/inishchith/gsoc-graal/issues/12#issuecomment-513330884) the new approach, we have decided to go ahead with it.

### # Code Complexity Dashboard

![CoCom Dashboard](http://g.recordit.co/cwNBDtvLdF.gif)

- Earlier the visualizations were bound to `repository-level` data and we had concerns related to the implementation of evolution metrics and their visualizations.
- After migrating to the new approach, we've decided to keep the visualizations segregated into different levels (file/commit-level and ones obtained via study.) which would help us enhance the quality of results shown on the dashboard.
- With the help of the study-level data, we could get the evolution metrics correct along with the line-chart corresponding to the metrics which can be delegated via the in-place Selector.

### # Code License Dashboard

![CoLic Dashboard](http://g.recordit.co/GvtS5Goz1k.gif)

- The CoLic dashboard was much cleaner and insightful which was bind to commit-level(primitive) data produced by Graal, we had planned to add evolution metrics for licensed and copyrighted files by adapting the new study-approach employed at the CoCom Enricher.

<br>

- **The incremental iteration of the [CoCom](http://tiny.cc/jx098y) & [CoLic](http://tiny.cc/52098y) Dashboard can be viewed from the remote instance**

- **In summary,** and as per the evaluation results, we had started off the process long time back with (1)Repository-Level enricher which used about 36,000 items in memory. We tried to improve this via (2)File-level + Study(cache_dict) and brought down the execution time significantly and memory usage to just 200 items. And finally, to File-Level + Study(query_chuck) which brought down the memory usage to a worst-case of `number_of_intervals` items (an interval is decided by chunking data into months, starting from the first commit) and all by trading of just 5% more execution time. 🎉

<br>

- <u>Pull request created</u>
  - [chaoss/grimoirelab-elk#664](https://github.com/chaoss/grimoirelab-elk/pull/664): [graal] Add support of Graal's CoCom Backend to ELK [File-level + Study] <br>
  - [chaoss/grimoirelab-elk#669](https://github.com/chaoss/grimoirelab-elk/pull/669): [graal] Add support of Graal's CoLic Backend to ELK [File-level + Study] <br>
  - [chaoss/grimoirelab-graal#46](https://github.com/chaoss/grimoirelab-graal/pull/46): [cloc] Fix cloc error due to mulitple word language-name <br>

- <u>Issues opened</u>
  - [chaoss/grimoirelab-graal#47](https://github.com/chaoss/grimoirelab-graal/issues/47): [cocom] Redundant log on every file-open operation <br>
  - [chaoss/grimoirelab-graal#48](https://github.com/chaoss/grimoirelab-graal/issues/48): [colic] Incorrect extraction of copyright information <br>
  - [inishchith/gsoc-graal#15](https://github.com/inishchith/gsoc-graal/issues/15): [refinements] Revamp Index and visualizations to appropriate levels <br>
