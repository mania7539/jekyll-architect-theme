---
published: true
---
* Type in commands as below for completing multiple git commit

```bash	
$ mkdir branch
$ cd branch

# initialize git #
$ bitbucket create --private --protocol ssh --scm git [YOUR_REPO_NAME=branch]
$ git remote
$ git init
$ git remote
$ git remote add git@bitbucket.org:mania7539/[YOUR_REPO_NAME=branch]

# edit file and commit for 3 times" #
$ echo add 1 > echo.txt
$ git add .
$ git commit -m "commit 1"
$ echo add 2 >> echo.txt
$ git add .
$ git commit -m "commit 2"
$ echo add 3 >> echo.txt
$ git add .
$ git commit -m "commit 3"

# push 1 time #
$ git push --set-upstream origin master
```

![commit-3_push-1.png]({{site.url}}{{site.baseurl}}/images/commit-3_push-1.png)



* How to push the commmits from separate into one?


```bash
# edit file and commit for 3 times" #
$ echo add 7 > echo.txt
$ git add .
$ git commit -m "commit 7"
$ echo add 8 >> echo.txt
$ git add .
$ git commit -m "commit 8"
$ echo add 9 >> echo.txt
$ git add .
$ git commit -m "commit 9"

# rebase - pick and squash #
$ git rebase -i
```

* It will show a rebase interactive editor as below

![rebase_pick-squash.png]({{site.url}}{{site.baseurl}}/images/rebase_pick-squash.png)


* Then the commit message editor will show up for you to edit commit message
![rebase_commit-combine-message.png]({{site.url}}{{site.baseurl}}/images/rebase_commit-combine-message.png)


* git push after rebase and previous steps

```bash	
# push 1 time #
$ git push origin master
```

* Now you will get only one commit to push in the repository

![bitbucket_rebase-result.png]({{site.url}}{{site.baseurl}}/images/bitbucket_rebase-result.png)