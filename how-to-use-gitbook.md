## How to use GitBook?

### 1. GitBook Toolchain Installation
```
npm install gitbook-cli -g
```
Refer to [GitBook Toolchain Documentation](https://toolchain.gitbook.com/) for details.

### 2. Workflow
1. Create a free account on [GitBook](https://www.gitbook.com).
1. Create a new book on GitBook, for example: my-first-book
1. Open a terminal, and run following commands:
```
git clone https://git.gitbook.com/feici02/my-first-book.git
cd my-first-book
gitbook serve
```
1. The book is served at: http://localhost:4000
1. Make some changes to this book, for example: add a new chapter.
1. Run following commands to check-in your changes:
```
git add -A
git commit -m "add a new chapter"
```
1. Run following commands to push your changes to GitBook:
```
git push -u origin master
```
1. The book is served on GitBook.
