# word-repo
 Version control for MS-Word docs

MS Word documents are treated as binary files by default in `git`. Here this repo uses `pandoc` utility to convert word docs on the fly to markdown such that commands like `git diff` can work locally to see changes made in the word documents. This provides an efficient version control to track changes for people writing long word documents that requires frequent and sometimes collaborative editing.

## Prerequisites
`pandoc` : Download from here: [Link](https://github.com/jgm/pandoc/releases/)

Add the following lines in either `.gitconfig` file in the local computer or add these line in `.git/config`
```
[diff "pandoc"]
  textconv=pandoc --to=markdown
  prompt = false
[alias]
  wdiff = diff --word-diff=color --unified=1
```

**NB**:

`.gitconfig` file location:
- Windows: `C:\Users\<username>\.gitconfig`
- Linux: `/home/<username>/.gitconfig`

Acknowledgement: [Link](https://blog.front-matter.io/posts/using-microsoft-word-with-git/)
