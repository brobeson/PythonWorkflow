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

The workflow runs the steps described in the following sections.

1. **Format Check**
   The workflow runs [Black](https://black.readthedocs.io/en/stable/index.html) on all Python files in the repository.
   Use a [configuration file](https://black.readthedocs.io/en/stable/usage_and_configuration/the_basics.html#configuration-via-a-file) in your repository to control how Black formats your code.
   The workflow reports mis-formatted files; it does not modify any files.

## Issue Tracking

[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/bug?logo=github&label=Bugs)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aissue+is%3Aopen+label%3Abug)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/enhancement?logo=github&label=Enhancements)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/PythonWorkflow/new%20step?logo=github&label=New%20Steps)](https://github.com/brobeson/PythonWorkflow/issues?q=is%3Aopen+is%3Aissue+label%3A%22new+step%22)
[![GitHub milestone details](https://img.shields.io/github/milestones/progress/brobeson/PythonWorkflow/1?logo=github)](https://github.com/brobeson/PythonWorkflow/milestone/1)

[Report a bug](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=bug&projects=&template=bug.yaml) |
[Request a new step](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=new+step&projects=&template=new_step.yaml) |
[Update an existing step](https://github.com/brobeson/PythonWorkflow/issues/new?assignees=brobeson&labels=enhancement&projects=&template=enhancement.yaml)
