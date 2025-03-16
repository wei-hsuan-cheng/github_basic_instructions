# GitHub: create/push/commit repositories

### 1. Ensure Git is installed

If you haven’t already installed Git, install it using your package manager. For example, on Ubuntu:

```bash
sudo apt update
sudo apt install git
```

### 2. Install the GitHub CLI

Using the GitHub CLI (command: `gh`) makes creating repositories from the terminal easier.

On Ubuntu, you can install it as follows:

```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

Then log in:

```bash
gh auth login
```

Follow the prompts to authenticate with your GitHub account.

### 3. Initialise your local Git repository

Open a terminal and navigate to the root of your directory (for example, the `<github_repo_name>` folder). Then run:

```bash
cd <your_path>/<github_repo_name>  # adjust path as needed
git init && git add . && git commit -m "Initial commit"
```

### 4. Create a new GitHub repository using GitHub CLI

Now create a repository on GitHub. For example, if you want your repository to be public and named `<github_repo_name>`, run:

```bash
gh repo create <github_repo_name> --public --source=. --remote=origin
```

This command does the following:

- Creates a new public repository named `<github_repo_name>` under your GitHub account.
- Uses the current directory as the source.
- Sets the remote name to `origin`.

### 5. Push your code to GitHub

Finally, push your commit to the new remote repository. Depending on your default branch name (*e.g.* `main` or `master`), run:

```bash
# Check the existing branches
git branch

# Depending on the branch name (main or master, etc.)
git push -u origin main
git push -u origin master
```

Your project is now pushed to GitHub!

### 6. Commit and push

First navigate to the root of your directory, stage the changes, commit, and push.

```bash
cd <your_path>/<github_repo_name>  # adjust path as needed
git add . && git commit -m "commit_message" # stage and commit the changes

# Depending on the branch name (main or master, etc.)
git push -u origin main
git push -u origin master
```

### 7. Useful commands

```bash
# Sometimes if things just don't work, use this and you can push again
git pull --rebase origin main
git pull --rebase origin master

# Remove Git setting
rm -rf .git
```