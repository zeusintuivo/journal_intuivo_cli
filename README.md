# journal_intuivo_cli
Bash Utitilies to help keep focus during programing and yield positive results. Providing several tools to organize, and keep track of "WHAT CHANGED?" and "WHAT DID I DO?." As an aid for git tools using command line

# Install

I recommend just putting in the path or making softlinks to the scripts from `/usr/local/bin/`

I also recommend using a script I build that will make suchs softlinks automatically called `link_folder_scrips`

You can find this script in
`
https://github.com/zeusintuivo/bash_intuivo_cli
`
or more specifically

`
https://github.com/zeusintuivo/bash_intuivo_cli/blob/master/link_folder_scripts
`
or just the file
`
https://raw.githubusercontent.com/zeusintuivo/bash_intuivo_cli/master/link_folder_scripts
`

You basically can just use these lines oneliner curl
```
mkdir -p ~/bin/
git clone https://github.com/zeusintuivo/journal_intuivo_cli.git ~/bin/journal_intuivo_cli
cd ~/bin/journal_intuivo_cli
curl -o- https://raw.githubusercontent.com/zeusintuivo/bash_intuivo_cli/master/link_folder_scripts | bash
```
or using wget
```
mkdir -p ~/bin/
git clone https://github.com/zeusintuivo/journal_intuivo_cli.git ~/bin/journal_intuivo_cli
cd ~/bin/journal_intuivo_cli
wget -qO- https://raw.githubusercontent.com/zeusintuivo/bash_intuivo_cli/master/link_folder_scripts | bash
```
The scripts above are cloning this repository to `~/bin/journal_intuivo_cli` and then downloading and runnning `link_folder_scripts` which in turn will create softlinks inside  `/usr/local/bin/`

I am assuming that `/usr/local/bin/`  is inside your local environment variable $PATH if not you can check with this one liner
```
echo $PATH | sed 's/[:]/\n/g' | sort | uniq | [[ "$(grep '/usr/local/bin')" == *"/usr/local/bin"* ]] && echo "\\033[38;5;2mYup\! '/usr/local/bin' is in your local \$PATH.\\033[0m"
```
If you see a green `Yup! '/usr/local/bin' is in your local $PATH.`  then you are ready
If you see nothing from the line above. Then I recomend you google how to add things to your $PATH variable.

# USAGE

The concept that you can create work branch using command line deṕending on your work environment

using: `newissue      `  makes a new branch using the issue-TICKET namming with normal branching
using: `newfeature    `  makes a new branch using the feature/TICKET namming with git flow if available, otherwise normal branching
using: `newworkbranchg`  makes a new branch using only normal namming, and normal branching

All these are the start of your work.

They will all create a branch from another branch and build a description for it

using: `describe         `  will show you this description. You can also assign a new descript using the same command
using: `edit_description `  will let you change the description that is inside `git config`
using: `description_edit `  will let you change the description that is inside `git config`

Once you are working, you can  keep on adding new work statuses of descriptions using the `work` command

using: `work          `  will restart a new note inside your journal folder, you can also pass a new description for it



when you are done

You can use `journaladdfiles` to same snapshots out of git. In case you want to keep track, of certain things you commit or made. Because the branches will later get deleted.
And sometimes you just want to keep the recipe of how you made those changes.

using: 'journalentry'   ...good question I ..still need to check if this one work s


When you open an `ìssue` branch then you are forced to use `issue` format
so then you have to commit with
` issueput    `   Commits and pushes the change
and
` issuecommit `   Just commits

They both will build a commit message that looks like this

```
refs #30515 @0:20 I fixed some issues here
```

refs means "referencing"
#1234 where 1234 is the TICKET ID or TICKET NAME from the issue you are fixing
@XX:XX is the time it took you to for this commit, you can make many commit and are 5 minutes or 6 minutes to every commit and then add the total later based on your own commit messages
"I fixed something" is it quite clear that is the just the message


The neat thing that I have coupled this issue-commands with my other git project `https://github.com/zeusintuivo/git_intuivo_cli`
which I also recommend
where then you can install it the same way you installed this
and you call issueouts with `verbs`
like this
```
updated 0:05 the description readme file
```

This command above will figure out if the branch has an issue namming style and then try to find issueput if available to commit .


More to come, as I debbug and fix things .



