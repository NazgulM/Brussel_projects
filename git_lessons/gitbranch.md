Create Git branch using checkout
The easiest way to create a Git branch is to use the “git checkout” command with the “-b” option for a new branch. Next, you just have to specify the name for the branch you want to create.

$ git checkout -b <branch-name>
As an example, let’s say that you want to create a new Git branch from the master branch named “feature”

To achieve that, you will run the “git checkout” command with the “-b” option and add “feature” as the branch name.

$ git checkout -b feature
Switched to new branch 'feature'

Create Git Branch without switching
In order to create a new Git branch, without switching to this new branch, you have to use the “git branch” command and specify the name of the Git branch to be created.

$ git branch <branch_name>
You can later on switch to your new Git branch by using the “git checkout” function.

$ git checkout <branch_name>
Going back to our previous example, let’s say that you want to create a branch named “feature”.

$ git branch feature
You can inspect existing branches by running the “git branch” command with the “-a” option for all branches.

$ git branch -a

Create Git Branch from Commit
In the last sections, we have seen how you can create a new Git branch from the HEAD commit of the current branch.

In some cases, you want to create a Git branch from a specific commit in your Git history.

In order to create a Git branch from a commit, use the “git checkout” command with the “-b” option and specify the branch name as well as the commit to create your branch from.

$ git checkout -b <branch_name> <commit_sha>
Alternatively, you can use the “git branch” command with the branch name and the commit SHA for the new branch.

$ git branch <branch_name> <commit_sha>
Going back to our previous example, let’s say that you want to create a Git branch from a specific commit in your Git history.

To get commits SHA from your history, you have to use the “git log” with the “–oneline” option.

$ git log --oneline --graph

- 9127753 (HEAD -> master) Commit 3
- f2fcb99 Commit 2
- cab6e1b (origin/master) master : initial commit
  To create a new Git branch from the second commit (f2fcb99), you would run the following command

$ git checkout -b feature f2fcb99
Switched to a new branch named 'feature'
Using the “git log” command, you can verify that your branch was created from the second commit of your history.

$ git log --oneline --graph

- f2fcb99 (HEAD -> feature) Commit 2
- cab6e1b (origin/master) master : initial commit
  Awesome, you have successfully created a new Git branch from a specific commit!

Create Git Branch from Tag
In previous tutorials, we have seen that Git tags are pretty useful : they can be use as reference points in your development.

As a consequence, it can be quite useful to create Git branches from existing tags.

In order to create a new Git branch from a tag, use the “git checkout” command with the “-b” option and specify the branch name as well the tag name for your new branch.

$ git checkout -b <branch_name> <tag_name>
Alternatively, if you don’t want to switch to your new branch, you can use the “git branch” with the branch name and the tag name.

$ git branch <branch_name> <tag_name>
Back to our previous example, let’s say that you want to create a new Git branch from a tag named “v1.0” in your history.

In order to list your existing tags, you can use the “git tag” command. Alternatively, you can use the “git log” command to identify a tag associated with a commit.

$ git tag
v1.0
Now that you have identified your tag, you can create a new branch from it using the “git checkout” command.

$ git checkout -b feature v1.0
Next, you can inspect your Git history in order to make sure that your new branch was indeed created from the tag.
