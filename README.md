# git-merge-conflict-resolve

This repository is meant to practise the process of resolving merge conflicts

fork this repository and follow the steps below.

# Steps:


1. Create a new branch and add a new line to the `file.txt`.

    i.e. create a branch called `change-a`
    ```BASH
    $ git checkout -B change-a # make a new branch
    $ git push --set-upstream origin change-a # push branch to remote
    $ cat file.txt  # update file.txt
    one
    two
    three
    change-a # add this line to file.txt
    $ git add file.txt # add this file to the change on this branch
    $ git commit -m "change-a: made a change to file.txt" # create a commit message
    $ git push # push to the remote repository
    ```

2. Checkout out a new branch off of master and make a change to the `file.txt` that is different than the change made in step 1, but on the same line.
    
    i.e. 
    ```BASH
    $ git checkout main # go back to your main branch
    $ git checkout -B change-b # checkout a new branch with name change-b
    $ git push --set-upstream origin change-b # push this new branch to remote
    $ cat file.txt # make a change to this file in same place as step 1
    one
    two
    three
    change-b # add this line to file.txt
    $ git add file.txt # add this file to the commit
    $ git commit -m "change-b: made a change to file.txt" # create a commit message
    $ git push
    ```

3. Merge merge main onto change-a branch:

    ```
    $~ git merge --onto main
    ```



