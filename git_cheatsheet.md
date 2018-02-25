# Git Cheatsheet

## Squash: Merge multiple commits together

### Steps:
1. Check your commit log by typing: `git log` in your console.
2. Count how many commits you wanna go back by then type:
    * `git rebase -i HEAD~num_of_commits_back`
    * where `num_of_commits_back` is the number of commits back the oldest commit you want to merge is.
3. A window will open showing the commits you can merge. Change `pick` to `squash` or `s` for the commits you want to merge.
   Save and close.
4. Another window will open for you to choose your commit message. Delete everything and enter your new commit message.
   Save and close.
### Example
1. `git log`
    * returns:
      ```
        commit 365d9848e90f7580002320200f4a2000230d0c5b
        Author: John Doe <johndoe@gmail.com>
        Date:   Sat Feb 23 21:39:01 2018 -0600

            Final fix for bug on index page foreal foreal

        commit d5b12eba08183db4999b02406e0704f1460c8c3f
        Author: John Doe <johndoe@gmail.com>
        Date:   Sat Feb 23 20:49:54 2018 -0600

            Fix other bug on index page foreal

        commit 3dbec41608183dba9308dc06c120a26893bf720f
        Author: John Doe <johndoe@gmail.com>
        Date:   Fri Feb 23 19:23:56 2018 -0600

            Fix other bug on index page

        commit dc06c84608183dba9308dc06c120a26893bf720f
        Author: John Doe <johndoe@gmail.com>
        Date:   Fri Feb 23 17:23:56 2018 -0600

            Fix bug on index page
        
        commit 183d984608183dba9308dc06c120a26893bf720f
        Author: John Doe <johndoe@gmail.com>
        Date:   Fri Feb 23 17:10:56 2018 -0600

            Add magnificent things on index page
     ```
2. You want to merge together the series of "Fix bugs..." commits. So you count 4 and type `git rebase -i HEAD~4`
    * returns:
      ```
        pick 365d984 Final fix for bug on index page foreal foreal
        pick d5b12eb Fix other bug on index page foreal
        pick 3dbec41 Fix other bug on index page
        pick dc06c84 Fix bug on index page

        # Rebase f60e8aa..6e17880 onto f60e8aa (4 commands)
        #
        # Commands:
        # p, pick = use commit
        # r, reword = use commit, but edit the commit message
        # e, edit = use commit, but stop for amending
        # s, squash = use commit, but meld into previous commit
        # f, fixup = like "squash", but discard this commit's log message
        # x, exec = run command (the rest of the line) using shell
        # d, drop = remove commit
        #
        # These lines can be re-ordered; they are executed from top to bottom.
        #
        # If you remove a line here THAT COMMIT WILL BE LOST.
        #
        # However, if you remove everything, the rebase will be aborted.
        #
        # Note that empty commits are commented out
      ```
3. Change `pick` to `squash` or `s` for the commits you want to merge.
    * Top part should look like:
      ```
        s 365d984 Final fix for bug on index page foreal foreal
        s d5b12eb Fix other bug on index page foreal
        s 3dbec41 Fix other bug on index page
        s dc06c84 Fix bug on index page
      ```
    * Save and close.
4. Another window will open showing the commits you have for each of the commits to squash. Remove everything except for the commit you want to have for the combined commits.
    * Ex.
      ```Fix bug on index page```
    * Save and close.
5. Type `git log` to check if it worked.
