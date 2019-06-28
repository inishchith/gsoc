## # Week-5 Summary

> - For this week, we'd planned to get ready with the first iteration of the dashboard for a set of visualizations of metrics produced with the help of Graal’s CoCom backend.
> - Adding more visualizations for metrics such as the relation between LOC and CCN, LOC and functions, and others.

- I started the week by getting repository-level implementation [graal-PR#29](https://github.com/chaoss/grimoirelab-graal/pull/39) reviewed by [@valcos](https://github.com/valeriocos) and completing changes proposed such as adding commit-level information to it. (we finally got it merged yesterday 🎉)

- I had earlier done some work on data-tables to showcase attributes such as Overall CCN, LOC, and top-complex-files of a given repository, I went on to create an [issue ticket](https://github.com/inishchith/gsoc-graal/issues/11#issuecomment-505134143) in order to keep track of ideas and to conduct discussion on the same. <br> Some of the implemented widgets are shown below -

-------------------

<div align="center">
       <b>[ Pie: Top complex files for given projects ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/60321323-223dce80-999a-11e9-8d46-8e86bc0385f0.png)

-------------------

<div align="center">
       <b>[ Data Table: Relation between LOC & Comments (Derived) ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/60203111-93ca2f80-9869-11e9-9720-baacd0db84dc.png)

-------------------

<div align="center">
       <b>[ Line: Project-Wise Code Complexity per day ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/60323538-fcb3c380-999f-11e9-933d-382507be08ae.png)

-------------------

<div align="center">
       <b>[ Data Table: Project-Wise Metrics Table ]</b>
</div>

![Screenshot 2019-06-13 at 11 23 55 PM](https://user-images.githubusercontent.com/20226361/60323595-20770980-99a0-11e9-830b-265a5bb93452.png)

<br>

- **The first iteration of the CoCom Dashboard can be viewed from the remote instance : [here](http://tiny.cc/ug3x8y)**


<br>

> This week's task also included analyzing data produced by Graal's CoLic(Code License) backend, I've opened an [issue ticket](https://github.com/inishchith/gsoc-graal/issues/9) for the purpose of discussing relevant attributes to be added as fields in the enriched index of ElasticSearch and pushed some reference code on my fork of [grimoirelab-elk](https://github.com/inishchith/grimoirelab-elk/tree/gsoc-graal-2019-colic) with the help of earlier work done on CoCom enricher. The approach and further steps related to CoLic data(fields) and refinements to CoCom dashboard will be discussed in today's meeting.

- <u>Working branch</u>
  - [inishchith/grimoirelab-elk#gsoc-graal-2019-cocom](https://github.com/inishchith/grimoirelab-elk/tree/gsoc-graal-2019-cocom): Adding support of CoCom backend to ELK
  - [inishchith/grimoirelab-elk#gsoc-graal-2019-colic](https://github.com/inishchith/grimoirelab-elk/tree/gsoc-graal-2019-colic): Adding support of CoLic backend to ELK

- <u>Issues opened</u>
  - [inishchith/gsoc-graal#11](https://github.com/inishchith/gsoc-graal/issues/11): [visualization] Dashboard for CoCom backend <br><br>
