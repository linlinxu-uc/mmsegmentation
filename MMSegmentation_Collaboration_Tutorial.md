
# Tutorial for Collaborating on the MMSegmentation Project

This guide will walk you through how to:

- Clone the repository.
- Make changes and commit them.
- Push changes to the gsilab_segmentation branch.
- Sync with the latest code from the main branch.

---

## 1. Download the Project
Clone the repository to your local machine:
```bash
git clone https://github.com/linlinxu-uc/mmsegmentation.git
cd mmsegmentation
```

Set up the environment:

Create a virtual environment (optional but recommended):
```bash
python -m venv mmseg-env
source mmseg-env/bin/activate  # On Windows: mmseg-env\Scripts\activate
```

Install dependencies:
```bash
pip install -r requirements.txt
pip install -v -e .
```

---

## 2. Switch to the gsilab_segmentation Branch
Fetch all branches from the remote repository:
```bash
git fetch --all
```

Switch to the gsilab_segmentation branch:
```bash
git checkout gsilab_segmentation
```

---

## 3. Make Changes
Create a new branch for your work (optional but recommended):
```bash
git checkout -b your-branch-name
```
Replace `your-branch-name` with a descriptive name for your changes (e.g., feature/new-model or bugfix/data-augmentation).

Make your changes:

- Edit files in the project (e.g., add new models, fix bugs, or update configurations).
- Test your changes to ensure they work as expected.

---

## 4. Commit Your Changes
Stage your changes:
```bash
git add .
```
This adds all modified files to the staging area. If you only want to add specific files, replace `.` with the file names.

Commit your changes with a meaningful message:
```bash
git commit -m "Describe your changes here"
```
Example:
```bash
git commit -m "Add new U-Net model for segmentation"
```

Push your branch to the remote repository:
```bash
git push origin your-branch-name
```

---

## 5. Push to the gsilab_segmentation Branch
If you created a new branch (`your-branch-name`), you’ll need to merge it into `gsilab_segmentation`:

Switch to the gsilab_segmentation branch:
```bash
git checkout gsilab_segmentation
```

Merge your changes into gsilab_segmentation:
```bash
git merge your-branch-name
```

Push the updated gsilab_segmentation branch to the remote repository:
```bash
git push origin gsilab_segmentation
```

---

## 6. Get the Newest Code
To stay up-to-date with the latest changes in the main branch:

Switch to the main branch:
```bash
git checkout main
```

Pull the latest changes from the upstream repository:
```bash
git pull upstream main
```

Rebase the gsilab_segmentation branch onto the latest main branch:
```bash
git checkout gsilab_segmentation
git rebase main
```

Resolve conflicts (if any):

- Open the conflicting files in a text editor.
- Resolve the conflicts and save the files.

Stage the resolved files:
```bash
git add <resolved-file>
```

Continue the rebase:
```bash
git rebase --continue
```

Push the updated gsilab_segmentation branch:
```bash
git push --force origin gsilab_segmentation
```

---

## 7. Best Practices
- **Commit Often**: Make small, logical commits with clear messages.
- **Branch Naming**: Use descriptive branch names (e.g., feature/new-model, bugfix/data-augmentation).
- **Pull Requests**: Always create a PR for your changes and request a review from teammates.
- **Sync Regularly**: Regularly pull the latest changes from main to avoid conflicts.

---

## 8. Example Workflow
Clone the repository:
```bash
git clone https://github.com/linlinxu-uc/mmsegmentation.git
cd mmsegmentation
```

Switch to the gsilab_segmentation branch:
```bash
git checkout gsilab_segmentation
```

Create a new branch:
```bash
git checkout -b feature/new-model
```

Make changes and commit:
```bash
git add .
git commit -m "Add new U-Net model"
git push origin feature/new-model
```

Merge into gsilab_segmentation:
```bash
git checkout gsilab_segmentation
git merge feature/new-model
git push origin gsilab_segmentation
```

Sync with the latest code:
```bash
git checkout main
git pull upstream main
git checkout gsilab_segmentation
git rebase main
git push --force origin gsilab_segmentation
```
