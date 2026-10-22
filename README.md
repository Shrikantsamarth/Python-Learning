-- Go to the Notebook folder and create the repository there
cd ~/Documents/Notebook
git init

--Check the exact file names
ls

--Ignore the checkpoint folder
echo ".ipynb_checkpoints/" > .gitignore
git add .gitignore

--Git needs to know who you are before it can commit. Set your name and the email linked to your GitHub account:
git config --global user.name "Shrikant"
git config --global user.email "your-github-email@example.com"

--Add each notebook one by one
git add "Python Learning 1-Print,Datatype,Syntax,Variable.ipynb"
git add "Python Learning 2-Identifier,TypeConversion.ipynb"
git add "Python Learning 3-Literals,OPERATORS.ipynb"
git add "Python Learning 4-DecisionControl, IF,ELSE.ipynb"

-- Commit
git commit -m "Add Python learning notebooks 1-4"


--Connect to GitHub and push
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main



--- When changes made 
git add "filename.ipynb"
git commit -m "Update operators examples"
git push
