# Introduction
foxGitIgnore contains two different templates that work for different types of development. First find out which of the two sections better describes your working style.

## .gitignore.single
You are the only developer on this project or you are part of a team, but all of you work in the same network folder. You use git to maintain a linear history of your work and/or as a mean to backup your working folder to a remote location. You regularly check-in the current state. You might or might not use a hosted git service such as github, bitbucket or gitlab. 

If you take a graphical look at your commit history, you see a long line of commits. You are not using any merge commits.

Your goal is to maintain an exact copy of the working folder in git. You use git to view the differences you made over a period of time, to roll back to the last working version if your current approach turns out not to be working, and from time to time you want to go back to an older version of your entire working folder to reproduce bugs.

To accomplish this goal you keep as much of the binary files in git. You are not using any tooling to facilitate merging. After you cloned a repository, you want to instantly be able to build the project.

## .gitignore.team
You are part of a team with each team member having their own copy of the working folder. Or, you are a single developer who is using git branches to separate different features, switch between different tickets or test various approaches.

Your graphical commit history resembles a public transport map with multiple lines going parallel merging in various directions.

You use tooling such as [TwoFox](https://bitbucket.org/cwollenhaupt/foxpert.tools.twofox) or [FoxBin2Prg](https://github.com/fdbozzo/foxbin2prg) to maintain textual versions of all VFP binary files. You perform a binary-text and text-binary conversion before updating the repository. Work of others or your own work from different branches gets frequently merged into other branches and the main branch (formerly known as the master branch). 

Because binary files cannot easily be merged and because you need a single source of truth in the repository to reliably merge code, you only maintain a text version of your binary files in the repository that can be converted both ways. You do not keep binaries or old style SCCTEXT files in the repository.

# Usage
Decide which one of the two files you need. Copy the file into your working folder and rename to ".gitignore" by removing the extra extension, then add all project specific exclusions at the end.

# Alternative approaches
These two .gitignore files are based on the approach to exclude what definitely should not be in the repository and include anything else. When you add a new file that is not in the exclusion list, you will see this as an unversioned or unstaged file in your working folder (the exact description depends on the git client you use). You can then decide whether this new file is something that must go into the repository or should remain outside. 

Adding a new file type to the repository is a rare occurrence in the life-cycle of a project. This approach ensures that new files types will not go unnoticed. You do not have to remember what the process is because the existence of the file will remind you that you have to make a decision.

Lutz Scheffler uses a different approach in [FoxBin2Prg](https://github.com/fdbozzo/foxbin2prg/blob/master/docs/FoxBin2Prg_git.md). He excludes everything by default and only includes what has to go into the repository. The advantage of this approach is that you do not have to modify the .gitignore file when you introduce new file types that should stay out of the repository.