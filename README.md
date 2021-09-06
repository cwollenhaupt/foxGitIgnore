# foxGitIgnore
Generic .gitignore file for FoxPro development as a team or as an individual developer who works on multiple features in different branches.

Important: This .gitignore file is not meant for individual developers who create a linear history of their working folders for lookup and backup purposes. The .gitignore file specifically excludes the binary files and all one-way text files such as SCCTEXT. In order to use this .gitignore file, you must use a tool that handles the binary to text to binary conversion such as [TwoFox](https://bitbucket.org/cwollenhaupt/foxpert.tools.twofox) or [FoxBin2Prg](https://github.com/fdbozzo/foxbin2prg). Please refer to #1 and #2 for a discussion on this topic.

Copy the file into your working folder and rename to ".gitignore" by removing the ".example" extension, then add all project specififc exclusions at the end.
