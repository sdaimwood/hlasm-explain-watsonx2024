# InstructLab@IBM Taxonomy

This starter repository is for you to use to get started on developing your custom taxonomy.

Just click on the [**Fork**](https://github.ibm.com/instructlab-at-ibm/taxonomy-template/fork) button to create a fork of this repository for you to use. Pick an owner and repository name for your fork which makes sense for you. Once done feel free to replace this README file with something specific to your project.

And see the [public taxonomy repository README](https://github.com/instructlab/taxonomy/blob/main/README.md) for information on the form of taxonomy files.

## Checking the validity of your taxonomy files

The IBM Enterprise GitHub instance does not currently support GitHub actions which means that a lot of the infrastructure in place for the [open source InstructLab project](https://github.com/instructlab) does not work for InstructLab@IBM. This includes in particular a YAML linter that automatically checks the validity of the YAML files submitted as a contribution to the open source project via a Pull Request.

For InstructLab@IBM you can of course use off the shelf YAML checkers but this repository template includes the same script as the one that is run on the open source project. It just won't get triggered automatically for you so instead, you need to run it manually.

You can check a taxonomy file to make sure it has proper linting standards and conforms to the schema of a taxonomy file.

First you should create a Python virtual environment for Python 3.11 or later and then activate the virtual environment. With [Miniforge](https://github.com/conda-forge/miniforge) you do:

```sh
conda create -n instructlab-taxonomy python=3.11
conda activate instructlab-taxonomy
```

Then install the requirements for the `check-yaml` script:

```sh
python -m pip install -r scripts/requirements.txt
```

You can then check an individual taxonomy file with:

```sh
scripts/check-yaml.py compositional_skills/my/taxonomy/path/qna.yaml
```

And you could check all the qna files with something like:

```sh
scripts/check-yaml.py $(find . -name "qna.yaml" -print)
```

For more information on this script can be obtained with:

```sh
scripts/check-yaml.py --help
```
