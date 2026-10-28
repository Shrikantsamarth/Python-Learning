Scenario 1: First-Time Setup (New Repository)


# 1. Go to the folder and initialize Git
cd ~/Documents/Notebook
git init

# 2. Confirm the exact file names (watch for spaces and commas)
ls

# 3. Ignore Jupyter checkpoint folders
echo ".ipynb_checkpoints/" > .gitignore
git add .gitignore

# 4. Set your identity (one-time; use the email linked to your GitHub account)
git config --global user.name "Shrikant"
git config --global user.email "your-github-email@example.com"

# 5. Stage your notebooks
git add "Python Learning 1-Print,Datatype,Syntax,Variable.ipynb"
git add "Python Learning 2-Identifier,TypeConversion.ipynb"
git add "Python Learning 3-Literals,OPERATORS.ipynb"
git add "Python Learning 4-DecisionControl, IF,ELSE.ipynb"

# 6. Commit
git commit -m "Add Python learning notebooks 1-4"

# 7. Connect to GitHub and push
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main



Scenario 2: Adding New Changes to an Existing Repository
# Use this when you’ve already pushed once and want to upload new or edited notebooks.
cd ~/Documents/Notebook
git status                          # See what changed
git add -A                          # Stage all changes (or a specific file)
git commit -m "Update operators examples"
git push



Scenario 3: Push Rejected Because GitHub Has Newer Commits
# This happens when GitHub has files you don’t have locally, such as a README or LICENSE created during repo setup.
git pull --rebase origin main
git push -u origin main

# If the rebase stops with a conflict:
1. Open the conflicting files, fix the conflict markers, then:
git add -A
git rebase --continue

2. Push again
git push -u origin main

# If you want to abort and start over:
git rebase --abort



Scenario 4: Updating an Existing Notebook
# Same as Scenario 2, but a good commit message describes the change.

cd ~/Documents/Notebook
git add -A
git commit -m "Refine IF/ELSE examples in notebook 4"
git pull --rebase origin main       # Always pull first when GitHub may have changed
git push


Scenario 5: Adding a Brand-New Notebook to an Existing Repo
cd ~/Documents/Notebook
git add -A
git commit -m "Add new notebook"
git pull --rebase origin main
git push -u origin main