# PSI_Fire_Detection
Fire detection project made for Machine Learning Summer School in Petnica Summer Institute (2025)


## Standards of committing and branching on the repository
1. Developers create a feature branch from main.
```bash
git checkout -b name/feature
```
Example:
```bash
git checkout -b miron/initial-setup
```

2. Developers commit to this branch in the following manner:
```bash
git commit -m "action: short description"
```
Example:
```bash
git commit -m "add: initial infrastructure for the project"
```
The actions that should generally be used are: `add`, `update`, `fix`. Removing something constitutes updating it, so give an additional comment in that case.

3. When work is done (everything that's improtant for the feature is committed), they create a pull request.
```bash
git push origin name/feature
```
Example:
```bash
git push origin miron/initial-setup
```
4. CI/CD runs status checks (linting, tests, etc).
5. Code is reviewed and approved.
- This is important because the developers need to be up to date with what is being done on the project.
6. The PR is merged using rebase and fast-forward, keeping a linear history. When merging the pull request, you should select the option to `squash and merge`.
- The source branch can be deleted when merged.
7. No merge commits, ensuring a clean Git history.
8. When you are finished, to update the remote repo with your own:
```bash
git checkout main
git fetch --prune
git pull --rebase
```

General adding, committing tips:
- Use `git status` a lot to see what you're working with.
- Use `git tree` to see what branch you're checked out to (as well as the commit history), so there is no mixup to what branch it's being committed to.


## Environment setup
### 1. Virtual environment setup
There are two approaches to running this project:
1. Create virtual environment using Conda

```bash
conda create --name venv_fire python=3.10
conda activate venv_fire
```


2. Use vanilla python to setup virtual environment:
- Windows (cmd):
```bash
python3.10 -m venv venv
venv\Scripts\activate
```
- Windows (PowerShell):
```bash
python3.10 -m venv venv
venv\Scripts\Activate.ps1
```
- Windows (Git Bash):
```bash
python3.10 -m venv venv
source venv/Scripts/activate
```
- Linux/macOS:
```bash
python3.10 -m venv venv
source venv/bin/activate
```

- Note: To deactivate a virtual environment, in the terminal run `conda deactivate` for the first case, and `deactivate` for the second case.

### 2. Installing dependencies

1. After installing and activating the virtual environment, the next step is installing dependencies:
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

Optional: Verify installation and setup
```bash
python --version        # Should be 3.10.x
pip list                # Confirm packages are installed
```


2. Pre-commit install for local linting (flake8, black, isort) (Optional, Dev only):
```bash
pip install pre-commit==2.13
pre-commit install
```

3. Install Git Large file storage, for the models to be tracked
```bash
git lfs install
```

### 3. Visual Studio Code setup (Optional, Dev only)
I suggest installing the following extensions, and configuring them in the settings:
- Black formatter, then go into VS Code settings > As a Default formatter add Black formatter > Search for Black > To `Black-formatter: Args` add: `--line-length=99`.
- Flake8, then go into VS Code settings > Search for Flake8 > For `Flake8: Import Strategy` put `fromEnvironment`.
- isort, then go into VS Code settings > Search for Flake8 > For `isort: Import Strategy` put `fromEnvironment`.
- Python Extension Pack is good too.
- RainbowCSV for easier viewing of `.csv` files.
- vscode-pdf for easier viewing of `.pdf` files.

This ensures there's no need to run pre-commit each time (the linting happens automatically most of the time, because of the extensions), consequently making the code versioning part a little less daunting.

DELETE: test
