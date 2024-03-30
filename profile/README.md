# ValUtils

In this organization you will find a bunch of utils and apps related to Valorant written in Python.

## Apps

There is currently 2 apps in this organization, [ValConfig](https://github.com/ValUtils/ValConfig) and [ValChange](https://github.com/ValUtils/ValChange).
Neither have documentation or easy to install process but in the future there will be docs per application and in this same README.

## DevEnvironment

### Prequisites

- Git
- Python =>3.8 (I recommend 3.9)
- pip

### Pip Shenanigans

I personally like to do is install the projects as [editables](https://pip.pypa.io/en/stable/topics/local-project-installs/#editable-installs).
This can be done with a simple command:

```sh
pip install -e Val
```

But if you need compatibility with your editor it'd be better to use:

```sh
pip install -e Val --config-settings editable_mode=compat
```

### How-To

Depending on what you wanna work it might be enough to just clone the repo you are trying to work on.
But if you intend on working with the whole stack I recommend cloning and installing all projects.

```sh
git clone https://github.com/ValUtils/ValLib.git
git clone https://github.com/ValUtils/ValStorage.git
git clone https://github.com/ValUtils/ValVault.git
git clone https://github.com/ValUtils/ValConfig.git
git clone https://github.com/ValUtils/ValImgs.git
git clone https://github.com/ValUtils/ValChange.git
pip install -e ValLib --config-settings editable_mode=compat
pip install -e ValStorage --config-settings editable_mode=compat
pip install -e ValVault --config-settings editable_mode=compat
pip install -e ValConfig --config-settings editable_mode=compat
pip install -e ValImgs --config-settings editable_mode=compat
pip install -e ValChange --config-settings editable_mode=compat
```

### Formatting

For sorting dependencies I use `isort` with the following arguments:

```sh
isort . --atomic --star-first --combine-star --combine-as --remove-redundant-aliases --multi-line=3
```

or

`pyproject.toml`
```
[tool.isort]
atomic = true
star_first = true
combine_star = true
combine_as_imports = true
remove_redundant_aliases = true
multi_line_output = 3
```

And my code formatter is `autopep8`.

## Creating a new package

In case I ever need to create a new package I follow the next directory structure

```
.
├── .github
├── test
├── ValName
├── .gitattributes
├── .gitignore
├── License
├── README.md
└── pyproject.toml
```

In which `LICENSE` would be `GPL-3` and the other files would need to be filled accordingly.
