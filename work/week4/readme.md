## # Week-4 Summary

> Last week, we had addressed the issue with then [implementation](https://github.com/chaoss/grimoirelab-graal/pull/38) of repository-level analysis that it wouldn't persist the file-level information and had discussed a new enrich index structure.

- Given a thought; Instead of altering the structure of enrich index, there's an alternate way to deal with the problem and would lead to implementation. I implemented a rough version of repository-level analysis this time with the help of [lizard](https://github.com/terryyin/lizard) (which is also employed for file-level analysis), as it provided extra optimization for recursively performing the operation on a given software repository. (Evaluation results below)
<br><br>

| <u>Repository</u>   | <u>Number of Commits </u>&nbsp;&nbsp;|   <u> File Level</u>&nbsp;&nbsp; | <u>Repository Level</u>  |
| :-------------: | :-----------: |:-------------: | :--------:|
| [chaoss/grimoirelab-perceval](https://github.com/chaoss/grimoirelab-perceval)| 1394 | 26:22 min |  26:56 min |
| [chaoss/grimoirelab-sirmordred](https://github.com/chaoss/grimoirelab-sirmordred) | 869 | 08:51 min | 3:51 min |
| [chaoss/grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal)   | 171 |  2:24 min  | 1:04 min |

<br>
_above results are considering only the master branch. We can observe that the divergence in execution time is dependent on the number of files in a given repository_ (for obvious reasons 😅)
<br><br>

- With the help of the above implementation, I could produce the following metrics in Kibana with minimal configuration. The approaches for producing others (including the evolution of the metrics) efficiently is yet to be discussed with mentors.

Repository: [chaoss/grimoirelab-perceval](https://github.com/chaoss/grimoirelab-perceval)

-------------------

<div align="center">
       <b>[ Total Lines of Code after latest commit ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/59657545-ac2db080-91be-11e9-9313-8f16b9235c17.png)

--------------------

<div align="center">
       <b>[ Total Code Complexity after latest commit ]</b>
</div>

![Screenshot 2019-06-13 at 11 24 35 PM](https://user-images.githubusercontent.com/20226361/59657546-ac2db080-91be-11e9-9a99-9196b91692c3.png)

---------------------

<div align="center">
<b> [ Most Complex files after latest commit ] </b>
</div>

![Screenshot 2019-06-12 at 7 48 09 PM](https://user-images.githubusercontent.com/20226361/59675831-c1690600-91e3-11e9-9c5f-0c1227cb85f3.png)


<br>

- The enrich index working branch can be found at [inishchith/grimoirelab-elk](https://github.com/inishchith/grimoirelab-elk/tree/gsoc-graal-2019-lizard-repository)
<br><br>

> This week's task also included working on **TimeLion** visualizations, but as our idea of implementing the metrics involved bucketing (an attribute) and I couldn't get a clear reference for implementation and after giving some time had to stage the work which will be addressed in today's meeting with some discussion on how to proceed with more visualizations.

- <u>Pull request created</u>
  - [chaoss/grimoirelab-graal#39](https://github.com/chaoss/grimoirelab-graal/pull/39): [cocom] Add repository level analysis via lizard <br>

- <u>Issues opened</u>
  - [chaoss/grimoirelab-elk#642](https://github.com/chaoss/grimoirelab-elk/issues/642): Add option to fetch from selected branches <br><br>
