## # Week-3 Summary

> Last week, we had thought to provide analysis(visualization) of changes over a period of time(configurable) for attributes such as ccn (code complexity), loc (lines of code), num_funs (number of functions), tokens (number of tokens) which are produced by Graal’s CoCom Backend. <br>
> So for this week, My task revolved around working on some reference visualization and to conduct some discussion related to the requirement in the issue thread - [inishchith/gsoc-graal#6)](https://github.com/inishchith/gsoc-graal/issues/6): [discussion] Considering relevant attributes from Graal for Visualization

- In order to provide some context, Graal's CoCom backend would provide us analysis data for each file that is affected in a commit. (shown below)
```
    analysis = [
    ...
        {
            "ccn": 19,
            "avg_ccn": 2.111111111111111,
            "avg_loc": 9.11111111111111,
            "avg_tokens": 64,
            "num_funs": 9,
            "loc": 129,
            "tokens": 786,
            "ext": "py",
            "blanks": 48,
            "comments": 63,
            "file_path": "graal/codecomplexity.py"
        }
    ...
    ]
```

At this point, We need to keep track of files(and their analysis data) that are available after each checkout commit and calculate the sum of the attributes, in order to produce some insights related to (for eg.) Total Code Complexity (and others) of the Software repository.

- Fortunately, [@valcos](https://github.com/valeriocos) had shared some reference implementation of the above idea and agreed to the fact that we had to maintained separate items in the enriched index for each file's analysis data that is available in the raw index. (We had exchanged some implementation in the course of the week in the corresponding working branch, and yesterday @valcos had made some improvements to the code wrt. to the redundancy in the insertion of items)<br><br>

- [ **BLOCKER** ] Now, the idea was a lot clear but there was still work to be done from configuring visualization in Kibana and get it working according to the discussed idea (i.e point 1). I couldn't find a way to implement the idea for (variable number of) files available after a point in time, though the latter part was easier to implement (calculating the sum total of the particular analysis attribute eg. ccn).

- In order to utilize the time, I proposed an idea of repository-level analysis in an issue thread which was basically producing repository-level analysis as an option for CoCom Backend, which would make the visualization to be carried out in Kibana in a bit easier way. (below are some comparison)
<br><br>

    | <u>Repository</u>   | <u>Number of Commits</u> |   <u> File Level</u> | <u>Repository Level</u>  |
    | :-------------: | :---------: |:-------------: | :------------:|
    | [coala/coala](https://github.com/coala/coala) | 4458 | 58.89 min | 59.92 min |
    | [grimoirelab-perceval](https://github.com/chaoss/grimoirelab-perceval)| 1387 | 24.83 min | 26.63 min |
    | [grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal)   | 169 | 1.82 min  | 1.86 min |

<br>

- I felt this would be a good-to-have option in `Graal` and as I've mentioned in the [comment](https://github.com/inishchith/gsoc-graal/issues/6#issuecomment-501297676), would make it easier to visualize the data in Kibana. Hence, I've worked on the repository level analysis and could produce the following results.

Repository: [chaoss/grimoirelab-perceval](https://github.com/chaoss/grimoirelab-perceval)

---------------------
<div align="center">
<b> [ Total Lines of Code at a given point of time ( here per month ) ] </b>
</div>

![Screenshot 2019-06-12 at 7 46 50 PM](https://user-images.githubusercontent.com/20226361/59359014-3dc69980-8d4b-11e9-880c-de1ba19a4da5.png)

 ---------------------

<div align="center">
<b> [ Total Code Complexity at a given point of time ( here per month ) ] </b>
</div>

![Screenshot 2019-06-12 at 7 48 09 PM](https://user-images.githubusercontent.com/20226361/59359015-3dc69980-8d4b-11e9-88a0-2a94a1130961.png)


<div align="center">
       <b>[ Code Complexity per week ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/59455813-9329a600-8e32-11e9-9f07-584c626478a9.png)

--------------------

<div align="center">
       <b>[ Code Complexity v/s Lines of Code per week ]</b>
</div>

![Screenshot 2019-06-13 at 11 24 35 PM](https://user-images.githubusercontent.com/20226361/59455814-9329a600-8e32-11e9-8a55-d98c70daf42f.png)


- I feel the above can be further improved after getting some more clarity and having a discussion with the mentors in today's meeting :) <br><br>

- <u>Pull request created</u>
  - [chaoss/grimoirelab-graal#37)](https://github.com/chaoss/grimoirelab-graal/pull/37): [analyzer] Fix results for deleted files for CoCom backend
  - [chaoss/grimoirelab-graal#38](https://github.com/chaoss/grimoirelab-graal/pull/38): [cocom] Add repository level analysis option for CoCom backend <br><br>

- <u>Issues opened</u>
  - [chaoss/grimoirelab-graal#35](https://github.com/chaoss/grimoirelab-graal/issues/35): [analyzer] Fix results for deleted files 
  - [chaoss/grimoirelab-graal#36](https://github.com/chaoss/grimoirelab-graal/issues/36): [cocom] Evaluating results with repository level analysis <br><br>
