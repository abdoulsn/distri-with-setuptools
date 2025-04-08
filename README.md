# [Packaging and distributing projects - SetupTools](https://packaging.python.org/en/latest/guides/distributing-packages-using-setuptools/#packaging-and-distributing-projects)

First, make sure you have already fulfilled the requirements for installing packages.  

Install “twine”:

### Install twine
```bash
  uv pip install twine
```

### Configuring your project
Initial files to setup
```bash
  uv touch setup.py MANIFEST.in README.md setup.cfg LICENSE
```

### Set setup() arguments
This consist of settingp up the arguments for: packages, install_requires, entry_points, classifiers, package_data, scripts,
data_files, namespace_packages, test_suite, tests_require, etc.   

See [setup()](https://packaging.python.org/en/latest/guides/distributing-packages-using-setuptools/#setup) for more information.

### Packaging your project

```bash
  py -m pip install build
  # or
  uv pip install build
```

### Source distributions
Minimally, you should create a Source Distribution
```bash
  [python|py] -m build --sdist
  # or
  uv build --sdist  # quicker
```
### Wheel distributions
```bash
  [python|py] -m build --wheel
  # or
  uv build --wheel # quicker
```

### All distributions
```bash
  [python|py] -m build
  # or
  uv build # quicker
```

### Buil --wheel and sdist
```bash
  [python|py] -m build --wheel --sdist
  # or
  uv build --wheel --sdist  # quicker
```

### check
```bash
  [python|py] -m twine check dist/*
  # or
  uv run python -m twine check dist/*
```
### Another way to check
```bash
(.venv) ~\Documents\distri-with-setuptools git:[main] twine check dist/*
    Checking dist\distri_with_setuptools-0.1.0-py3-none-any.whl: PASSED
    Checking dist\distri_with_setuptools-0.1.0.tar.gz: PASSED

(.venv) ~\Documents\distri-with-setuptools git:[main] uv run python -m twine check dist/*
    Checking dist\distri_with_setuptools-0.1.0-py3-none-any.whl: PASSED
    Checking dist\distri_with_setuptools-0.1.0.tar.gz: PASSED
```

### Uploading your project
```bash
  [python|py] -m twine upload dist/*
  # or
  uv run python -m twine upload dist/*
```

