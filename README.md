# Tool Repo
===========
This repository serves as a sort of master repository of various tools that people have come across.

The format for structure should be as follows:

	top-level repo -
			project_name -
				      README.md (review/information)
				      git submodule to repo (if appropriate)

Please do not put any actual code in here.


## Example

Adding a repo:

	mkdir project_name
	git submodule add https://github.com/username/project_name project_name/repo
	echo "[link](http://github.com/username/project_name)" > project_name/README.md
	git add project_name
	git commit -am 'added project_name'
