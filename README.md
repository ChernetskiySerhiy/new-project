# new-project

Jira: PROM-42164 — Set up new Git repository and create development branch.

## Step-by-step instructions

1. Create a new directory and go into it:
   ```bash
   mkdir new-project
   cd new-project
   ```
2. Initialize a Git repository with the `main` branch:
   ```bash
   git init -b main
   ```
3. Create `README.md` with initial text:
   ```bash
   echo "# new-project" > README.md
   ```
4. Stage the file and make the first commit:
   ```bash
   git add README.md
   git commit -m "init"
   ```
5. Create the `development` branch and switch to it:
   ```bash
   git checkout -b development
   ```
6. Add instructions to `README.md`, then stage and commit them with a Jira Smart Commit message:
   ```bash
   git add README.md
   git commit -m "PROM-42164 #comment Add step-by-step instructions to README"
   ```
7. Switch to `main` and merge `development` into it:
   ```bash
   git checkout main
   git merge development
   ```
8. Check that everything is up to date:
   ```bash
   git status
   ```
9. Connect the GitHub repository and push both branches:
   ```bash
   git remote add origin https://github.com/ChernetskiySerhiy/new-project.git
   git push -u origin main
   git push -u origin development
   ```

## Smart Commit format

`<ISSUE-KEY> #comment <text>`, for example `PROM-42164 #comment Add step-by-step instructions to README`.
Jira links the commit to the ticket and adds the text as a comment.
