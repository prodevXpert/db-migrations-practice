# Create new branch:
To create a new branch on GitHub using the terminal, follow these steps:
1. Open Terminal or cmd.
2. navigate to repository where you want to create new branch.
3. Ensure you are on the main branch by running the command ``` git checkout main ```
4. fetch the latest changes from remote repo to ensure you have the most up-to-date version by running the command ``` git fetch ```.
5. Create new branch based on main branch by running the command ``` git branch [new-branch-name] ```
6. Switch to the newly created branch using ``` git checkout [new-branch-name]``` command.
7. Push the new branch to remote repositry on github using the ``` git push origin [new-branch-name] ``` command

After completing these steps, you will have created a new branch named ``` [new-branch-name] ```