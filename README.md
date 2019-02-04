# Petfinder.my adoption prediction

Helping those pets to find home.

## Instructions

Download Kaggle data to `input` and unzip:

```bash
$ make download
```

**Important**

Kaggle kernels expect to find the dataset in directory `../input`. In contrast, for a notebook in path
`kernels/exploration`, the dataset is found in `../../input`. To be able to use the same code
both locally and in Kaggle, add a symbolic link in `kernels/` pointing to `input/`:

```bash
ln -sf ../input ./kernels/input
```

## Notebook organization

All kernels should have their own folder in `kernels/`.

Before a kernel with a given folder can be pushed to Kaggle from command-line, it needs the metadata file `kernel-metadata.json` in the same folder. You can create it either by running 

```bash
$ kaggle kernels init -p /path/to/kernel/directory
```

to initialize the file, or check [kernel-metadata.json](./kernels/1.0-initial-exploration/kernel-metadata.json)
for reference and copy it (with appropriate changes) to the folder with your kernel.

Once you're happy with the kernel and metadata has been setup, push it to Kaggle for execution:

```bash
$ kaggle kernels push -p /path/to/kernel/directory
```

Note that all kernels are private by default.

#### Detailed organization

```
    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make download` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── unzip_input.sh     <- Bash script for unzipping all archives in `input`
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    |
    |── input              <- Raw data downloaded from Kaggle with `make download`
    |
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── kernels                 <- Jupyter notebooks. Naming convention is a number (for ordering),
    │   └ 1.0-initial-exploration  the creator's initials, and a short `-` delimited description, e.g.
    │                              `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    └── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
                              generated with `pip freeze > requirements.txt`

```

Project created with the [cookiecutter](https://github.com/audreyr/cookiecutter)
template for [Kaggle competitions](https://github.com/Meeshkan/cookiecutter-kaggle-kernels).