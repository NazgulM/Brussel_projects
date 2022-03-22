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

REDIRECTION
|
| is a “pipe.” The | takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as “command to command” redirection.

$ cat volcanoes.txt | wc  
Above, the output of cat volcanoes.txt becomes the standard input of wc. in turn, the wc command outputs the number of lines, words, and characters in volcanoes.txt, respectively.

$ cat volcanoes.txt | wc | cat > islands.txt 
Multiple |s can be chained together. Here the standard output of cat volcanoes.txt is “piped” to the wc command. The standard output of wc is then “piped” to cat. Finally, the standard output of cat is redirected to islands.txt.

You can view the output data of this chain by typing cat islands.txt.

sort
$ sort continents.txt 
sort takes the standard input and orders it alphabetically for the standard output (it doesn’t change the file itself). Here, the continents in continents.txt will be listed in alphabetical order:

Africa
Antarctica
Asia
Australia
Europe
North America
South America
$ cat glaciers.txt | sort > sorted-glaciers.txt 
Here, the command takes the standard output from cat glaciers.txt and “pipes” it to sort. The standard output of sort is redirected to a new file named sorted-glaciers.txt.

REDIRECTION
uniq
$ uniq deserts.txt 
uniq stands for “unique.” It filters out adjacent, duplicate lines in a file. Here uniq deserts.txt filters out duplicates of "Sahara Desert", because its duplicate directly follows the previous instance. The “Kalahari Desert” duplicates are not adjacent, and thus remain.

$ sort deserts.txt | uniq
A more effective way to use uniq is to call sort to alphabetize a file, and “pipe” the standard output to uniq. By piping sort deserts.txt to uniq, all duplicate lines are alphabetized (and thereby made adjacent) and filtered out.

sort deserts.txt | uniq > uniq-deserts.txt 
Here we simply send filtered contents to uniq-deserts.txt, which you can view with the cat command.

REDIRECTION
grep I
$ grep America continents.txt 
grep stands for “global regular expression print.” It searches files for lines that match a pattern and then returns the results. It is also case sensitive. Above, grep searched for anything that matched “America” in continents.txt.

$ grep -i America continents.txt
grep -i enables the command to be case insensitive. Here, grep searched for capital or lowercase strings that match “America” in continents.txt. Note that we don’t use quotes in our command.

The above commands are a great way to get started with grep. If you are familiar with regular expressions, you can also use regular expressions to search for patterns in files.