**Configure username and emailId for new git repo**
    - git config --global user.name "your-username"
    - git config --global user.email "your-email"

**Move between different commits**
    - git checkout <id>
    - Above command will allow to temporarly move to another commit using commit id
    - HEAD pointer basically describes or point towards which current commit is loaded.
    - By default HEAD pointer points to the latest commit

**Revert specific commit changes**
    - git revert <id>
    - By above command we can revert changes of commit by creating a new commit

**Revert multiple commits**
    - git reset --hard <id>
    - By above command, we can undo changes by deleting all commits since <id>

**useful git commands**
![Git commands](commands.png)


**What is branches in git**
    -  Branches are like a container which contains commits
    - feature branch is branch where you can implement feature specific commit without impacting the main branch.
    - You can merge the feature branch changes to main branch using below command:
        - First you should be on the branch which you want to be merge with main branch
        - After that execute below command:
            - git merge <branchName>
            - e.g. git merge main
    -`Naming convetion for branch`
        - It is common practice to use all the alphabets in lowercase
        - If there are multiple words then it's very common to separate multiple words with slashes("/")
        - Example: branch names would be "feature/blog", "dev/bugfix" etc
    
