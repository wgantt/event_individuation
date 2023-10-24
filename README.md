# event\_individuation
This is the official repository for the following paper:

> [On Event Individuation for Document-Level Information Extraction](https://arxiv.org/abs/2212.09702). William Gantt, Reno Kriz, Yunmo Chen, Siddharth Vashishtha, and Aaron Steven White. In *Findings of the Association for Computational Linguistics: EMNLP 2023*.

This repository provides:

- The materials, raw annotations, and analysis for the reannotation study described in Section 4 of the paper (see the `reannotation_study` directory).
- The model predictions and code for the analysis of the event individuation capabilities of template filling models presented in Section 5 of the paper (see the `model_predictions` directory).

Each of these directories contains its own README with more detailed information. Unfortunately, only results for MUC-4 can be made available, as the BETTER data (available [here](https://ir.nist.gov/better/) with free registration) is subject to usage agreements that prevents us from releasing them ourselves. If you acquire access to these datasets, however, please feel free to contact Will Gantt (wgantt.iv@gmail.com) for those results.

## Setup

This repository uses [Poetry](https://python-poetry.org/) for dependency installation and management. After cloning this repository, you should create and activate a new virtual environment using the platform of your choosing (e.g. virtualenv, Conda). We used Python 3.11, so (e.g.) if you are using Conda, you can run:

```
conda create -n <environment_name> python=3.11
```

Next, `cd` into the project root (if you haven't already) and install Poetry:

```
cd <project_root>
poetry install
```

You should now be able to run the Jupyter notebooks (`reannotation_study/Reannotation Study Analysis.ipynb` and `Multi Template Instance Investigations.ipynb`), as well as the model prediction evaluation script (`third_party/eval.py`) used to produce the results in the paper. See the READMEs in each subdirectory of the project root for more information.


## Questions and Issues

Please submit questions and issues to this repository using the GitHub Issues feature. For private communications, feel free to email Will Gantt (wgantt.iv@gmail.com).
