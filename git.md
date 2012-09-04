# prepare environment

    $ git config --global core.editor "vim"
    $ git config --global user.email "you@example.com"
    $ git config --global user.name "Your Name"

# clone repo

    $ git clone git://192.168.0.13/<repo_name>
    $ cd <repo_name>

# track untracked files

    $ git add .

# upload modifications to local repo

    $ git commit -a

# Upload local modification to a remote repo

    $ git push <remote> <branch>

example:

    $ git push origin master

# show *working directory* status

    $ git status

# show differences between *working directory* and *stage*

    $ git diff <file>

# show remotes

    $ git remote

# merge branch to master

    $ git checkout master
    $ git merge <branch>

# create submodule

    $ git submodule add https://repo.git git_modules/repo

# remove submodule

http://stackoverflow.com/questions/1260748/how-do-i-remove-a-git-submodule

1.  Delete the relevant section from the .gitmodules file.
2.  Delete the relevant section from .git/config.
3.  Run git rm --cached path_to_submodule (no trailing slash).
4.  Commit and delete the now untracked submodule files.
