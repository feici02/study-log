### GitHub/GitBook Integration Workflow

1. Create a new repo on Github, for example: my-gitbook-test
1. Clone this repo:
```
git clone https://github.com/feici02/my-gitbook-test.git```
1. Create a new book with GitBook command line tool:
```
cd my-gitbook-test
gitbook init
```
1. Make some changes to this book, for example: add 2 chapters.
1. When your changes are done, you can preview your book locally.
```
gitbook serve
```
1. Copy a .gitignore file from other GitBooks.
1. If you are satisfied with the book, check in these changes.
```
git status
git add -A
git commit -m "initial commit"
```
1. Push your repo to Github.
```
git push -u origin master
```
1. Now, you can view this book on GitHub.
1. On GitBook, configure the integration with GitHub in ```Account Settings - GitHub```.
1. On GitHub, ```Settings - Installed integrations - GitBook Configure```, you can specify your repos that can be accessed by GitBook.
1. Create on new book on GitBook by importing from Github.
1. If the integration is setup correctly, when you push new changes to the GitHub repo, your GitBook will be updated automatically.
