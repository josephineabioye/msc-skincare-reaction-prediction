# Notebook Starter

This helps me recreate my working environment faster each time I create a new notebook.

It does four things:

- Connects to my GitHub repo, either cloning it (if it's not there yet) or pulling the latest changes (if it already is) so my project files are accessible.
- Configures my Git identity so my commits go through.
- Mounts my Google Drive so I can access my dataset files.
- Sets up shortcut variables so I don't have to type long paths every time I read or save data.

## Prerequisites

- A GitHub personal access token added to Colab Secrets under the name `GITHUB_TOKEN`
- A Google Drive folder at `MyDrive/msc-skincare-project/` with `data/raw/` and `data/processed/` subfolders inside it

## Setup cell

```python
from google.colab import userdata, drive
import os

GITHUB_TOKEN = userdata.get('GITHUB_TOKEN')
GITHUB_USERNAME = 'josephineabioye'
REPO_NAME = 'msc-skincare-reaction-prediction'

if not os.path.exists(REPO_NAME):
    !git clone https://{GITHUB_TOKEN}@github.com/{GITHUB_USERNAME}/{REPO_NAME}.git
    %cd {REPO_NAME}
else:
    %cd {REPO_NAME}
    !git pull

!git config user.email "josephineabioye@yahoo.com"
!git config user.name "Josephine Abioye"

drive.mount('/content/drive', force_remount=False)

DRIVE_PROJECT = '/content/drive/MyDrive/msc-skincare-project'
DATA_RAW = f'{DRIVE_PROJECT}/data/raw'
DATA_PROCESSED = f'{DRIVE_PROJECT}/data/processed'

print(f"Working in: {os.getcwd()}")
```

## Working with data

Read from Drive:

```python
df = pd.read_csv(f'{DATA_RAW}/dataset.csv')
```

Save to Drive:

```python
df.to_parquet(f'{DATA_PROCESSED}/cleaned.parquet')
```

## Committing changes cell

```python
!git add .
!git commit -m "<describe what changed>"
!git push
```
