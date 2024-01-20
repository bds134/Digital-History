# Lesson GitHub Version Control System

## Lesson overview

This lesson provides instruction on how to connect Visual Studio Code (VSC) to GitHub and how to utilize GiHubs Version Control System (VCS) to edit within VSC and to make commits to GitHub.

## GitHub

[The Pro Git Book](https://git-scm.com/book/en/v2 "The entire Pro Git book, written by Scott Chacon and Ben Straub and published by Apress") provides excellent documentation for GitHub.

## Commit Options

There are three options for committing changes:

1. Commit: Records changes that you have made on your local machine. It will not mark the change in the remote repository.
2. Commit (amend): Modifies the most recent commit.
3. Commit & Push: Does the above and pushes it to the remote repository. This means that any changes you have made will be saved to the remote repository as well.
4. Commit & Sync: Does three things. First, it will commit. Second, it will perform a pull (grabs the updated information from the remote repo). Finally, it will push.

## The seven rules of a great Git commit message

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line
4. Do not end the subject line with a period
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how
