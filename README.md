# Python Workflow

[![Workflow Quality](https://github.com/brobeson/PythonWorkflow/actions/workflows/workflow_quality.yaml/badge.svg)](https://github.com/brobeson/PythonWorkflow/actions/workflows/workflow_quality.yaml)
[![GitHub Release](https://img.shields.io/github/v/release/brobeson/PythonWorkflow?sort=semver&logo=github&label=Release)](https://github.com/brobeson/PythonWorkflow/releases/latest)

This is a reusable workflow to ensure quality Python code.
For general help with reusable workflows, read [GitHub's _Reusing workflows_ documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

## Getting Started

To use this workflow, just set it in the `uses` key of a job in your project's workflow file.
Here is an example workflow snippet that calls this workflow:

```yaml
jobs:
  dotFiles:
    name: Python
    uses: brobeson/PythonWorkflow/.github/workflows/python.yaml@v1
```

## Steps

The workflow has two jobs: Static Analysis and Test.

### Static Analysis

The Static Analysis job runs the steps described in the following sections.

1. **Format Check**
   The job runs [Black](https://black.readthedocs.io/en/stable/index.html) on all Python files in the repository.
   Use a [configuration file](https://black.readthedocs.io/en/stable/usage_and_configuration/the_basics.html#configuration-via-a-file) in your repository to control how Black formats your code.
   The job reports mis-formatted files; it does not modify any files.
1. **PyLint**  
   The job runs [PyLint](https://pylint.pycqa.org/en/latest/index.html) on all Python files in the repository.
   Use a [configuration file](https://pylint.pycqa.org/en/latest/user_guide/usage/run.html#command-line-options) in your repository to control PyLint runs.
1. **MyPy**  
   The job runs [MyPy](https://mypy.readthedocs.io/en/stable/index.html) on all Python files in the repository.
   Use a [configuration file](https://mypy.readthedocs.io/en/stable/config_file.html) in your repository to control MyPy runs.
1. **isort**  
   The job runs [isort](https://pycqa.github.io/isort/index.html) on all Python files in the repository.
   Use a [configuration file](https://pycqa.github.io/isort/docs/configuration/config_files.html) in your repository to control isort runs.

### Test

The Test job runs tests on multiple platforms, with multiple versions of Python.

1. **Run Tests**  
   The job runs [pytest](https://docs.pytest.org/en/stable/index.html).
   This step assumes your tests follow default pytest conventions, or you [configured pytest](https://docs.pytest.org/en/stable/reference/customize.html) in your repository.
1. **Report Test Coverage**  
   After running tests, the job uploads coverage data to [Coveralls](https://coveralls.io).
   It uploads a separate report for each cell in the test matrix (OS / Python combination).

## Issue Tracking

[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/bug?logo=github&label=Bugs)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aissue+is%3Aopen+label%3Abug)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/enhancement?logo=github&label=Enhancements)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/new%20step?logo=github&label=New%20Steps)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aopen+is%3Aissue+label%3A%22new+step%22)
[![GitHub milestone details](https://img.shields.io/github/milestones/progress/brobeson/PythonWorkflow/1?logo=github)](https://github.com/brobeson/PythonWorkflow/milestone/1)

[Report a bug](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=bug&projects=&template=bug.yaml) |
[Request a new step](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=new+step&projects=&template=new_step.yaml) |
[Update an existing step](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=enhancement&projects=&template=enhancement.yaml)
