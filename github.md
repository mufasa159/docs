# GitHub

### New Repository Setup

Create a new repository on the command line  
```
echo "# dash" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/mufasa159/dash.git
git push -u origin main
```

Push an existing repository from the command line
```
git remote add origin https://github.com/mufasa159/dash.git
git branch -M main
git push -u origin main
```