Following the article below

	http://blog.martinfenner.org/2014/08/25/using-microsoft-word-with-git/
	
安装pandoc

	brew install pandoc
	
修改.gitattributes 文件
	
	# .gitattributes file in root folder of your git project
	*.docx diff=pandoc

修改 ~/.gitconfig 文件
	
	# .gitconfig file in your home folder
	[diff "pandoc"]
  		textconv=pandoc --to=markdown
  		prompt = false
	[alias]
  		wdiff = diff --word-diff=color --unified=1
  		
You can then use **git wdiff important_file.docx** to see the changes (with deletions in red and insertions in green), or **git log -p --word-diff=color important_file.docx** to see all changes over time.

