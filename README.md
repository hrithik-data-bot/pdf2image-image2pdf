# xyz

TODO: add description about xyz

</br>

## Installation  

For package install:

```bash
conda install xyz
```

*see `development` section for details on how to softlink the code*

</br>

## Project Structure

The directory structure of xyz looks like this:

```
│
├── conda.recipe                        <- contains meta.yaml file for building conda package
│
├── xyz       <- python package
        │
        ├── cli.py                      <- entry point for the CLI application
        │
        ├── rest.py                     <- REST API endpoints
        │
        ├── settings.py                 <- configuration management for the application
        │
        ├── app_logging.py              <- logging management for the application
│
├── tests                               <- code for Unit testing, Regression testing etc.
│
├── environment.yml                     <- conda environment for testing and development
│
├── Makefile                            <- pre-configured shell scripts for common tasks
│
├── README.md                           <- top-level README for developers
│
├── setup.py                            <- app packaging and installation
```

</br>

## Development and Tests

__Create an environment__:
create a new conda environment named `xyz` by running the following commands:

```bash
cd xyz
conda env create --file environment.yml
```

__Activate the envirionment__:
activate the newly created conda environment:

```bash
conda activate xyz
```

__Run the tests__:
In order to test this package, activate the environment created above and run:

> `pytest` or `make test`

</br>

## Soft Linking

If you want to use the application from other environments without repackaging everything then use soft linking.
Using the conda environment, navigate to the application folder to develop the application:

```bash
cd xyz
python setup.py develop
```

OR the following (___new and recommended___) technique:

>
```bash
cd xyz
pip install -e .
```

</br>

## Release

A package release is made via a git tag:

```bash
cd xyz 
git checkout master
git pull
git tag -a 0.0.x -m "0.0.x"
git push --tags
```
