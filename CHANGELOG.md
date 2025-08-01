## v7.4.1

*05 Mar 2024*

Bug Fixes:

- Skip constraint path check ({pr}`2038`).
  Thanks {user}`honnix`
- Fix collecting deps for all extras in multiple input packages ({pr}`1981`).
  Thanks {user}`dragly`

## v7.4.0

*16 Feb 2024*

Features:

- Allow force-enabling or force-disabling colorized output ({pr}`2041`).
  Thanks {user}`aneeshusa`
- Add support for command-specific configuration sections ({pr}`1966`).
  Thanks {user}`chrysle`
- Add options for including build dependencies in compiled output ({pr}`1681`).
  Thanks {user}`apljungquist`

Bug Fixes:

- Fix for `src-files` not being used when specified in a config file ({pr}`2015`).
  Thanks {user}`csalerno-asml`
- Fix ignorance of inverted CLI options in config for `pip-sync` ({pr}`1989`).
  Thanks {user}`chrysle`
- Filter out origin ireqs for extra requirements before writing output annotations ({pr}`2011`).
  Thanks {user}`chrysle`
- Make BacktrackingResolver ignore extras when dropping existing constraints ({pr}`1984`).
  Thanks {user}`chludwig-haufe`
- Display `pyproject.toml`'s metatada parsing errors in verbose mode ({pr}`1979`).
  Thanks {user}`szobov`

Other Changes:

- Add mention of pip-compile-multi in Other useful tools README section ({pr}`1986`).
  Thanks {user}`peterdemin`

## v7.3.0

*09 Aug 2023*

Features:

- Add `--no-strip-extras` and warn about strip extras by default ({pr}`1954`).
  Thanks {user}`ryanhiebert`

Bug Fixes:

- Fix revealed default config in header if requirements in subfolder ({pr}`1904`).
  Thanks {user}`atugushev`
- Direct references show extra requirements in .txt files ({pr}`1582`).
  Thanks {user}`FlorentJeannot`

Other Changes:

- Document how to run under `pipx run` ({pr}`1951`).
  Thanks {user}`brettcannon`
- Document that the backtracking resolver is the current default ({pr}`1948`).
  Thanks {user}`jeffwidman`

## v7.2.0

*02 Aug 2023*

Features:

- Add `-c/--constraint` option to `pip-compile` ({pr}`1936`).
  Thanks {user}`atugushev`

Bug Fixes:

- Allow options in config from both `pip-compile` and `pip-sync` ({pr}`1933`).
  Thanks {user}`atugushev`
- Fix rejection of negating CLI boolean flags in config ({pr}`1913`).
  Thanks {user}`chrysle`

Other Changes:

- Add Command Line Reference section to docs ({pr}`1934`).
  Thanks {user}`atugushev`

## v7.1.0

*18 Jul 2023*

Features:

- Validate parsed config against CLI options ({pr}`1910`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix a bug where `pip-sync` would unexpectedly uninstall some packages ({pr}`1919`).
  Thanks {user}`atugushev`

## v7.0.0

*14 Jul 2023*

Backwards Incompatible Changes:

- Default to `--resolver=backtracking` ({pr}`1897`).
  Thanks {user}`atugushev`
- Drop support for Python 3.7 ({pr}`1879`).
  Thanks {user}`chrysle`

Features:

- Add support for `pip==23.2` where refactored out `DEV_PKGS` ({pr}`1906`).
  Thanks {user}`atugushev`
- Add `--no-config` option ({pr}`1896`).
  Thanks {user}`atugushev`

Bug Fixes:

- Sync direct references with hashes ({pr}`1885`).
  Thanks {user}`siddharthab`
- Fix missing `via`s when more than two input files are used ({pr}`1890`).
  Thanks {user}`lpulley`

## v6.14.0

*28 Jun 2023*

Features:

- Support config defaults using `.pip-tools.toml` or `pyproject.toml` ({pr}`1863`).
  Thanks {user}`j00bar`
- Log a warning if the user specifies `-P` and the output file is present but empty ({pr}`1822`).
  Thanks {user}`davidmreed`
- Improve warning for `pip-compile` if no `--allow-unsafe` was passed ({pr}`1867`).
  Thanks {user}`chrysle`

Other Changes:

- Correct in README `pre-commit` hook to run off `requirements.in` ({pr}`1847`).
  Thanks {user}`atugushev`
- Add pyprojects.toml example for using setuptools ({pr}`1851`).
  Thanks {user}`shatakshiiii`

## v6.13.0

*07 Apr 2023*

Features:

- Add support for self-referential extras ({pr}`1791`).
  Thanks {user}`q0w`
- Add support for `pip==23.1` where removed `FormatControl` in `WheelCache` ({pr}`1834`).
  Thanks {user}`atugushev`
- Add support for `pip==23.1` where refactored requirement options ({pr}`1832`).
  Thanks {user}`atugushev`
- Add support for `pip==23.1` where deprecated `--install-option` has been removed ({pr}`1828`).
  Thanks {user}`atugushev`

Bug Fixes:

- Pass `--cache-dir` to `--pip-args` for backtracking resolver ({pr}`1827`).
  Thanks {user}`q0w`

Other Changes:

- Update examples in README ({pr}`1835`).
  Thanks {user}`lucaswerkmeister`

## v6.12.3

*01 Mar 2023*

Bug Fixes:

- Remove extras from user-supplied constraints in backtracking resolver ({pr}`1808`).
  Thanks {user}`thomdixon`
- Fix for sync error when the ireqs being merged have no names ({pr}`1802`).
  Thanks {user}`richafrank`

## v6.12.2

*25 Dec 2022*

Bug Fixes:

- Raise error if input and output filenames are matched ({pr}`1787`).
  Thanks {user}`atugushev`
- Add `pyproject.toml` as default input file format ({pr}`1780`).
  Thanks {user}`berislavlopac`
- Fix a regression with unsafe packages for `--allow-unsafe` ({pr}`1788`).
  Thanks {user}`q0w`

## v6.12.1

*16 Dec 2022*

Bug Fixes:

- Set explicitly packages for setuptools ({pr}`1782`).
  Thanks {user}`q0w`

## v6.12.0

*13 Dec 2022*

Features:

- Add `--no-index` flag to `pip-compile` ({pr}`1745`).
  Thanks {user}`atugushev`

Bug Fixes:

- Treat `--upgrade-packages` PKGSPECs as constraints (not just minimums), consistently ({pr}`1578`).
  Thanks {user}`AndydeCleyre`
- Filter out the user provided unsafe packages ({pr}`1766`).
  Thanks {user}`q0w`
- Adopt PEP-621 for packaging ({pr}`1763`).
  Thanks {user}`ssbarnea`

## v6.11.0

*30 Nov 2022*

Features:

- Add `pyproject.toml` file ({pr}`1643`).
  Thanks {user}`otherJL0`
- Support build isolation using `setuptools/pyproject.toml` requirement files ({pr}`1727`).
  Thanks {user}`atugushev`

Bug Fixes:

- Improve punctuation/grammar with `pip-compile` header ({pr}`1547`).
  Thanks {user}`blueyed`
- Generate hashes for all available candidates ({pr}`1723`).
  Thanks {user}`neykov`

Other Changes:

- Bump click minimum version to `>= 8` ({pr}`1733`).
  Thanks {user}`atugushev`
- Bump pip minimum version to `>= 22.2` ({pr}`1729`).
  Thanks {user}`atugushev`

## v6.10.0

*13 Nov 2022*

Features:

- Deprecate `pip-compile --resolver=legacy` ({pr}`1724`).
  Thanks {user}`atugushev`
- Prompt user to use the backtracking resolver on errors ({pr}`1719`).
  Thanks {user}`maxfenv`
- Add support for Python 3.11 final ({pr}`1708`).
  Thanks {user}`hugovk`
- Add `--newline=[LF|CRLF|native|preserve]` option to `pip-compile` ({pr}`1652`).
  Thanks {user}`AndydeCleyre`

Bug Fixes:

- Fix inconsistent handling of constraints comments with backtracking resolver ({pr}`1713`).
  Thanks {user}`mkniewallner`
- Fix some encoding warnings in Python 3.10 (PEP 597) ({pr}`1614`).
  Thanks {user}`GalaxySnail`

Other Changes:

- Update pip-tools version in the README's pre-commit examples ({pr}`1701`).
  Thanks {user}`Kludex`
- Document use of the backtracking resolver ({pr}`1718`).
  Thanks {user}`maxfenv`
- Use HTTPS in a readme link ({pr}`1716`).
  Thanks {user}`Arhell`

## v6.9.0

*05 Oct 2022*

Features:

- Add `--all-extras` flag to `pip-compile` ({pr}`1630`).
  Thanks {user}`apljungquist`
- Support Exclude Package with custom unsafe packages ({pr}`1509`).
  Thanks {user}`hmc-cs-mdrissi`

Bug Fixes:

- Fix compile cached vcs packages ({pr}`1649`).
  Thanks {user}`atugushev`
- Include `py.typed` in wheel file ({pr}`1648`).
  Thanks {user}`FlorentJeannot`

Other Changes:

- Add pyproject.toml & modern packaging to introduction. ({pr}`1668`).
  Thanks {user}`hynek`

## v6.8.0

*30 Jun 2022*

Features:

- Add support for pip's 2020 dependency resolver. Use
  `pip-compile --resolver backtracking` to enable new resolver ({pr}`1539`).
  Thanks {user}`atugushev`

## v6.7.0

*27 Jun 2022*

Features:

- Support for the `importlib.metadata` metadata implementation ({pr}`1632`).
  Thanks {user}`richafrank`

Bug Fixes:

- Instantiate a new accumulator `InstallRequirement` for `combine_install_requirements`
  output ({pr}`1519`).
  Thanks {user}`richafrank`

Other Changes:

- Replace direct usage of the `pep517` module with the `build` module, for loading
  project metadata ({pr}`1629`).
  Thanks {user}`AndydeCleyre`

## v6.6.2

*23 May 2022*

Bug Fixes:

- Update `PyPIRepository::resolve_reqs()` for pip>=22.1.1 ({pr}`1624`).
  Thanks {user}`m000`

## v6.6.1

*13 May 2022*

Bug Fixes:

- Fix support for pip>=22.1 ({pr}`1618`).
  Thanks {user}`wizpig64`

## v6.6.0

*06 Apr 2022*

Features:

- Add support for pip>=22.1 ({pr}`1607`).
  Thanks {user}`atugushev`

Bug Fixes:

- Ensure `pip-compile --dry-run --quiet` still shows what would be done, while omitting
  the dry run message ({pr}`1592`).
  Thanks {user}`AndydeCleyre`
- Fix `--generate-hashes` when hashes are computed from files ({pr}`1540`).
  Thanks {user}`RazerM`

## v6.5.1

*08 Feb 2022*

Bug Fixes:

- Ensure canonicalized requirement names are used as keys, to prevent unnecessary
  reinstallations during sync ({pr}`1572`).
  Thanks {user}`AndydeCleyre`

## v6.5.0

*04 Feb 2022*

Features:

- Add support for pip>=22.0, drop support for Python 3.6 ({pr}`1567`).
  Thanks {user}`di`
- Test on Python 3.11 ({pr}`1527`).
  Thanks {user}`hugovk`

Other Changes:

- Minor doc edits ({pr}`1445`).
  Thanks {user}`ssiano`

## v6.4.0

*12 Oct 2021*

Features:

- Add support for `pip>=21.3` ({pr}`1501`).
  Thanks {user}`atugushev`
- Add support for Python 3.10 ({pr}`1497`).
  Thanks {user}`joshuadavidthomas`

Other Changes:

- Bump pip minimum version to `>= 21.2` ({pr}`1500`).
  Thanks {user}`atugushev`

## v6.3.1

*08 Oct 2021*

Bug Fixes:

- Ensure `pip-tools` unions dependencies of multiple declarations of a package with
  different extras ({pr}`1486`).
  Thanks {user}`richafrank`
- Allow comma-separated arguments for `--extra` ({pr}`1493`).
  Thanks {user}`AndydeCleyre`
- Improve clarity of help text for options supporting multiple ({pr}`1492`).
  Thanks {user}`AndydeCleyre`

## v6.3.0

*21 Sep 2021*

Features:

- Enable single-line annotations with `pip-compile --annotation-style=line` ({pr}`1477`).
  Thanks {user}`AndydeCleyre`
- Generate PEP 440 direct reference whenever possible ({pr}`1455`).
  Thanks {user}`FlorentJeannot`
- PEP 440 Direct Reference support ({pr}`1392`).
  Thanks {user}`FlorentJeannot`

Bug Fixes:

- Change log level of hash message ({pr}`1460`).
  Thanks {user}`plannigan`
- Allow passing `--no-upgrade` option ({pr}`1438`).
  Thanks {user}`ssbarnea`

## v6.2.0

*22 Jun 2021*

Features:

- Add `--emit-options/--no-emit-options` flags to `pip-compile` ({pr}`1123`).
  Thanks {user}`atugushev`
- Add `--python-executable` option for `pip-sync` ({pr}`1333`).
  Thanks {user}`MaratFM`
- Log which python version was used during compile ({pr}`828`).
  Thanks {user}`graingert`

Bug Fixes:

- Fix `pip-compile` package ordering ({pr}`1419`).
  Thanks {user}`adamsol`
- Add `--strip-extras` option to `pip-compile` for producing constraint compatible
  output ({pr}`1404`).
  Thanks {user}`ssbarnea`
- Fix `click` v7 `version_option` compatibility ({pr}`1410`).
  Thanks {user}`FuegoFro`
- Pass `package_name` explicitly in `click.version_option` decorators for compatibility
  with `click>=8.0` ({pr}`1400`).
  Thanks {user}`nicoa`

Other Changes:

- Document updating requirements with `pre-commit` hooks ({pr}`1387`).
  Thanks {user}`microcat49`
- Add `setuptools` and `wheel` dependencies to the `setup.cfg` ({pr}`889`).
  Thanks {user}`jayvdb`
- Improve instructions for new contributors ({pr}`1394`).
  Thanks {user}`FlorentJeannot`
- Better explain role of existing `requirements.txt` ({pr}`1369`).
  Thanks {user}`mikepqr`

## v6.1.0

*14 Apr 2021*

Features:

- Add support for `pyproject.toml` or `setup.cfg` as input dependency file (PEP-517) for
  `pip-compile` ({pr}`1356`).
  Thanks {user}`orsinium`
- Add `pip-compile --extra` option to specify `extras_require` dependencies ({pr}`1363`).
  Thanks {user}`orsinium`

Bug Fixes:

- Restore ability to set compile cache with env var `PIP_TOOLS_CACHE_DIR` ({pr}`1368`).
  Thanks {user}`AndydeCleyre`

## v6.0.1

*15 Mar 2021*

Bug Fixes:

- Fixed a bug with undeclared dependency on `importlib-metadata` at Python 3.6 ({pr}`1353`).
  Thanks {user}`atugushev`

Dependencies:

- Add `pep517` dependency ({pr}`1353`).
  Thanks {user}`atugushev`

## v6.0.0

*12 Mar 2021*

Backwards Incompatible Changes:

- Remove support for EOL Python 3.5 and 2.7 ({pr}`1243`).
  Thanks {user}`jdufresne`
- Remove deprecated `--index/--no-index` option from `pip-compile` ({pr}`1234`).
  Thanks {user}`jdufresne`

Features:

- Use `pep517` to parse dependencies metadata from `setup.py` ({pr}`1311`).
  Thanks {user}`astrojuanlu`

Bug Fixes:

- Fix a bug where `pip-compile` with `setup.py` would not include dependencies with
  environment markers ({pr}`1311`).
  Thanks {user}`astrojuanlu`
- Prefer `===` over `==` when generating `requirements.txt` if a dependency was pinned
  with `===` ({pr}`1323`).
  Thanks {user}`IceTDrinker`
- Fix a bug where `pip-compile` with `setup.py` in nested folder would generate
  `setup.txt` output file ({pr}`1324`).
  Thanks {user}`peymanslh`
- Write out default index when it is provided as `--extra-index-url` ({pr}`1325`).
  Thanks {user}`fahrradflucht`

Dependencies:

- Bump `pip` minimum version to `>= 20.3` ({pr}`1340`).
  Thanks {user}`atugushev`

## v5.5.0

*31 Dec 2020*

Features:

- Add Python 3.9 support ({pr}`1222`).
  Thanks {user}`jdufresne`
- Improve formatting of long "via" annotations ({pr}`1237`).
  Thanks {user}`jdufresne`
- Add `--verbose` and `--quiet` options to `pip-sync` ({pr}`1241`).
  Thanks {user}`jdufresne`
- Add `--no-allow-unsafe` option to `pip-compile` ({pr}`1265`).
  Thanks {user}`jdufresne`

Bug Fixes:

- Restore `PIP_EXISTS_ACTION` environment variable to its previous state when resolve
  dependencies in `pip-compile` ({pr}`1255`).
  Thanks {user}`jdufresne`

Dependencies:

- Remove `six` dependency in favor `pip`'s vendored `six` ({pr}`1240`).
  Thanks {user}`jdufresne`

Improved Documentation:

- Add `pip-requirements.el` (for Emacs) to useful tools to `README` ({pr}`1244`).
  Thanks {user}`jdufresne`
- Add supported Python versions to `README` ({pr}`1246`).
  Thanks {user}`jdufresne`

## v5.4.0

*21 Nov 2020*

Features:

- Add `pip>=20.3` support ({pr}`1216`).
  Thanks {user}`atugushev` and {user}`AndydeCleyre`
- Exclude `--no-reuse-hashes` option from «command to run» header ({pr}`1197`).
  Thanks {user}`graingert`

Dependencies:

- Bump `pip` minimum version to `>= 20.1` ({pr}`1191`).
  Thanks {user}`atugushev` and {user}`AndydeCleyre`

## v5.3.1

*31 Jul 2020*

Bug Fixes:

- Fix `pip-20.2` compatibility issue that caused `pip-tools` to sometime fail to
  stabilize in a constant number of rounds ({pr}`1194`).
  Thanks {user}`vphilippon`

## v5.3.0

*26 Jul 2020*

Features:

- Add `-h` alias for `--help` option to `pip-sync` and `pip-compile` ({pr}`1163`).
  Thanks {user}`jan25`
- Add `pip>=20.2` support ({pr}`1168`).
  Thanks {user}`atugushev`
- `pip-sync` now exists with code `1` on `--dry-run` ({pr}`1172`).
  Thanks {user}`francisbrito`
- `pip-compile` now doesn't resolve constraints from `-c constraints.txt`that are not
  (yet) requirements ({pr}`1175`).
  Thanks {user}`clslgrnc`
- Add `--reuse-hashes/--no-reuse-hashes` options to `pip-compile` ({pr}`1177`).
  Thanks {user}`graingert`

## v5.2.1

*09 Jun 2020*

Bug Fixes:

- Fix a bug where `pip-compile` would lose some dependencies on update a
  `requirements.txt` ({pr}`1159`).
  Thanks {user}`richafrank`

## v5.2.0

*27 May 2020*

Features:

- Show basename of URLs when `pip-compile` generates hashes in a verbose mode ({pr}`1113`).
  Thanks {user}`atugushev`
- Add `--emit-index-url/--no-emit-index-url` options to `pip-compile` ({pr}`1130`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix a bug where `pip-compile` would ignore some of package versions when
  `PIP_PREFER_BINARY` is set on ({pr}`1119`).
  Thanks {user}`atugushev`
- Fix leaked URLs with credentials in the debug output of `pip-compile`. ({pr}`1146`).
  Thanks {user}`atugushev`
- Fix a bug where URL requirements would have name collisions ({pr}`1149`).
  Thanks {user}`geokala`

Deprecations:

- Deprecate `--index/--no-index` in favor of `--emit-index-url/--no-emit-index-url`
  options in `pip-compile` ({pr}`1130`).
  Thanks {user}`atugushev`

Other Changes:

- Switch to `setuptools` declarative syntax through `setup.cfg` ({pr}`1141`).
  Thanks {user}`jdufresne`

## v5.1.2

*05 May 2020*

Bug Fixes:

- Fix grouping of editables and non-editables requirements ({pr}`1132`).
  Thanks {user}`richafrank`

## v5.1.1

*01 May 2020*

Bug Fixes:

- Fix a bug where `pip-compile` would generate hashes for `*.egg` files ({pr}`1122`).
  Thanks {user}`atugushev`

## v5.1.0

*27 Apr 2020*

Features:

- Show progress bar when downloading packages in `pip-compile` verbose mode ({pr}`949`).
  Thanks {user}`atugushev`
- `pip-compile` now gets hashes from `PyPI` JSON API (if available) which significantly
  increases the speed of hashes generation ({pr}`1109`).
  Thanks {user}`atugushev`

## v5.0.0

*16 Apr 2020*

Backwards Incompatible Changes:

- `pip-tools` now requires `pip>=20.0` (previously `8.1.x` - `20.0.x`). Windows users,
  make sure to use `python -m pip install pip-tools` to avoid issues with `pip`
  self-update from now on ({pr}`1055`).
  Thanks {user}`atugushev`
- `--build-isolation` option now set on by default for `pip-compile` ({pr}`1060`).
  Thanks {user}`hramezani`

Features:

- Exclude requirements with non-matching markers from `pip-sync` ({pr}`927`).
  Thanks {user}`AndydeCleyre`
- Add `pre-commit` hook for `pip-compile` ({pr}`976`).
  Thanks {user}`atugushev`
- `pip-compile` and `pip-sync` now pass anything provided to the new `--pip-args` option
  on to `pip` ({pr}`1080`).
  Thanks {user}`AndydeCleyre`
- `pip-compile` output headers are now more accurate when `--` is used to escape
  filenames ({pr}`1080`).
  Thanks {user}`AndydeCleyre`
- Add `pip>=20.1` support ({pr}`1088`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix a bug where editables that are both direct requirements and constraints wouldn't
  appear in `pip-compile` output ({pr}`1093`).
  Thanks {user}`richafrank`
- `pip-compile` now sorts format controls (`--no-binary/--only-binary`) to ensure
  consistent results ({pr}`1098`).
  Thanks {user}`richafrank`

Improved Documentation:

- Add cross-environment usage documentation to `README` ({pr}`651`).
  Thanks {user}`vphilippon`
- Add versions compatibility table to `README` ({pr}`1106`).
  Thanks {user}`atugushev`

## v4.5.1

*26 Feb 2020*

Bug Fixes:

- Strip line number annotations such as "(line XX)" from file requirements, to prevent
  diff noise when modifying input requirement files ({pr}`1075`).
  Thanks {user}`adamchainz`

Improved Documentation:

- Updated `README` example outputs for primary requirement annotations ({pr}`1072`).
  Thanks {user}`richafrank`

## v4.5.0

*20 Feb 2020*

Features:

- Primary requirements and VCS dependencies are now get annotated with any source `.in`
  files and reverse dependencies ({pr}`1058`).
  Thanks {user}`AndydeCleyre`

Bug Fixes:

- Always use normalized path for cache directory as it is required in newer versions of
  `pip` ({pr}`1062`).
  Thanks {user}`kammala`

Improved Documentation:

- Replace outdated link in the `README` with rationale for pinning ({pr}`1053`).
  Thanks {user}`m-aciek`

## v4.4.1

*31 Jan 2020*

Bug Fixes:

- Fix a bug where `pip-compile` would keep outdated options from `requirements.txt` ({pr}`1029`).
  Thanks {user}`atugushev`
- Fix the `No handlers could be found for logger "pip.*"` error by configuring the
  builtin logging module ({pr}`1035`).
  Thanks {user}`vphilippon`
- Fix a bug where dependencies of relevant constraints may be missing from output file ({pr}`1037`).
  Thanks {user}`jeevb`
- Upgrade the minimal version of `click` from `6.0` to `7.0` version in `setup.py` ({pr}`1039`).
  Thanks {user}`hramezani`
- Ensure that depcache considers the python implementation such that (for example)
  `cpython3.6` does not poison the results of `pypy3.6` ({pr}`1050`).
  Thanks {user}`asottile`

Improved Documentation:

- Make the `README` more imperative about installing into a project's virtual
  environment to avoid confusion ({pr}`1023`).
  Thanks {user}`tekumara`
- Add a note to the `README` about how to install requirements on different stages to
  [Workflow for layered requirements](https://pip-tools.rtfd.io/en/latest/#workflow-for-layered-requirements)
  section ({pr}`1044`).
  Thanks {user}`hramezani`

## v4.4.0

*21 Jan 2020*

Features:

- Add `--cache-dir` option to `pip-compile` ({pr}`1022`).
  Thanks {user}`richafrank`
- Add `pip>=20.0` support ({pr}`1024`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix a bug where `pip-compile --upgrade-package` would upgrade those passed packages
  not already required according to the `*.in` and `*.txt` files ({pr}`1031`).
  Thanks {user}`AndydeCleyre`

## v4.3.0

*25 Nov 2019*

Features:

- Add Python 3.8 support ({pr}`956`).
  Thanks {user}`hramezani`
- Unpin commented out unsafe packages in `requirements.txt` ({pr}`975`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix `pip-compile` doesn't copy `--trusted-host` from `requirements.in` to
  `requirements.txt` ({pr}`964`).
  Thanks {user}`atugushev`
- Add compatibility with `pip>=20.0`
  ({pr}`953` and
  {pr}`978`).
  Thanks {user}`atugushev`
- Fix a bug where the resolver wouldn't clean up the ephemeral wheel cache ({pr}`968`).
  Thanks {user}`atugushev`

Improved Documentation:

- Add a note to `README` about `requirements.txt` file, which would possibly interfere
  if you're compiling from scratch ({pr}`959`).
  Thanks {user}`hramezani`

## v4.2.0

*12 Oct 2019*

Features:

- Add `--ask` option to `pip-sync` ({pr}`913`).
  Thanks {user}`georgek`

Bug Fixes:

- Add compatibility with `pip>=19.3`
  ({pr}`864`,
  {pr}`904`,
  {pr}`910`,
  {pr}`912` and
  {pr}`915`).
  Thanks {user}`atugushev`
- Ensure `pip-compile --no-header <blank requirements.in>` creates/overwrites
  `requirements.txt` ({pr}`909`).
  Thanks {user}`AndydeCleyre`
- Fix `pip-compile --upgrade-package` removes «via» annotation ({pr}`931`).
  Thanks {user}`hramezani`

Improved Documentation:

- Add info to `README` about layered requirements files and `-c` flag ({pr}`905`).
  Thanks {user}`jamescooke`

## v4.1.0

*26 Aug 2019*

Features:

- Add `--no-emit-find-links` option to `pip-compile` ({pr}`873`).
  Thanks {user}`jacobtolar`

Bug Fixes:

- Prevent `--dry-run` log message from being printed with `--quiet` option in
  `pip-compile` ({pr}`861`).
  Thanks {user}`ddormer`
- Fix resolution of requirements from Git URLs without `-e` ({pr}`879`).
  Thanks {user}`andersk`

## v4.0.0

*25 Jul 2019*

Backwards Incompatible Changes:

- Drop support for EOL Python 3.4 ({pr}`803`).
  Thanks {user}`auvipy`

Bug Fixes:

- Fix `pip>=19.2` compatibility ({pr}`857`).
  Thanks {user}`atugushev`

## v3.9.0

*17 Jul 2019*

Features:

- Print provenance information when `pip-compile` fails ({pr}`837`).
  Thanks {user}`jakevdp`

Bug Fixes:

- Output all logging to stderr instead of stdout ({pr}`834`).
  Thanks {user}`georgek`
- Fix output file update with `--dry-run` option in `pip-compile` ({pr}`842`).
  Thanks {user}`shipmints` and
  {user}`atugushev`

## v3.8.0

*06 Jun 2019*

Features:

- Options `--upgrade` and `--upgrade-package` are no longer mutually exclusive ({pr}`831`).
  Thanks {user}`adamchainz`

Bug Fixes:

- Fix `--generate-hashes` with bare VCS URLs ({pr}`812`).
  Thanks {user}`jcushman`
- Fix issues with `UnicodeError` when installing `pip-tools` from source in some systems ({pr}`816`).
  Thanks {user}`AbdealiJK`
- Respect `--pre` option in the input file ({pr}`822`).
  Thanks {user}`atugushev`
- Option `--upgrade-package` now works even if the output file does not exist ({pr}`831`).
  Thanks {user}`adamchainz`

## v3.7.0

*09 May 2019*

Features:

- Show progressbar on generation hashes in `pip-compile` verbose mode ({pr}`743`).
  Thanks {user}`atugushev`
- Add options `--cert` and `--client-cert` to `pip-sync` ({pr}`798`).
  Thanks {user}`atugushev`
- Add support for `--find-links` in `pip-compile` output ({pr}`793`).
  Thanks {user}`estan` and {user}`atugushev`
- Normalize «command to run» in `pip-compile` headers ({pr}`800`).
  Thanks {user}`atugushev`
- Support URLs as packages ({pr}`807`).
  Thanks {user}`jcushman`, {user}`nim65s` and {user}`toejough`

Bug Fixes:

- Fix replacing password to asterisks in `pip-compile` ({pr}`808`).
  Thanks {user}`atugushev`

## v3.6.1

*24 Apr 2019*

Bug Fixes:

- Fix `pip>=19.1` compatibility ({pr}`795`).
  Thanks {user}`atugushev`

## v3.6.0

*03 Apr 2019*

Features:

- Show less output on `pip-sync` with `--quiet` option ({pr}`765`).
  Thanks {user}`atugushev`
- Support the flag `--trusted-host` in `pip-sync` ({pr}`777`).
  Thanks {user}`firebirdberlin`

## v3.5.0

*13 Mar 2019*

Features:

- Show default index url provided by `pip` ({pr}`735`).
  Thanks {user}`atugushev`
- Add an option to allow enabling/disabling build isolation ({pr}`758`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix the output file for `pip-compile` with an explicit `setup.py` as source file ({pr}`731`).
  Thanks {user}`atugushev`
- Fix order issue with generated lock file when `hashes` and `markers` are used together ({pr}`763`).
  Thanks {user}`milind-shakya-sp`

## v3.4.0

*19 Feb 2019*

Features:

- Add option `--quiet` to `pip-compile` ({pr}`720`).
  Thanks {user}`bendikro`
- Emit the original command to the `pip-compile`'s header ({pr}`733`).
  Thanks {user}`atugushev`

Bug Fixes:

- Fix `pip-sync` to use pip script depending on a python version ({pr}`737`).
  Thanks {user}`atugushev`

## v3.3.2

*26 Jan 2019*

Bug Fixes:

- Fix `pip-sync` with a temporary requirement file on Windows ({pr}`723`).
  Thanks {user}`atugushev`
- Fix `pip-sync` to prevent uninstall of stdlib and dev packages ({pr}`718`).
  Thanks {user}`atugushev`

## v3.3.1

*24 Jan 2019*

- Re-release of 3.3.0 after fixing the deployment pipeline ({issue}`716`).
  Thanks {user}`atugushev`

## v3.3.0

*23 Jan 2019*

(Unreleased - Deployment pipeline issue, see 3.3.1)

Features:

- Added support of `pip` 19.0 ({pr}`715`).
  Thanks {user}`atugushev`
- Add `--allow-unsafe` to update instructions in the generated `requirements.txt` ({pr}`708`).
  Thanks {user}`richafrank`

Bug Fixes:

- Fix `pip-sync` to check hashes ({pr}`706`).
  Thanks {user}`atugushev`

## v3.2.0

*18 Dec 2018*

Features:

- Apply version constraints specified with package upgrade option
  (`-P, --upgrade-package`) ({pr}`694`).
  Thanks {user}`richafrank`

## v3.1.0

*05 Oct 2018*

Features:

- Added support of `pip` 18.1 ({pr}`689`).
  Thanks {user}`vphilippon`

## v3.0.0

*24 Sep 2018*

Major changes:

- Update `pip-tools` for native `pip` 8, 9, 10 and 18 compatibility, un-vendoring `pip`
  to use the user-installed `pip` ({pr}`657` and {pr}`672`).
  Thanks {user}`techalchemy`, {user}`suutari`, {user}`tysonclugg` and
  {user}`vphilippon`

Features:

- Removed the dependency on the external library `first` ({pr}`676`).
  Thanks {user}`jdufresne`

## v2.0.2

*28 Apr 2018*

Bug Fixes:

- Added clearer error reporting when skipping pre-releases ({pr}`655`).
  Thanks {user}`WoLpH`

## v2.0.1

*15 Apr 2018*

Bug Fixes:

- Added missing package data from vendored pip, such as missing cacert.pem file.
  Thanks {user}`vphilippon`

## v2.0.0

*15 Apr 2018*

Major changes:

- Vendored `pip` 9.0.3 to keep compatibility for users with `pip` 10.0.0 ({pr}`644`).
  Thanks {user}`vphilippon`

Features:

- Improved the speed of `pip-compile --generate-hashes` by caching the hashes from an
  existing output file ({pr}`641`).
  Thanks {user}`justicz`
- Added a `pip-sync --user` option to restrict attention to user-local directory ({pr}`642`).
  Thanks {user}`jbergknoff-10e`
- Removed the hard dependency on setuptools ({pr}`645`).
  Thanks {user}`vphilippon`

Bug fixes:

- The pip environment markers on top-level requirements in the source file
  (requirements.in) are now properly handled and will only be processed in the right
  environment ({pr}`647`).
  Thanks {user}`JoergRittinger`

## v1.11.0

*30 Nov 2017*

Features:

- Allow editable packages in requirements.in with `pip-compile --generate-hashes` ({pr}`524`).
  Thanks {user}`jdufresne`
- Allow for CA bundles with `pip-compile --cert` ({pr}`612`).
  Thanks {user}`khwilson`
- Improved `pip-compile` duration with large locally available editable requirement by
  skipping a copy to the cache ({pr}`583`).
  Thanks {user}`costypetrisor`
- Slightly improved the `NoCandidateFound` error message on potential causes ({pr}`614`).
  Thanks {user}`vphilippon`

Bug Fixes:

- Add `-markerlib` to the list of `PACKAGES_TO_IGNORE` of `pip-sync` ({pr}`613`).

## v1.10.2

*22 Nov 2017*

Bug Fixes:

- Fixed bug causing dependencies from invalid wheels for the current platform to be
  included ({pr}`571`).
- `pip-sync` will respect environment markers in the `requirements.txt` ({pr}`600`).
  Thanks {user}`hazmat345`
- Converted the ReadMe to have a nice description rendering on PyPI.
  Thanks {user}`bittner`

## v1.10.1

*27 Sep 2017*

Bug Fixes:

- Fixed bug breaking `pip-sync` on Python 3, raising
  `TypeError: '<' not supported between instances of 'InstallRequirement' and 'InstallRequirement'` ({pr}`570`).

## v1.10.0

*27 Sep 2017*

Features:

- `--generate-hashes` now generates hashes for all wheels, not only wheels for the
  currently running platform ({pr}`520`).
  Thanks {user}`jdufresne`
- Added a `-q`/`--quiet` argument to the `pip-sync` command to reduce log output.

Bug Fixes:

- Fixed bug where unsafe packages would get pinned in generated requirements files when
  `--allow-unsafe` was not set. ({pr}`517`).
  Thanks {user}`dschaller`
- Fixed bug where editable PyPI dependencies would have a `download_dir` and be exposed
  to `git-checkout-index`, (thus losing their VCS directory) and
  `python setup.py egg_info` fails. ({pr}`385`) and {pr}`538`).
  Thanks {user}`blueyed` and {user}`dfee`
- Fixed bug where some primary dependencies were annotated with "via" info comments. ({pr}`542`).
  Thanks {user}`quantus`
- Fixed bug where pkg-resources would be removed by `pip-sync` in Ubuntu. ({pr}`555`).
  Thanks {user}`cemsbr`
- Fixed bug where the resolver would sometime not stabilize on requirements specifying
  extras. ({pr}`566`).
  Thanks {user}`vphilippon`
- Fixed an unicode encoding error when distribution package contains non-ASCII file
  names ({pr}`567`).
  Thanks {user}`suutari`
- Fixed package hashing doing unnecessary unpacking ({pr}`557`).
  Thanks {user}`suutari-ai`

## v1.9.0

*12 Apr 2017*

Features:

- Added ability to read requirements from `setup.py` instead of just `requirements.in`
  ({pr}`418`).
  Thanks {user}`tysonclugg` and {user}`majuscule`
- Added a `--max-rounds` argument to the `pip-compile` command to allow for solving large
  requirement sets ({pr}`472`).
  Thanks {user}`derek-miller`.
- Exclude unsafe packages' dependencies when `--allow-unsafe` is not in use ({pr}`441`).
  Thanks {user}`jdufresne`
- Exclude irrelevant pip constraints ({pr}`471`).
  Thanks {user}`derek-miller`.
- Allow control over emitting trusted-host to the compiled requirements. ({pr}`448`).
  Thanks {user}`tonyseek`
- Allow running as a Python module ({pr}`461`).
  Thanks {user}`AndreLouisCaron`
- Preserve environment markers in generated `requirements.txt`. ({pr}`460`).
  Thanks {user}`barrywhart`

Bug Fixes:

- Fixed the `--upgrade-package` option to respect the given package list to update ({pr}`491`).
- Fixed the default output file name when the source file has no extension ({pr}`488`).
  Thanks {user}`vphilippon`
- Fixed crash on editable requirements introduced in 1.8.2.
- Fixed duplicated `--trusted-host`, `--extra-index-url` and `--index-url` in the generated
  requirements.

## v1.8.2

*28 Mar 2017*

- Regression fix: editable reqs were losing their dependencies after first round ({pr}`476`)
  Thanks {user}`mattlong`
- Remove duplicate index urls in generated `requirements.txt` ({pr}`468`)
  Thanks {user}`majuscule`

## v1.8.1

*22 Mar 2017*

- Recalculate secondary dependencies between rounds ({pr}`378`)
- Calculated dependencies could be left with wrong candidates when toplevel requirements
  happen to be also pinned in sub-dependencies ({pr}`450`)
- Fix duplicate entries that could happen in generated `requirements.txt` ({pr}`427`)
- Gracefully report invalid pip version ({pr}`457`)
- Fix capitalization in the generated `requirements.txt`, packages will always be
  lowercased ({pr}`452`)

## v1.8.0

*17 Nov 2016*

- Adds support for upgrading individual packages with a new option `--upgrade-package`.
  To upgrade a _specific_ package to the latest or a specific version use
  `--upgrade-package <pkg>`. To upgrade all packages, you can still use
  `pip-compile --upgrade`. ({pr}`409`)
- Adds support for pinning dependencies even further by including the hashes found on
  PyPI at compilation time, which will be re-checked when dependencies are installed at
  installation time. This adds protection against packages that are tampered with. ({pr}`383`)
- Improve support for extras, like `hypothesis[django]`
- Drop support for `pip < 8`

## v1.7.1

*20 Oct 2016*

- Add `--allow-unsafe` option (#377)

## v1.7.0

*06 Jul 2016*

- Add compatibility with `pip >= 8.1.2` (#374)
  Thanks {user}`jmbowman`

## v1.6.5

*11 May 2016*

- Add warning that `pip >= 8.1.2` is not supported until 1.7.x is out

## v1.6.4

*03 May 2016*

- Incorporate fix for atomic file saving behaviour on the Windows platform (see {issue}`351`)

## v1.6.3

*02 May 2016*

- PyPI won't let me upload 1.6.2

## v1.6.2

*02 May 2016*

- Respect pip configuration from `pip.{ini,conf}`
- Fixes for atomic-saving of output files on Windows (see {issue}`351`)

## v1.6.1

*06 Apr 2016*

Minor changes:

- `pip-sync` now supports being invoked from within and outside an activated virtualenv
  (see {issue}`317`)
- `pip-compile`: support `-U` as a shorthand for `--upgrade`
- `pip-compile`: support pip's `--no-binary` and `--binary-only` flags

Fixes:

- Change header format of output files to mention all input files

## v1.6

*05 Feb 2016*

Major change:

- `pip-compile` will by default try to fulfill package specs by looking at a previously
  compiled output file first, before checking PyPI. This means `pip-compile` will only
  update the `requirements.txt` when it absolutely has to. To get the old behaviour
  (picking the latest version of all packages from PyPI), use the new `--upgrade`
  option.

Minor changes:

- Bugfix where `pip-compile` would lose "via" info when on pip 8 (see {issue}`313`)
- Ensure cache dir exists (see {issue}`315`)

## v1.5

*23 Jan 2016*

- Add support for `pip >= 8`
- Drop support for `pip < 7`
- Fix bug where `pip-sync` fails to uninstall packages if you're using the `--no-index`
  (or other) flags

## v1.4.5

*20 Jan 2016*

- Add `--no-index` flag to `pip-compile` to avoid emitting `--index-url` into the output
  (useful if you have configured a different index in your global `~/.pip/pip.conf`, for
  example)
- Fix: ignore stdlib backport packages, like `argparse`, when listing which packages
  will be installed/uninstalled ({issue}`286`)
- Fix `pip-sync` failed uninstalling packages when using `--find-links` ({issue}`298`)
- Explicitly error when pip-tools is used with pip 8.0+ (for now)

## v1.4.4

*11 Jan 2016*

- Fix: unintended change in behaviour where packages installed by `pip-sync` could
  accidentally get upgraded under certain conditions, even though the `requirements.txt`
  would dictate otherwise (see {issue}`290`)

## v1.4.3

*06 Jan 2016*

- Fix: add `--index-url` and `--extra-index-url` options to `pip-sync`
- Fix: always install using `--upgrade` flag when running `pip-sync`

## v1.4.2

*13 Dec 2015*

- Fix bug where umask was ignored when writing requirement files ({issue}`268`)

## v1.4.1

*13 Dec 2015*

- Fix bug where successive invocations of `pip-sync` with editables kept
  uninstalling/installing them (fixes {issue}`270`)

## v1.4.0

*13 Dec 2015*

- Add command line option `-f` / `--find-links`
- Add command line option `--no-index`
- Add command line alias `-n` (for `--dry-run`)
- Fix a unicode issue

## v1.3.0

*08 Dec 2015*

- Support multiple requirement files to `pip-compile`
- Support requirements from stdin for `pip-compile`
- Support `--output-file` option on `pip-compile`, to redirect output to a file (or stdout)

## v1.2.0

*30 Nov 2015*

- Add CHANGELOG :)
- Support pip-sync'ing editable requirements
- Support extras properly (i.e. `package[foo]` syntax)

(Anything before 1.2.0 was not recorded.)
