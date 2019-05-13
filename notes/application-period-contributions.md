## Microtask #9

- Submit at least a PR to one of the GrimoireLab repositories to fix an issue, improve the documentation, etc.

<hr>

### # GrimoireLab Pull Requests

| No. | Pull Request: repository |  Fixes  | Description | Status |
| :---------------: | :---------------: | :---------------: | :---------------: | :---------------: |
| 1 | [#61: grimoirelab-tutorial](https://github.com/chaoss/grimoirelab-tutorial/pull/61) | - |Fix documentation typos | Merged |
| 2 | [#2: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/2) | - | Fix documentation example  |   Merged |
| 3 | [#4: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/4) | [#3](https://github.com/chaoss/grimoirelab-graal/issues/3) | Fix failing tests      |    Merged |
| 4 | [#7: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/7) | [#6](https://github.com/chaoss/grimoirelab-graal/issues/6) | Update copyright dates under license | Merged |
| 5 | [#9: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/9) | [#8](https://github.com/chaoss/grimoirelab-graal/issues/8) |  Add support for Lua & Golang via Lizard version bump | Merged |
| 6 | [#15: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/15) | - | Add flake8 analyzer to CoQua backend | Merged & Closed |
| 7 | [# 349: grimoirelab-sigils](https://github.com/chaoss/grimoirelab-sigils/pull/349) | - | [docs] Fix broken links in docs | Merged |
| 8 | [# 76: grimoirelab-tutorial](https://github.com/chaoss/grimoirelab-tutorial/pull/76) | [#75](https://github.com/chaoss/grimoirelab-tutorial/issues/75) | [graal] Add Graal to GrimoireLab Tutorial  | Merged |

<br>

<hr>

### # Description

**1. Fix documentation typos under [#61: grimoirelab-tutorial](https://github.com/chaoss/grimoirelab-tutorial/pull/61)**

**2. Fix documentation example under [#2: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/2)**

  - Fix `CoCom backend`'s parameter shown in the example and the source code's document strings.

**3. Fix failing tests: Issue [#3](https://github.com/chaoss/grimoirelab-graal/issues/3) under grimoirelab-graal**

  - Initially the tests failed due to absence of executables ( and their path ) of NOMOS and ScanCode tools which was supposed to be defined under `.travis.yml` file and accordingly updating their paths in source code. After the merge, As of now there's no issues regarding failing tests in the repository :tada:
  - Fixed documentation to add `build status` and `coverage` information..

**4. Update copyright dates under license: Issue [#6](https://github.com/chaoss/grimoirelab-graal/issues/6)**

  - Most files in Graal come with a old copyright date (e.g., # Copyright (C) 2015-2018 Bitergia ). Updated the copyright dates of every other file included in Graal accordingly.

**5. Add support for Lua & Golang [#8](https://github.com/chaoss/grimoirelab-graal/issues/8)**

  - Lizard has recently added support for GoLang ( release v1.15.3 ) & Lua ( release v1.16.1 )
  - Updated the Lizard module version, documentation strings for source code & `ALLOWED_EXTENSIONS` for CoCom backend.

**6. Add flake8 analyzer to CoQua backend [#15: grimoirelab-graal](https://github.com/chaoss/grimoirelab-graal/pull/15)**

  - Source
    - Added flake8 analyzer for CoQua backend
    - Updated CoQua backend in order to add parameter to select either pylint or flake8. Default set to pylint.
  - Tests
    - Updated CoQua backend tests
    - Added tests for Flake8 analyzer

**7. Fix broken links in docs under [# 349: grimoirelab-sigils](https://github.com/chaoss/grimoirelab-sigils/pull/349)**

**8. Add Graal to GrimoireLab Tutorial**

  - Tutorials for set of tools provided by GrimoireLab doesn't contain tutorial for usage of Graal. My task was to add tutorial on Graal usage to [this](https://github.com/chaoss/grimoirelab-tutorial) repository.

<hr>

### # [ Related ]
- I've previously worked with SCANCODE, one of the tools which Graal `CoLic` backend uses in order to extract license information.

#### # ScanCode Pull Requests

1. `Limit number of urls and emails reported in a single file #384` [Merged](https://github.com/nexB/scancode-toolkit/commits?author=inishchith)
2. `add code_of_coduct` [Merged](https://github.com/inishchith/scancode-toolkit/commits?author=inishchith)