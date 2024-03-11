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


