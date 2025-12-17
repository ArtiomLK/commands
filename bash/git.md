# Git Basic Commands

```bash
#  ------------------------------------------------------------------------------------------------
# Init git environment
#  ------------------------------------------------------------------------------------------------
# Set user name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"


#  ------------------------------------------------------------------------------------------------
# Starting a Repository
#  ------------------------------------------------------------------------------------------------
# Initialize a new Git repository
git init

# Clone an existing repository
git clone <repository_url>


#  ------------------------------------------------------------------------------------------------
# Basic Operations for SDLC
#  ------------------------------------------------------------------------------------------------
# Check the status of the repository
git status

# create a new branch and switch to it
git checkout -b <branch_name>

#  ---------------------
# Making Changes
#  ---------------------
# Add files to staging area
git add .  # Add all changes

# Commit changes with a message
git commit -m "Your commit message"

# Push changes to remote repository
git push origin <branch_name>
```
