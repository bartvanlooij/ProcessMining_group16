# ProcessMining_group16
This is a group project made for the course 2IOI0 - Process Mining 

Currently there are two branches:
- main
- develop

For a quick update about how to work with git can be found here: 
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

But otherwise this Readme should cover how to work with git

We will be working on the branch _develop_ and merging with _main_. Main will thus contain our final product!

_"The master branch is meant to be stable, and it is the social contract of open source software to never, 
ever push anything to master that is not tested, or that breaks the build. "_

### Setup
To set up the local repo do the following (in cmd):

1. 'git clone https://github.com/poopeloep/ProcessMining_group16.git' (or ssh depending on your own setup)
2. 'cd ProcessMining_group16'
3. Check that you are on main branch by: 'git branch'
- If not, do: 'git checkout main'
4. Now we want to set from which branch your local branch should be updated. And this is the remote/<branch>. Do this: 'git branch -u origin/main'
5. Now we'll do the same for develop branch.
- 'git checkout develop'
- 'git branch -u origin/develop'
6. To check if they're being tracked correctly: 'git branch -vv'
- This should print something like
develop ....... [origin/develop] <commit msg>
main  ....... [origin/main] <commit msg>

### Daily 
When you start working on something, to make sure that you're working on the updated files, once you navigate to your local repo, do the following:
- 'git checkout develop'
- 'git pull'
Then, it would be recommended to work on a new branch on the develop branch. To do so do:
- 'git checkout -b <feature_name>' (calling it a feature branch because of the convention, although for our purposes it's most likely not a feature)
After you're done making some changes, and you want to commit it to the feature branch:
- 'git add <file_name>' or 'git add .' (adds all files that have been changed)
- 'git commit -m "_Change into a message explaining what you did_" '
- 'git push develop <feature_name>'
Now you can merge this <feature_name> branch to the _develop_ branch.

### Merging
"Very important: when merging, we need to be on the branch
that we want to merge to. Basically, we will be telling git,
“See that new thing? It’s ok to bring it over here now.” "

According to this, we would have to: 
- 'git checkout develop'
- 'git pull origin develop' (to make sure no new changes have been made while you were working on the feature)
- 'git merge <feature_name> –no-ff' (-no-ff is only needed in situations when you're merging something important)
If you do not run into merge conflicts you can simply:
- 'git push origin develop'

If you do run into merge conflicts, and you do not know how to fix it, just make sure that they are pushed to the <feature_name> branch and let the group know about the conflict. 

### Fixing the Merge conflicts:

Check this website for a detailed description: https://dev.to/neshaz/how-to-use-git-merge-the-correctway-25pd

Generate a list of the files which need to be resolved: 'git status'
When the conflicted line is encountered, Git will edit the content of the affected files with visual indicators that mark both sides of the conflicting content. These visual markers are:
\*
  * <<<<<<< - Conflict marker, the conflict starts after this line.
  * ======= - Divides your changes from the changes in the other branch.
  * \>>>>>>> - End of the conflicted lines.

Example:
\* 
  * \<<<<<<< HEAD(develop)
  * conflicted text from HEAD(develop)
  * \=======
  * conflicted text from feature_name
  * \>>>>>>> feature_name

- Decide if you want to keep only your feature_name or develop changes, or write a completely new code. Delete the conflict markers before merging your changes.
- When you're ready to merge, all you have to do is run git add command on the conflicted files to tell Git they're resolved.
- Commit your changes with git commit to generate the merge commit.

### Merging to Master
- git checkout master
- git merge develop -no-ff
- git push origin master
To delete a merged branch: git branch -d <branch_name> 
No worries: if you accidentally attempt to delete a branch that has not yet been merged, git will throw an error.



"Because, remember: Don’t. Mess. With. The. Master. "
