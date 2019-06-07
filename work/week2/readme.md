## # Week-2 Summary

> In this week, The first task involved an initial exploration of ELK & Mordred and to look/discuss an approach to integrate Graal with the toolchain; The second task involved learning the process of creation of visualizations, import, and export of Kibana dashboards using appropriate Grimoirelab components.

- For the first task, I'd thought to integrate Graal's CoCom Backend first and after it's completion, we can move ahead to support other backends as well. At the start of the week, [@valeriocos](https://github.com/valeriocos) had pushed some reference code so that I could improve on it.
- The approach was to add sections in Mordred's [config file](https://github.com/chaoss/grimoirelab-sirmordred/blob/master/utils/setup.cfg) as per convention (reference show below)

```
[cocom]
raw_index = git_cocom
enriched_index = git_cocom_enriched
latest-items = true
category = ...
```

- And, the above would require adding more connectors to `ELK` with a dependency to Graal. Each connector would be composed of [ GraalBackend, raw, enrich connector, GraalCommand ] as shown below:

```
"cocom": [CoCom, CoComOcean, CoComEnrich, CoComCommand]
```

- A working branch [inishchith/grimoirelab-elk#gsoc-graal-2019](https://github.com/inishchith/grimoirelab-elk) was created to track the progress of integrating Graal's CoCom Backend with ELK. In order to proceed, We'll have a discussion today on what attributes from the results produced by Graal are relevant and should be considered for visualization and creation of dashboards and the issue thread can be found here - [inishchith/gsoc-graal#6](https://github.com/inishchith/gsoc-graal/issues/6)

- For the second task, we had a webinar scheduled yesterday (Thursday, 6th June 2019) at 12:00 CEST or 15:00 IST, which helped me understand how the components work, how to create, export and import dashboard panels using the tools - Kibiter, Sigils & Kidash. The brief summary on the task can be found [inishchith/gsoc-graal#5](https://github.com/inishchith/gsoc-graal/issues/5)<br><br>

- <u>Pull request created</u>
  - [chaoss/grimoirelab-graal#32](https://github.com/chaoss/grimoirelab-graal/pull/32): [graal] Derive `git_path` from `uri`
  - [chaoss/grimoirelab-graal#34](https://github.com/chaoss/grimoirelab-graal/pull/34): [logger] Switch `info` logger level to `debug` <br><br>

- <u>Issues opened</u>
  - [chaoss/grimoirelab-graal#33](https://github.com/chaoss/grimoirelab-graal/issues/33): [graal] Checkout log an issue in case of large repositories
  - [inishchith/gsoc-graal#5](https://github.com/inishchith/gsoc-graal/issues/5): [visualization] Creation Import & Export of Kibana Dashboards
  - [inishchith/gsoc-graal#4](https://github.com/inishchith/gsoc-graal/issues/4): [integration] Add support of Graal to ELK & Mordred <br><br>
