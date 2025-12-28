# GitHub CI Action: build-cmake-code

![Test action](https://github.com/NOAA-EMC/ci-build-cmake-code/actions/workflows/test-action.yml/badge.svg)

This repository provides a GitHub Action for checking out and building CMake
code from GitHub repositories, as well as caching the resulting code 
(currently this is only supported for repository caches through the 
[actions/cache](https://github.com/actions/cache) action). In general, NCEP
library CI workflows should not call this action directly, and should instead
use https://github.com/NOAA-EMC/ci-build-nceplibs, which will call this Action.

This repository supports [NCEPLIBS](https://github.com/NOAA-EMC/NCEPLIBS) CI
workflows.

To submit bug reports, feature requests, or other code-related issues including
usage questions, please create a [GitHub
issue](https://github.com/NOAA-EMC/ci-build-cmake-code/issues). For general
NCEPLIBS inquiries, contact [Alex Richert](mailto:alexander.richert@noaa.gov)
(secondary point of contact [Hang Lei](mailto:hang.lei@noaa.gov)).

### Authors

[Alex Richert](mailto:alexander.richert@noaa.gov)

### Usage

To use this Action, include the following step in your GitHub Actions workflow:
```
    - name: "Build 'bacio'"
      uses: NOAA-EMC/ci-build-cmake-code@develop
      with:
        package-name: NCEPLIBS-bacio
        package-org: NOAA-EMC
        cmake-args: -DBUILD_SHARED_LIBS=ON
        git-ref: v2.6.0
        repo-cache: true
```

See `action.yml` for the full list of available options and their defaults.

## Disclaimer

The United States Department of Commerce (DOC) GitHub project code is provided
on an "as is" basis and the user assumes responsibility for its use. DOC has
relinquished control of the information and no longer has responsibility to
protect the integrity, confidentiality, or availability of the information. Any
claims against the Department of Commerce stemming from the use of its GitHub
project will be governed by all applicable Federal law. Any reference to
specific commercial products, processes, or services by service mark, trademark,
manufacturer, or otherwise, does not constitute or imply their endorsement,
recommendation or favoring by the Department of Commerce. The Department of
Commerce seal and logo, or the seal and logo of a DOC bureau, shall not be used
in any manner to imply endorsement of any commercial product or activity by DOC
or the United States Government.
