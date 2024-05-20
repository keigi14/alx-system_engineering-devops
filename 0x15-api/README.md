# 0x15-API
![api](https://appmaster.io/cdn-cgi/image/width=768,quality=90,format=auto/api/_files/PqV7MuNwv89GrZvBd4LNNK/download/)

## Learning Objectives
- What Bash scripting should not be used for
- What is an API
- What is a REST API
- What are microservices
- What is the CSV format
- What is the JSON format
- Pythonic Package and module name style
- Pythonic Class name style
- Pythonic Variable name style
- Pythonic Function name style
- Pythonic Constant name style
- Significance of CapWords or CamelCase in Python

## Project Requirements
- Allowed editors: `vi`, `vim`, `emacs`
- All your files will be interpreted/compiled on `Ubuntu 14.04 LTS` using python3 (version 3.4.3)
- All your files should end with a new line
- The first line of all your files should be exactly #!/usr/bin/python3
- Libraries imported in your Python files must be organized in alphabetical order
- A `README.md` file, at the root of the folder of the project, is mandatory
- Your code should use the `PEP 8 style`
- All your files must be executable
- The length of your files will be tested using `wc`
- All your modules should have a documentation `(python3 -c 'print(__import__("my_module").__doc__)')`
- You must use get to access to dictionary value by key (it won’t throw an exception if the key doesn’t exist in the dictionary)
- Your code should not be executed when imported (by using `if __name__ == "__main__":`)


# 0x15. API

# API

This project was further practice in working with API's. I collected data from the
[JSONPlaceholder REST API](https://jsonplaceholder.typicode.com/), and learned how
to export it to either CSV or JSON format.

## Tasks :page_with_curl:

* **0. Gather data from an API**
  * [0-gather_data_from_an_API.py](./0-gather_data_from_an_API.py): Python script
  that returns information on the to-do list progress of a given employee ID.
  * Usage: `python3 0-gather_data_from_an_API.py <employee ID>`.
  * Output: `Employee <employee name> is done with tasks(<# completed tasks>/<total # tasks>):`

* **1. Export to CSV**
  * [1-export_to_CSV.py](./1-export_to_CSV.py): Python script exports to-do list
  information of a given employee ID to CSV format.
  * Usage: `python3 1-export_to_CSV.py <employee ID>`
  * File name: `<user id>.csv`.
  * Format: `"<user id>","<username>","<task completed status>","<task title>"`.

* **2. Export to JSON**
  * [2-export_to_JSON.py](./2-export_to_JSON.py): Python script that exports
  to-do list information of a given employee ID to JSON format.
  * Usage: `python3 2-export_to_JSON.py <employee ID>`
  * File name: `<user id>.json`
  * Format: `{ "<user id>": [ {"task": "<task title>", "completed": <task completed status>, "username": "<username>"}}, ... ]}`

* **3. Dictionary of list of dictionaries**
  * [3-dictionary_of_list_of_dictionaries.py](./3-dictionary_of_list_of_dictionaries.py):
  Python script that exports to-do list information for all employees to JSON format.
  * Usage: `python3 3-dictionary_of_list_of_dictionaries.py`
  * File name: `todo_all_employees.json`
  * Format: `{ "<user id>": [ {"username": "<username>", "task": "<task title>", "completed": <task completed status>}, {"username": "<username>", "task": "<task title>", "completed": <task completed status>}, ... ], "<user id>": [ {"username": "<username>", "task": "<task title>", "completed": <task completed status>}, {"username": "<username>", "task": "<task title>", "completed": <task completed status>}, ... ]}`
