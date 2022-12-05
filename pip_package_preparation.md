1. A simple project

This tutorial uses a simple project named example_package_YOUR_USERNAME_HERE.

Create the following file structure locally:

packaging_tutorial/
└── src/
    └── example_package_YOUR_USERNAME_HERE/
        ├── __init__.py
        └── example.py

__init__.py is required to import the directory as a package, and should be empty.

example.py is an example of a module within the package that could contain the logic (functions, classes, constants, etc.)

2. Creating the package files
Add files that are used to prepare the project for distribution, like this:

packaging_tutorial/
├── LICENSE
├── pyproject.toml
├── README.md
├── src/
│   └── example_package_YOUR_USERNAME_HERE/
│       ├── __init__.py
│       └── example.py
└── tests/

3. Creating pyproject.toml
 You can define like above example :
    [build-system]
    requires = ["hatchling"]
    build-backend = "hatchling.build"

    [project]
    name = "my_web_app"
    classifiers = ["Private :: Do Not Upload"]
    version = "0"
    dependencies = ["Flask"]
You can run and test:
    $ python -m piptools compile \
        -o requirements.txt \
        pyproject.toml

4. Configuring metadata
Add above dependecies to the pyproject.toml :

[project]
name = "example_package_YOUR_USERNAME_HERE"
version = "0.0.1"
authors = [
  { name="Example Author", email="author@example.com" },
]
description = "A small example package"
readme = "README.md"
requires-python = ">=3.7"
classifiers = [
    "Programming Language :: Python :: 3",
    "License :: OSI Approved :: MIT License",
    "Operating System :: OS Independent",
]

[project.urls]
"Homepage" = "https://github.com/pypa/sampleproject"
"Bug Tracker" = "https://github.com/pypa/sampleproject/issues"
5. Creating README.md
6. Creating a LICENSE