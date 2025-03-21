
# Setting Up an gsilab_segmentation Project with Git

Setting up an **MMSegmentation** project in a way that allows you to:

1. Record all your modifications to the code.
2. Pull updates from the main branch of the original MMSegmentation repository.

can be achieved using **Git** and a proper workflow. Here's a step-by-step guide to set this up:

---

## 1. Fork the MMSegmentation Repository
1. Go to the [MMSegmentation GitHub repository](https://github.com/open-mmlab/mmsegmentation).
2. Click the **Fork** button to create your own copy of the repository under your GitHub account.

---

## 2. Clone Your Forked Repository
1. Clone your forked repository to your local machine:
   ```bash
   git clone https://github.com/your-username/mmsegmentation.git
   cd mmsegmentation
   ```
2. Add the original MMSegmentation repository as a remote (to pull updates later):
   ```bash
   git remote add upstream https://github.com/open-mmlab/mmsegmentation.git
   ```

---

## 3. Create a New Branch for Your Modifications
Create a new branch for your project:
   ```bash
   git checkout -b my-project
   ```
Make all your modifications in this branch. This keeps your changes isolated from the main branch.

---

## 4. Commit Your Changes
Stage your changes:
   ```bash
   git add .
   ```
Commit your changes with a meaningful message:
   ```bash
   git commit -m "Added custom modifications for my project"
   ```
Push your branch to your forked repository:
   ```bash
   git push origin my-project
   ```

---

## 5. Pull Updates from the Original Repository
To pull updates from the original MMSegmentation repository:

1. Switch to the main branch:
   ```bash
   git checkout main
   ```
2. Fetch updates from the original repository:
   ```bash
   git fetch upstream
   ```
3. Merge the updates into your main branch:
   ```bash
   git merge upstream/main
   ```
4. Push the updated main branch to your forked repository:
   ```bash
   git push origin main
   ```

---

## 6. Rebase Your Project Branch
To incorporate updates from the original repository into your project branch:

1. Switch to your project branch:
   ```bash
   git checkout my-project
   ```
2. Rebase your branch onto the updated main branch:
   ```bash
   git rebase main
   ```
3. Resolve any conflicts that arise during the rebase.

4. Push the rebased branch to your forked repository:
   ```bash
   git push --force origin my-project
   ```

---

## 7. Use a .gitignore File
To avoid tracking unnecessary files (e.g., logs, checkpoints), create a .gitignore file in your repository:
   ```bash
   # Ignore logs and checkpoints
   logs/
   work_dirs/
   *.pyc
   __pycache__/
   ```

---

## 8. Regularly Sync with the Original Repository
To keep your forked repository up-to-date with the original MMSegmentation repository:

1. Fetch updates from the original repository:
   ```bash
   git fetch upstream
   ```
2. Merge updates into your main branch:
   ```bash
   git merge upstream/main
   ```
3. Rebase your project branch onto the updated main branch:
   ```bash
   git checkout my-project
   git rebase main
   ```

---

## 9. Use a Virtual Environment
To manage dependencies and avoid conflicts:

1. Create a virtual environment:
   ```bash
   python -m venv mmseg-env
   source mmseg-env/bin/activate  # On Windows: mmseg-env\Scripts\activate
   ```
2. Install MMSegmentation and its dependencies:
   ```bash
   pip install -r requirements.txt
   pip install -v -e .
   ```

