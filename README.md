# Git Talk - Productive commands

 

 - **:wink:Add an specific file**: `git add [filename]`
 - **:ok_hand: Move some commit to a separate branch**: 
		 1. `git log`
		 2. Check or search the commit-hash
		 3. `git reset --hard [commit-hash]` 
		 4. `git checkout -b [new-branch-name]`
		 5. `git add .`
		 6. `git commit -m "[Your message here]"`
 - **:warning:Push a rebased local branch**: `git push -f`
 - **:nail_care:Polish my feature before submitting for review**: `git rebase -i [branch-name/commit hash]`
 - **:dango:Squash all commits into a single one and merge it into develop**: 
	 1. Go to your main branch (eg. develop) : `git checkout develop`
	 2. `git merge --squash [branch-name]`
	 3. `git commit`
	 4. Add your commit's message

- **:rocket: Git time-machine to undo something terrible    :boom::scream:**
	1.  `git reflog`
	2. Search for all the index HEAD@{index} and search for the command just before everything crashed
	3. `git resert HEAD@{index}`
- **:sweat_smile:Ups, I Just made a commit and forget to add a little change**:
	1. `git add .`
	2. `git commit --amend --no-edit`
- **:sweat_smile:Ups, I need to change my last commit's message**: `git commit --amend`
- **:see_no_evil:Holly Crap! I  just pushed to the wrong branch:running::dash:**
	1. Undo the last commit, but let the changes availables: `git reset HEAD~ --soft`
	2. `git stash`
	3. Move to the correct branch: `git checkout [branchname]`
	4. `git stash pop`
	5. `git add .`
	6. `git commit -m "Your message here"`

- **Or using cherry-pick**:
	1. `git checkout [correct-branch-name]`
	2. Get the last commit from master: `git cherry-pick master`
	3. `git checkout master`
	4. Delete the lat commit from master: `git reset HEAD~ --hard`
	
- **:leftwards_arrow_with_hook:   :pray: Yisus Craist! I need to undo a commit**:
	1. Search for the commit  and save its hash: `git log`
	2. `git revert [commit-hash]`
- **:shit: Oh mai Gudness, I need to undo the changes of an specific file**: 
	1. Search for the hash of the previous commit when the file was modified: `git log`
	2. `git checkout [commit-hash] --path/to/file`
	3. `git commit -m "New message"`
 - **:art:Enchulanding git**: `git config --global -e` and add any command or commands you based on your preference. Just like the example:
	 - `lg = log`
	 - `ls = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate`
	 - `ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat`
	 - `lds = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate  date=short`
	 - `ec = config --global -e`
	 - `co = checkout`
	 - `br = branch`
	 - `cm = commit -am`
	 - `st = status`
	 - `cp = cherry-pick`
	 - `save = !git add -A && git commit -m 'SAVEPOINT'`
	 - `wip = commit -am "WIP"`
	 - `undo = reset HEAD~1 --mixed`
	 - `amend = commit -a --amend`

**Note:warning:** : Commands like `git reset` or `git ammend` change the commit id/hash


