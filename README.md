# Python env examples

Here's a minimal example of package management via `pip` and secret management via `python-dotenv`.

## Setup

This assumes python is installed. I'm using `python3` as my python command. Yours might be just `python` depending on how it's aliased.
So if `python3` doesn't work, try `python` instead.

1. Install package dependencies
```bash
python3 -m pip install -r requirements.txt
```

The `requirements.txt` file lists the package dependencies. We specify which version of the packages we want to use there.

`python3 -m` makes sure the `pip` command is run with the same python version as the one you're using to run the script.

2. Create a `.env` file with your secrets
```bash
cp .env.example .env
```

3. Update the OPENAI_API_KEY in the `.env` file with your OpenAI API key

Since we have .env added in the .gitignore file, the .env file will not be pushed to the git repository. Just make sure to never push the .env file to the git repository.

4. Run the script
```bash
python3 main.py
```

## Script

The `main.py` script uses the `openai` package to call the OpenAI API. It also reads the `OPENAI_API_KEY` from the `.env` file.

```python
from dotenv import load_dotenv

load_dotenv()
```

For more info, check out the [python-dotenv](https://pypi.org/project/python-dotenv/) package.
