# Git Notes
## Summary
Git is a version control system, typically used for source code management.  
Alongside Git is GitHub which also provides other useful project management tools.  

## Installation
### Windows
Be sure to install [Git for Windows](https://gitforwindows.org/).  
Once installed make sure you can then use Git commands in Powershell.  
Visual Studio should also detect Git once installed.  

### MacOS
Install with Homebrew `brew install git`.  

### Linux
Install with Apt `sudo apt install git`.  

### Common
For each, you will need to configure credentials locally to match GitHub credentials.  
`git config --global user.name <username>`    
`git config --global user.email <email>`  
For your first commit, you may be prompted for a password.  
Be sure you use an active Token provided in the GitHub account settings.  

## Commands
| Command | Description |
|---------|-------------|
| `git clone <repo_address>`| Clones a remote repository locally into the current folder |
| `git status` | Displays information about the repo such as modified files and current branch |
| `git branch` | List all local branches |
| `git checkout <branch>` | Checkout a given branch (will also pull a branch if remote) |
| `git checkout -b <branch>` | Checkout a new branch off of the current branch |
| `git pull` | Pulls the latest changes from remote repository and updates your local repo |
| `git add <files>` | Stages files with changes for commit |
| `git commit -m <message>` | Commit all staged changes with a commit message |
| `git push` | Pushes all changes on the branch to the upstream/remote branch |
| `git stash` | Temporarily store changes on a branch and revert back to most recent commit |
| `git stash pop` | Returns the stored changes from `git stash` |
| `git log` | Display the log of previous commits |
| `git revert --hard <commit>` | Revert back to previous commit, discarding all commits ahead of given commit |
| `git revert <commit>` | Revert back to previous commit, but make a new commit ahead of the current commit |

## Typical Workflow
```
# Update you repo and make a new branch
git pull
git status
git checkout -b MyNewBranch

# Make changes to my_modified_file.txt
git status
git add my_modified_file.txt
git commit -m "An example commit message"
git push

# Update your version of main
git checkout main
git pull
```

## Tips
- Use `git status` frequently. Always verify the files you are about to commit, add, modify first.
- Unless absolutely necessary, do not make direct commits to main. Repo admins can protect the main branch.
- Work on separate branches as another person to avoid git history conflicts with other people.
- Keeps commits small and single responsibility. Make commit messages descriptive with ticket numbers or action items.
- Try to keep large binary files out of the repo (except for Releases on GitHub). If necessary use [Git LFS](https://git-lfs.com/) to minimize repo size. If using lots of binaries, consider using Plastic SCM or Perforce for those objects.
- Link pull requests on GitHub to tickets. Project managers like [ZenHub](https://www.zenhub.com/) can help with this.
- Always test your code before merging into the main. Run unit tests and make sure any CI/CD tests pass as well.
- When handling merge conflicts, the best way to solve is to use the help of VS Code or GitHub Editor (if small conflicts). If lots of conflict occur, check the commit history and see who modified the same file. Checking with them can typically resolve the conflict. Most conflicts usually resolve by adding both changes (same lines got modified).
- Using `git pull` frequently and merging with main early on if conflicts are expected can help avoid large merge conflicts.

## Links
- [GitHub](https://github.com/)
- [Git for Windows](https://gitforwindows.org/)
- [Git LFS](https://git-lfs.com/)
- [ZenHub](https://www.zenhub.com/)