# python-template

## Linting our code

📚 Ahora que tenemos algunas pruebas, el siguiente paso lógico es comenzar a modificar nuestro código. Linting es el proceso de verificar nuestro código en busca de posibles errores y/o falta de formato. Existen muchos linters (pylint, flake8, black, etc.).

$ poetry add --group lint flake8 black isort mypy

A few examples of linting your code include:

> poetry run mypy hello_world_cli/cli.py
> poetry run flake8 hello_world_cli/cli.py
> poetry run black hello_world_cli/cli.py

## Testing: PyTest

We can add the most common python tests package, pytest

$ poetry add --group dev pytest

and the pytest coverage package to shows the code coverage

$ poetry add --group dev pytest-cov

Also, we need to add the test path for the pytest in the setup.cfg
After running them, we can run:

$ poetry run pytest --cov --cov-fail-under=100

## Automatización de las comprobaciones locales con pre-commit

📚 Ahora que comprendemos el linting y las pruebas, podemos comenzar a automatizar nuestras comprobaciones. El objetivo de automatizar nuestras comprobaciones es asegurarnos de que nuestro código esté siempre en buen estado. La confirmación previa es una excelente alternativa ya que básicamente nos impide enviar código incorrecto o mal formateado (como su nombre indica).

🛠️ Para instalar la confirmación previa, podemos ejecutar el siguiente comando:

Install the pre-commit using poetry:

$ poetry add --group dev pre-commit

Create a file called .pre-commit-config.yaml and then run the installation for the pre-commit

$ poetry run pre-commit install

Now, you can try to run the pre-commit using

$ poetry run pre-commit run --all-files

la confirmación previa está ejecutando las comprobaciones que definimos en el 
fidhero .pre-commit-config.yaml.

and every time you commit, the pre-commit config will also runs.
You can always run:

git add .
git commit --no-verify -m "feat: ..."

## Automatice las comprobaciones remotas con GitHub Actions

📚 Ahora que tenemos algunas pruebas y algunos linters, podemos comenzar a automatizar nuestras comprobaciones en el lado del servidor. Si bien existen muchas herramientas que pueden ayudarnos a automatizar nuestras comprobaciones (GitHub Actions, Travis CI, Circle CI, etc.), yo personalmente uso y recomiendo Github Actions (también conocido como GHA).

pendiente

## Automatiza nuestro lanzamiento con GitHub Actions

📚 Hemos hablado brevemente sobre linting (usando black, flake8, isort y mypy) y pruebas (usando pytest). La versión es un concepto igualmente importante que nos permite dar versiones a instantáneas específicas de nuestro código. Conceptualmente, asigna un sha de confirmación con un número (v1.2.3).

pendiente