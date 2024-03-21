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
    - `Delete the branch`    
        - To delete the branch, first you have to move the other branch than the branch which you want to delete.
        - Example:
            - Let's say you are having two branch "main", "feature/jira-1234"
            - Now if you want to delete branch named "feature/jira-1234" then first you need to switch to main branch and from there you can trigger the command to delete the feature branch
            - git checkout main
            - git branch -D feature/jira-1234
            - Above command will delete the feature branch
    -`Check current active branch`
        - git branch
        - Above command will git list of branches available under the repo and the branch which is in active state it will get displayed with "*"
        - Example: "* main" (mainly highlighted in green color)
    -`Merge changes to another branch`
        - You can merge changes of one branch to another branch
        - Let's say you have a two branch named "feature1", "feature2
        - Now you made changes under branch "feature1"  and commited the changes under feature1
        - Now you switched to branch "feature2" and want to have a changes from branch "feature1"
            - `git checkout feature2`
            - `git merge feature1`
        - Above command will merge all the changes of feature1 to feature2

**GitHub Actions - Key Elements**
    -`Workflows:`
        - Attached to a github repository
        - Contains one or more Jobs
        - Triggered upon events defined for the repo. This events can be triggered manual or in automated way.
    -`Jobs:`
        - Define a runner(execution environment). This runner can be weither the pre-defined runner defined by the GitHub or can be your own runner hosted on your server.
        - Contain one or more Steps which will get executed under the runner
        - Run in parallel(default) or sequential
        - Can be conditional
    -`Steps:`
        - Execute a shell script or an Action(It is predefined task)
        - Can use custom or third party actions
        - Steps are executed in order

**Multiple Jobs under same workflow**
    
    - This is very important. Every job gets its own runner, it's own virtual machine that's totally isolated from other machines and jobs.
    - If you want that one job should be depend on another job then you need add the the keyword "Needs"
        - Example: Needs: <Job-name-on-which-it-depends>
    - If your job is depends on multiple jobs then you can also define the job names as array
        - Example: Needs [<jobName1>,<JobName2>]
    - If you want your workflow to be triggered by automated action and also by manual trigger then you can below on events:
        - Example: on: [push, workflow_dispatch]
