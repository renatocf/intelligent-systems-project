# Training

In the first part of this project, we will create the **training pipeline** for
a **categorization model**.

More specifically, you will **train a model** that should receive data related
to **products** and return the best **categories** for them.

More info about the data can be found [here][1].

## Training Pipeline

Your training pipeline should be composed of the following steps:

1. **Data extraction** <br>
   Loads a dataset with product data from a specified path available in the
   environment variable `DATASET_PATH`.

2. **Data formatting** <br>
   Processes the dataset to use it for training and validation.

3. **Modeling** <br>
   Specifies a model to handle the categorization problem.

4. **Model validation** <br>
   Generates metrics about the model accuracy (precision, recall, F1, etc.)
   for each category and exports them to a specified path available in the
   environment variable `METRICS_PATH`.

5. **Model exportation** <br>
   Exports a candidate model to a specified path available in the environment
   variable `MODEL_PATH`.

## Implementation

The training pipeline should be implemented using [JupyterLab][2] in a file
named `trainer.ipynb`.

Use [Markdown cells][3] to document **relevant** details about your
implementation. Remember that good documentation should focus on the **why**
(e.g., why a specific type of model was chosen), since clean code should be
enough to understand the **how** (e.g., how you selected a specific type of
model).

## Infrastructure

In this directory, we provide a **containerized environment** that uses
[docker][4] and [docker-compose][5] to run JupyterLab. This should standardize
the development environment and avoid compatibility problems.

To install docker and docker-compose, check their official documentation
[here][4] and [here][5]. Both tools should be instalable at Linux, MacOS and
Windows.

To execute JupyterLab, just run the following command:
```bash
docker-compose up --build
```
Then open the link shown in the end.

To install an OS package (Debian-based), add the name of the package in the file
`packages.txt`. To intall a Python package (Pip-based), add the name and version
of the package in the file `requirements.txt`.

## Evaluation

The evaluation will be based on four criteria:

1. **Correctness** <br>
   If the solution runs without unexpected errors.

2. **Compliance** <br>
   If the solution respects all specified behaviors, in particular concerning
   inputs and outputs.

2. **Code Quality** <br>
   If the solution follows the principles of [clean code][6] and general good
   practices discussed in class.

3. **Documentation** <br>
   If the solution documents **relevant** decisions in the right measure.

[1]: ../data/README.md
[2]: https://jupyter.org
[3]: https://jupyter-notebook.readthedocs.io/en/stable/examples/Notebook/Working%20With%20Markdown%20Cells.html
[4]: https://docs.docker.com/get-docker
[5]: https://docs.docker.com/compose/install
[6]: https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29
