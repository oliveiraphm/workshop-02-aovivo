# workshop-02-aovivo

##Git
git clone git clone https://github.com/oliveiraphm/workshop-02-aovivo.git
.gitignore

##pyenv
pyenv local 3.11.5

##poetry
poetry init
###criação do .venv
poetry shell

##mkdocs
poetry add mkdocs
###geracao da pasta docs
mkdocs new .
poetry add 'mkdocs-mermaid2-plugin'

poetry add 'mkdocs-material'

poetry add 'mkdocstrings[python]'

no mkdocs.yml:

theme:
  name: material

plugins:
  - search
  - mermaid2
  - mkdocstring

poetry add taskipy
poetry add isort 
poetry add black
poetry add pytest

no final do pyproject.toml
[tool.taskipy.tasks]
format = """
isort .
black .
"""
kill = "kill -9 $(lsof -t -i :8000)"
test = "pytest -v"
run = """
python3 app/main.py
"""
doc = "mkdocs serve"

##CI/CD
criar a pasta .github/workflows
criar um arquivo .yml (CI.yml)

# how to install PostgreSQL (psycopg2)
sudo ap-get update
sudo apt-get install libpq-dev python-dev-is-python3
poetry add psycopg2