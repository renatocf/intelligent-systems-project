# Server

In the second part of this project, we will create an **API** for the
**categorization model** developed previously.

More specifically, you will **develop a server** that should receive data
related to **products** and return the best **categories** for them using a
**pretrained model**.

More info about the data can be found [here][1].

## Server API

Your API should be composed of the following components:

1. **Model Loading** <br>
   Loads a pretrained model from a specified path available in the environment
   variable `MODEL_PATH`.

2. **Categorization Endpoint** <br>
   Exposes a **POST** endpoint `/v1/categorize` that receives a JSON with
   product data and returns a JSON with their predicted categories.

3. **Input Validation** <br>
   Returns status `400 (Bad Request)` in case of ill-formatted user input
   without killing the API.

4. **[BONUS] Contract Testing** <br>
   Runs automated tests from a file `test_api.py` to validate the API
   responses according to different inputs.

**NOTE:** To test your API, you must provide a JSON file generated from the
dataset `test_producs.csv`, containing a valid input for your API
implementation. This file should be saved in the path available in the
environment variable `TEST_PRODUCTS_PATH`.

## Implementation

The server API should be implemented using the [Flask Library][2] in a file
named `api.py`.

Use [Python comments][3] to document **relevant** details about your
implementation. Remember that good documentation should focus on the **why**
(e.g., why a specific type of model was chosen), since clean code should be
enough to understand the **how** (e.g., how you selected a specific type of
model).

## Input

The expected input for the server should follow the following schema:
```json
{
  "products": [
    {
      "title": "Lembrancinha"
    },
    {
      "title": "Carrinho de Bebê"
    }
  ]
}
```
You **MAY** expect to **receive other fields** besides the title to
represent the products. Remember, however, to use as key the name of the field
specified in the [raw data][1].

## Output

The expected output from the server should follow the following schema:
```json
{
  "categories": [
    "Lembrancinha",
    "Bebê"
  ]
}
```
You **MUST NOT** send other fields besides the category.

## Infrastructure

In this directory, we provide a **containerized environment** that uses
[docker][4] and [docker-compose][5] to run the API. This should standardize the
development environment and avoid compatibility problems.

To install docker and docker-compose, check their official documentation
[here][4] and [here][5]. Both tools should be instalable at Linux, MacOS and
Windows.

To execute the API, just run the following command:
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
[2]: https://flask.palletsprojects.com/en/1.1.x/
[3]: https://realpython.com/documenting-python-code/
[4]: https://docs.docker.com/get-docker
[5]: https://docs.docker.com/compose/install
[6]: https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29
