## # Week-7 Summary

> - Our goal for this week was to make refinements by reiterating through the Code Complexity & Code License Dashboards
> - Along with improvements (listed in the last blog post), we also had to explore and evaluate solutions to improve the performance of Graal's integration in terms of memory management and time for execution.

<br>
<h3> <b> # Code Complexity(CoCom) Dashboard </b></h3>

<br>

![CoCom Dashboard](https://user-images.githubusercontent.com/20226361/61267854-30238a00-a7b7-11e9-924f-545e24d7be32.gif)

<br><br>

- We had started off the week with reiteration and making some necessary changes such as rearrangement of widgets, adding appropriate labels and revamping some of the visualizations (as the changes can be seen above).

> During our re-iteration time, [@valcos](https://github.com/valeriocos) had pointed out that due to no data corresponding to the common datetime, the current line-chart has problems. It should produce the sum total of the metrics on the line-chart at every point, which was incorrect in our case. As it would show the metric corresponding to the latest commit.<br>
> (We, earlier had a line-chart for each metric, lines in the line-chart would show the evolution of each repository(origin) for the corresponding metric over time, But this would cause problems in case of a large number of repositories. Hence, we had to think of other possible solutions)

- Ahead of all, we had already addressed the performance issues that repository-level data brought along with the insightful results and this was the time we had to re-think of ways to eliminate the overhead. At this point, [@valcos](https://github.com/valeriocos) had suggested me to explore the execution of a **study** over the available index which would help eliminate execution of analyzer at repository-level and hence reducing the memory overhead.

- I could produce an initial implementation of study and following is a comparison 

| <u>Repository</u>   | <u>Commits</u>&nbsp;&nbsp; | <u> File Level</u>&nbsp;&nbsp; | <u>Repository Level</u>&nbsp;&nbsp;  | <u>File-Level + Study</u>&nbsp; |
| :-------------: | :-----------: | :-------------: | :--------:| :-------------: |
| [grimoirelab-kingarthur](https://github.com/chaoss/grimoirelab-kingarthur)| 208 | 3:12 min |  34:23 min | 5:06 min |
| [grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal)   | 179 |  2:22 min  | 28:35 min | 3:58 min |

- **Space Complexity:** For instance, if we consider an item per file, the results for Graal repository would be as follows: (no. of files: ~200, no. of commits: ~180)
    - Repository Level: 36000 items (200*180)
    - File-Level + Study: 200 items
- A more detailed summary and discussion related to the above exploration can be found on the [issue thread](https://github.com/inishchith/gsoc-graal/issues/12).
- Instead of a line-chart, now we can easily implement a Bar-chart, split wrt. to repositories and in case of common data points we can have the sum total of the metrics. (created with the help of data in study index)
<br><br>

![Stacked Bar-Chart](https://lh3.googleusercontent.com/-DcGmMwVA9a4/XSn8TUWJrHI/AAAAAAAABhE/PKT5wUOxaf89DBYOeZoCRJfSS6mZHpXDwCK8BGAs/s0/Screenshot%2B2019-07-13%2Bat%2B9.13.38%2BPM.png)

<br><br>

- **The incremental iteration of the CoCom Dashboard can be viewed from the remote instance : [here](http://tiny.cc/jx098y)**

<br>

<h3> <b> # Code License(CoLic) Dashboard </b> </h3>

<br>

![CoLic Dashboard](https://user-images.githubusercontent.com/20226361/61267855-30bc2080-a7b7-11e9-897a-36c4a95f02a3.gif)

<br><br>

- We had decided to have as many insightful visualizations as possible on the dashboard and to reduce the number of data tables.

- **Refinements**
    - We earlier had separate tables for license and copyright definition per file, we've now merged it into a single table which is delegated with the help of **Selector**.
    - We've added more Pie-chart for the license and copyright information
        - All license and copyright definition.
        - Replaced number metric with Pie-Chart showing the number of licensed v/s non-licensed files, a similar one for copyrighted v/s non-copyrighted files.

- **Note:** In the last meeting we'd addressed the issue with copyright information extracted, The problem seems to be with the underlying tool([Scancode-toolkit](https://github.com/nexB/scancode-toolkit)) that we're using to extract the related information, we're planning to look into this in due time.

- Today's meeting would be very crucial in terms of defining further steps with the details that we have currently have and prioritizing work that needs to be done.

- **The incremental iteration of the CoLic Dashboard can be viewed from the remote instance : [here](http://tiny.cc/52098y)**
<br><br>


- <u>Working branch</u>
  - [inishchith/grimoirelab-elk#gsoc-graal-2019-cocom+study](https://github.com/inishchith/grimoirelab-elk/tree/gsoc-graal-2019-cocom+study): Study Enricher

- <u>Issue Thread</u>
  - [inishchith/gsoc-graal#12](https://github.com/inishchith/gsoc-graal/issues/12): [improvements] Evaluation of existing approaches and optimizations
