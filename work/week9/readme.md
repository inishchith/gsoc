## # Week-9 Summary

- Early last week, [@valcos](https://github.com/valeriocos) had suggested unifying the integration pull-request so that they can be reviewed and tested easily. With this we had identified some redundancy in logic and methods that were common to both (CoLic & CoCom) backend implementation which were improved during the time and an initial code review was done and we closed down [#664](https://github.com/chaoss/grimoirelab-elk/pull/664) & [#669](https://github.com/chaoss/grimoirelab-elk/pull/669).
- We had addressed [an issue](https://github.com/inishchith/grimoirelab-elk/commit/12ec7bfef50ead0d0bbe999d255a11ed5422c8b2#r34368615) with respect to the logic of study implementation which was related to having multiple items in an index with a unique `interval_months` parameter. After some discussion and analyzing different approaches, we decided to have the `interval_months` as a list of intervals (eg. [1, 3, 6] months) instead of just a single interval and added a filter on the dashboard with a default to `1 month` which can be delegated in case of multiple/overlapping items.
- Next task was to add appropriate tests for the Integration pull-request. With the reference to the existing implementation of Percival's `git` backend, added tests for both the enrichers and for their corresponding study implementations.
- The implementation of CoLic integration is based on the `Scancode CLI` analyzer, I'm currently working on categorizing it to support multiple analyzers offered by Graal (i.e Scancode & NOMOS), which will also require some minor changes to Graal module as some of the information extracted from the analyzers is restricted to only `licenses` which can be fixed by passing the `copyright` flag (issue linked below).


- **Note:**
  - We're now moving on to the 3rd iteration for improving the dashboard with regards to the changes made to the fields and additional information added.
  - [@valcos](https://github.com/valeriocos) and I had discussed rough plans for next week which will be discussed in more detail during today's meeting. The thread can be found [here](https://github.com/inishchith/gsoc/issues/16)
  - **The incremental iteration of the [CoCom](http://tiny.cc/jx098y) & [CoLic](http://tiny.cc/52098y) Dashboard can be viewed from the remote instance**


- <u>Pull request created</u>
  - [chaoss/grimoirelab-elk#672](https://github.com/chaoss/grimoirelab-elk/pull/672): [graal] Add support of Graal CoCom & CoLic Backend <br>
  - [chaoss/grimoirelab-graal#50](https://github.com/chaoss/grimoirelab-graal/pull/50): [colic] Add copyright flag for extraction of copyright information <br>

- <u>Issues opened</u>
  - [chaoss/grimoirelab-graal#49](https://github.com/chaoss/grimoirelab-graal/issues/49): [colic] Add copyright flag for extraction of copyright information <br>
