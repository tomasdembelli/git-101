# git-101
Following `git` commands demonstrates a simple workflow where a contributor adds a new feature to an existing project using the `git` version control system.

These commands are not meant to be exhaustive, but some pointers only. 

## Downloading a repository
Create a new directory with the repo name (In this case, it will be `git-101`).
Download the remote repository into it.
```shell
git clone git@github.com:tomasdembelli/git-101.git
```

Give the directory a specific name, i.e., `git_101_new_feature`.
```shell
git@github.com:tomasdembelli/git-101.git git_101_new_feature
```

_Note: The rest of the commands should be run from (inside) the repository directory. For Linux/Mac `cd git-101` to enter the local copy._


## Creating a new branch for our work
_Note that if this is a project of your own, then you might prefer working on the main/master branch directly. In that case, there is no need to create a new branch. You can move to the next section._

Give your new branch a name.
In a team environment, the name should _generally_ contain:
- the author-name
- task/issue number
- short description of the content of the new branch 
```shell
git branch -m johnsmith/task-123/add-db-client
```

Checkout to the new branch.
From this moment forward, the changes will be committed to this branch.
```shell
git checkout johnsmith/task-123/add-db-client
```

## Commit and push changes to the remote server
Add changes to the staging index in one go.
```shell
git add .
``` 

Changes can also be divided into smaller logical sections.
```shell
git add docs/how-to-use-db-client.md
```

Commit changes with a short message.
```shell
git commit -m 'Add DB client'
```

Push changes to the remote repository.

_Note that this step assumes that your `git` client has programmatic access to the remote repository. Such as with an [SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)._


```shell
git push
```

_Note that `git` will prompt you with an error that this branch does not exist in the remote repository. It will also provide the command on how to add it. Just copy/paste and run the suggested command. The suggested command should look like this:_
```shell
git push --set-upstream origin <your-branch-name>
```
Then you can try the `git push` command again.

After that, the peer-review (PR) phase starts.
This is where your co-workers review your changes and leave feedback.
After addressing their comments, they should approve your changes.
An approved PR can be merged on the application UI that serves/stores your repository, such as GitHub. 

