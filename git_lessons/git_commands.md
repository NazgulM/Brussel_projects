Solution

To fix the error, follow the steps below:

Inform Git of the location of the remote repository by running the following command:

git remote add origin <remote_URL>
where remote_URL is the link to the repository where you want your code to be stored.

Push your code by running the following command:

git push origin master

head commit
In Git, the commit you are currently on is known as the HEAD commit. In many cases, the most recently made commit is the HEAD commit.

To see the HEAD commit, enter:

git show HEAD