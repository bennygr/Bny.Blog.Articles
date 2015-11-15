<!--
Title:"Using WinMerge as Git difftool",
Date:"2014-09-04T20:41+0200",
Tags:"Git,WinMerge",
PreviewLength:"126"
-->
To use [WinMerge](http://winmerge.org) as diff viewer from within git, a few things need to be added to the git configuration which can be found at *%USERPROFILE%\.gitconfig*:

		[diff]
		tool = winmerge
		[difftool "winmerge"]
		cmd = winmergeu.exe -e -ub -x -wl -u -maximise -dl "base" -dr "mine" \"$LOCAL\" \"$REMOTE\"
