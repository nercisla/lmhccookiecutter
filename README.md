# `atoscookiecutter`

A cookiecutter template for analytical, Python-, or Python and R-based projects within
Atos.  It has been forked from the [govcookiecutter][govcookiecutter] repo:

This template helps to set up standardised project structures, and [includes security
features using pre-commit hooks][docs-pre-commit].

It also provides an Agile, centralised, and lightweight analytical quality assurance
(AQA) process. Pull or merge request templates are used to nudge users to complete this
process.

## Getting started

[First, make sure your system meets the
requirements](#requirements-to-create-a-cookiecutter-template). Next, open your
terminal, navigate to the directory where you want your new repository to exist. Then
run the following command for the latest stable release:

```shell
cookiecutter https://gitlab.com/GB_LON_ARAA/atoscookiecutter.git
```

or for a specific branch, tag, or commit SHA `{SPECIFIC}`, run:

```shell
cookiecutter https://gitlab.com/GB_LON_ARAA/atoscookiecutter.git --checkout {SPECIFIC}
```

Follow the prompts; if you are asked to re-download `atoscookiecutter`, input `yes`.
Default responses are shown in the squared brackets; to use them, leave your response
blank, and press enter.

Once you've answered all the prompts, your project will be created. Then:

1. Set up a Python virtual environment using [poetry][poetry]
2. In your terminal, navigate to your new project, and initialise Git
   ```shell
   git init
   ```
3. Install the necessary packages using `pip` and the pre-commit hooks:
   ```shell
   poetry install
   pre-commit install
   ```
   or use the `make` command:
   ```shell
   make requirements
   ```
4. Stage all your project files, and make your first commit
   ```shell
   git add .
   git commit -m "Initial commit"
   ```

### Requirements to create a cookiecutter template

To get started your system should meet the following requirements:

1. Python 3.6.1+ installed
2. R 4.0.4+ installed (optional)[^1]
3. The [`cookiecutter` package installed](https://github.com/best-practice-and-impact/govcookiecutter/blob/main/README.md#installing-the-cookiecutter-package)

[^1]: Only for combined Python and R projects, if selected in the prompts during
project creation.

#### Installing the `cookiecutter` package

There are many ways to install the `cookiecutter` package. Our recommendation is to
install it at the system or user level, rather than as a Python package with `pip` or
`conda`. This ensures it is isolated from the rest of your system, and always available.

For macOS, open your terminal, and [install `cookiecutter` with Homebrew][homebrew]:

```shell
brew install cookiecutter
```

For Debian/Ubuntu, use the following commands:

```shell
sudo apt-get install cookiecutter
```

Otherwise, you can install `cookiecutter` with `pip` — you may wish to create a virtual
environment first:

```shell
python -m pip install --user cookiecutter
```

## Licence

Unless stated otherwise, the codebase is released under the MIT License. This covers
both the codebase and any sample code in the documentation. 

## Acknowledgements

[The govcoookiecutter template is based off the DrivenData Cookiecutter Data Science
project][drivendata]. Specifically, it uses similar `data` and `src` folder structures,
and a modified version of the `help` commands in the `Makefile`s.

[docs-pre-commit]: https://github.com/nercisla/lmhccookiecutter/blob/main/.pre-commit-config.yaml
[drivendata]: http://drivendata.github.io/cookiecutter-data-science/
[govcookiecutter]: https://github.com/best-practice-and-impact/govcookiecutter
[homebrew]: https://brew.sh/
[poetry]: https://python-poetry.org/
