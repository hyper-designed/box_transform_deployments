How to delete old commits and clear file history to save space.

1. Checkout repo.
2. Delete all files.
3. Commit changes. git commit -m "Delete all files."

Next, create a new commit with a small change. Such as adding back this ReadMe after deleting all files.
A new commit makes sure the delete and remove files commit is not saved.

git add *
git commit -m "Create ReadMe"

Now, get the hash of this new commit. git rev-parse HEAD
Follow the steps below to create a completely new branch without any old files.

git checkout --orphan tempBranch <COMMIT_HASH> // Create a new unconnected branch with the same hash as the main branch.
git branch -d  main // Delete old main
git branch -m main // Rename tempBranch to main
git push origin main --force
