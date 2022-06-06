# git-merge-conflict-resolve

This repository is meant to practise the process of resolving merge conflicts

fork this repository and follow the steps below

# Steps:

1. Create a new branch and add a new line to the `file.txt`.

    i.e. create a branch called `change-a`
    ```BASH
    $ git checkout -B change-a
    $ git push --set-upstream origin change-a
    $ git push --set-upstream origin change-a
    $ cat file.txt   
    one
    two
    three
    change-a # add this line to file.txt
    $ git add file.txt
    $ git commit -m "change-a: made a change to file.txt"
    $ git push
    ```

2. Checkout out a new branch off of master and make a change to the `file.txt` that is different than the change made in step 1, but on the same line.
    
    i.e. 
    ```BASH
    $ git checkout master
    $ git checkout -B change-b
    $ git push --set-upstream origin change-b
    $ cat file.txt
    one
    two
    three
    change-b # add this line to file.txt
    $ git add file.txt
    $ git commit -m "change-b: made a change to file.txt"
    $ git push --set-upstream origin change-a # only need to do this
    ```



