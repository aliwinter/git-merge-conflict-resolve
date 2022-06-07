# git-merge-conflict-resolve

This repository is meant to practise the process of resolving merge conflicts

fork this repository and follow the steps below.

# Steps:


1. Create a new branch and add a new line to the `file.txt`.

    i.e. create a branch called `change-a`
    ```BASH
<<<<<<< HEAD
    $ git checkout -B change-a # make a new branch
    $ git push --set-upstream origin change-a # push branch to remote
    $ cat file.txt  # update file.txt
=======
    $ git checkout -B change-a
    $ git push --set-upstream origin change-a
    $ git push --set-upstream origin change-a
    $ cat file.txt   
>>>>>>> change-a
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
<<<<<<< HEAD
    $ git checkout main # go back to your main branch
    $ git checkout -B change-b # checkout a new branch with name change-b
    $ git push --set-upstream origin change-b # push this new branch to remote
    $ cat file.txt # make a change to this file in same place as step 1
=======
    $ git checkout master
    $ git checkout -B change-b
    $ git push --set-upstream origin change-b
    $ cat file.txt
>>>>>>> change-a
    one
    two
    three
    change-b # add this line to file.txt
    $ git add file.txt
    $ git commit -m "change-b: made a change to file.txt"
    $ git push --set-upstream origin change-a # only need to do this
    ```

3. Merge merge main onto change-a branch:

    ```
    $~ git checkout main
    $~ git merge change-a # merge change-a branch onto main
    $~ git push
    ```

4. Now try to merge Branch Be.  (This should cause a conflict)

    ```
    $~ git merge change-b
    Auto-merging file.txt
    CONFLICT (content): Merge conflict in file.txt
    Automatic merge failed; fix conflicts and then commit the result.
    ```

    you should now see a a merge conflict within the change-b branch should look something like this.
    ```
    # file.txt
    <<<<<<< HEAD
    change-a
    =======
    change-b
    >>>>>>> change-b
    ```
    Resolve this by going into the file and choosing the change. the HEAD shows the latest changes within the branch you are merging to ( in this case the main branch) this is known as Current Changes because these changes are currently on the branch we are merging onto.  The changes below the `=======` are known as the Incoming changes (in this case the change-b branch).


